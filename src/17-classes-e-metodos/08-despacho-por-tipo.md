## 17.8 - Despacho por tipo

Na seção anterior, acrescentamos dois objetos Time, mas você também pode querer acrescentar um número inteiro a um objeto Time. A seguir, veja uma versão de `__add__`, que verifica o tipo de other e invoca `add_time` ou increment:

```python
# dentro da classe Time:
    def __add__(self, other):
        if isinstance(other, Time):
            return self.add_time(other)
        else:
            return self.increment(other)

    def add_time(self, other):
        seconds = self.time_to_int() + other.time_to_int()
        return int_to_time(seconds)

    def increment(self, seconds):
        seconds += self.time_to_int()
        return int_to_time(seconds)
```

A função construída isinstance recebe um valor e um objeto de classe e retorna True se o valor for uma instância da classe.

Se other for um objeto Time, `__add__` invoca `add_time`. Do contrário, assume que o parâmetro seja um número e invoca increment. Essa operação chama-se despacho por tipo porque despacha a operação a métodos diferentes, baseados no tipo dos argumentos.

Veja exemplos que usam o operador `+` com tipos diferentes:

```python
>>> start = Time(9, 45)
>>> duration = Time(1, 35)
>>> print(start + duration)
11:20:00
>>> print(start + 1337)
10:07:17
```

Infelizmente, esta implementação da adição não é comutativa. Se o número inteiro for o primeiro operando, você recebe

```python
>>> print(1337 + start)
TypeError: unsupported operand type(s) for +: 'int' and 'instance'
```

O problema é que, em vez de pedir ao objeto Time que adicione um número inteiro, o Python está pedindo que um número inteiro adicione um objeto Time, e ele não sabe como fazer isso. Entretanto, há uma solução inteligente para este problema: o método especial `__radd__`, que significa “adição à direita”. Esse método é invocado quando um objeto Time aparece no lado direito do operador +. Aqui está a definição:

```python
# dentro da classe Time:
    def __radd__(self, other):
        return self.__add__(other)
```

E é assim que ele é usado:

```python
>>> print(1337 + start)
10:07:17
```

Como exercício, escreva um método add para Points que funcione com um objeto Point ou com uma tupla:

* Se o segundo operando for um Point, o método deve retornar um novo Point cuja coordenada x é a soma das coordenadas x dos operandos, e o mesmo se aplica às coordenadas de y.

* Se o segundo operando for uma tupla, o método deve adicionar o primeiro elemento da tupla à coordenada de x e o segundo elemento à coordenada de y, retornando um novo Point com o resultado.
