## 17.6 - Método `__str__`

`__str__` é um método especial, como `__init__`, usado para retornar uma representação de string de um objeto.

Por exemplo, aqui está um método str para objetos Time:

```python
# dentro da classe Time:

    def __str__(self):
        return '%.2d:%.2d:%.2d' % (self.hour, self.minute, self.second)
```

Ao exibir um objeto com print, o Python invoca o método str:

```python
>>> time = Time(9, 45)
>>> print(time)
09:45:00
```

Quando escrevo uma nova classe, quase sempre começo escrevendo `__init__`, o que facilita a instanciação de objetos, e `__str__`, que é útil para a depuração.

Como exercício, escreva um método str da classe Point. Crie um objeto Point e exiba-o.
