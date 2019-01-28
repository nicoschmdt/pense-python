## 17.4 - Um exemplo mais complicado

Reescrever `is_after` (de “Time”, na página 231) é ligeiramente mais complicado, porque ela recebe dois objetos Time como parâmetros. Nesse caso, a convenção é denominar o primeiro parâmetro self e o segundo parâmetro other:

```python
# dentro da classe Time:

    def is_after(self, other):
        return self.time_to_int() > other.time_to_int()
```

Para usar este [método](12-glossario.md#método), você deve invocá-lo para um objeto e passar outro como argumento:

```python
>>> end.is_after(start)
True
```

Uma vantagem desta sintaxe é que é quase literal em inglês: “o fim é depois da partida?”.
