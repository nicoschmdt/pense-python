## 17.7 - Sobrecarga de operadores

Ao definir outros métodos especiais, você pode especificar o comportamento de operadores nos tipos definidos pelo programador. Por exemplo, se você definir um método chamado `__add__` para a classe Time de Time, pode usar o operador + em objetos Time.

A definição pode ser assim:

```python
# dentro da classe Time:

    def __add__(self, other):
        seconds = self.time_to_int() + other.time_to_int()
        return int_to_time(seconds)
```


Você pode usá-lo assim:

```python
>>> start = Time(9, 45)
>>> duration = Time(1, 35)
>>> print(start + duration)
11:20:00
```

Ao aplicar o operador + a objetos Time, o Python invoca `__add__`. Ao exibir o resultado, o Python invoca `__str__`. Ou seja, há muita coisa acontecendo nos bastidores!

Alterar o comportamento de um operador para que funcione com tipos definidos pelo programador chama-se sobrecarga de operadores. Para cada operador no Python há um método especial correspondente, como `__add__`. Para obter mais informações, veja [http://docs.python.org/3/reference/datamodel.html\#specialnames](http://docs.python.org/3/reference/datamodel.html\#specialnames).

Como exercício, escreva um método add para a classe Point.
