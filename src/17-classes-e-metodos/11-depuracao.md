## 17.11 - Depuração

É legal acrescentar atributos a objetos em qualquer ponto da execução de um programa, mas se você tiver objetos do mesmo tipo que não têm os mesmos atributos, é fácil cometer erros. É uma boa ideia inicializar todos os atributos de um objeto no [método](12-glossario.md#método) init.

Caso não tenha certeza se um objeto tem um determinado atributo, você pode usar a função integrada hasattr (ver “Depuração”, na página 236).

Outra forma de acessar atributos é com a função integrada vars, que recebe um objeto e retorna um dicionário que mapeia os nomes dos atributos (como strings) aos seus valores:

```python
>>> p = Point(3, 4)
>>> vars(p)
{'y': 4, 'x': 3}
```

Para facilitar a depuração, pode ser útil usar esta função:

```python
def print_attributes(obj):
    for attr in vars(obj):
        print(attr, getattr(obj, attr))
```

`print_attributes` atravessa o dicionário e imprime cada nome de atributo e o seu valor correspondente.

A função integrada getattr recebe um objeto e um nome de atributo (como uma string) e devolve o valor do atributo.
