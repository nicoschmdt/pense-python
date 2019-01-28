## 17.2 - Exibição de objetos

No Capítulo 16 definimos uma classe chamada Time em “Time”, na página 231, e você escreveu uma função denominada `print_time`:

```python
class Time:
    """Represents the time of day."""

def print_time(time):
    print('%.2d:%.2d:%.2d' % (time.hour, time.minute, time.second))
```

Para chamar esta função, você precisa passar um objeto Time como argumento:

```python
>>> start = Time()
>>> start.hour = 9
>>> start.minute = 45
>>> start.second = 00
>>> print_time(start)
09:45:00
```

Para fazer de `print_time` um [método](12-glossario.md#método), tudo o que precisamos fazer é mover a definição da função para dentro da definição da classe. Note a alteração na endentação:

```python
class Time:
    def print_time(time):
        print('%.2d:%.2d:%.2d' % (time.hour, time.minute, time.second))
```

Agora há duas formas de chamar `print_time`. A primeira forma (e menos comum) é usar a sintaxe de função:

```python
>>> Time.print_time(start)
09:45:00
```

Nesse uso da notação de ponto, Time é o nome da classe, e `print_time` é o nome do método. `start` é passado como um parâmetro.

A segunda forma (e mais concisa) é usar a sintaxe de método:

```python
>>> start.print_time()
09:45:00
```

Nesse uso da notação de ponto, `print_time` é o nome do método (novamente), e `start` é o objeto no qual o método é invocado, que se chama de [sujeito](12-glossario.md#sujeito). Assim como em uma sentença, onde o sujeito é o foco da escrita, o sujeito de uma invocação de método é o foco do método.

Dentro do método, o sujeito é atribuído ao primeiro parâmetro, portanto, neste caso, `start` é atribuído a `time`.

Por convenção, o primeiro parâmetro de um método chama-se `self`, então seria mais comum escrever `print_time` desta forma:

```python
class Time:
    def print_time(self):
        print('%.2d:%.2d:%.2d' % (self.hour, self.minute, self.second))
```

A razão dessa convenção é uma metáfora implícita:

* A sintaxe de uma chamada de função, `print_time(start)`, sugere que a função é o agente ativo. Ela diz algo como: “Ei, `print_time`! Aqui está um objeto para você exibir”.

* Na [programação orientada a objeto](12-glossario.md#programação-orientada a objeto), os objetos são os agentes ativos. Uma invocação de método `como start.print_time()` diz: “Ei, `start`! Por favor, exiba-se”.

Essa mudança de perspectiva pode ser mais polida, mas não é óbvio que seja útil. Nos exemplos que vimos até agora, pode não ser. Porém, às vezes, deslocar a responsabilidade das funções para os objetos permite escrever funções (ou métodos) mais versáteis e facilita a manutenção e reutilização do código.

Como exercício, reescreva `time_to_int` (de “Prototipação versus planejamento”, na página 234) como um método. Você pode ficar tentado a reescrever `int_to_time` como um método também, mas isso não faz muito sentido porque não haveria nenhum objeto sobre o qual invocá-lo.
