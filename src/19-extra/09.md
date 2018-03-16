## 19.9 - Reunindo argumentos de palavra-chave

Em “Tuplas com argumentos de comprimento variável”, na página 181, vimos como escrever uma função que reúne seus argumentos em uma tupla:

```python
def printall(*args):
    print(args)
```

Você pode chamar esta função com qualquer número de argumentos posicionais (isto é, argumentos que não têm palavras-chave):

```python
>>> printall(1, 2.0, '3')
(1, 2.0, '3')
```

Porém, o operador `*` não reúne argumentos de palavra-chave:

```python
>>> printall(1, 2.0, third='3')
TypeError: printall() got an unexpected keyword argument 'third'
```

Para reunir argumentos de palavra-chave, você pode usar o operador `**`:

```python
def printall(*args, **kwargs):
    print(args, kwargs)
```

Você pode chamar o parâmetro de coleta de palavra-chave, como quiser, mas `kwargs` é uma escolha comum. O resultado é um dicionário que mapeia palavras-chave a valores:

```python
>>> printall(1, 2.0, third='3')
(1, 2.0) {'third': '3'}
```

Se tiver um dicionário de palavras-chave e valores, pode usar o operador de dispersão, `**`, para chamar uma função:

```python
>>> d = dict(x=1, y=2)
>>> Point(**d)
Point(x=1, y=2)
```

Sem o operador de dispersão, a função trataria d como um único argumento posicional, e então atribuiria d a x e se queixaria porque não há nada para atribuir a y:

```python
>>> d = dict(x=1, y=2)
>>> Point(d)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: __new__() missing 1 required positional argument: 'y'
```

Quando estiver trabalhando com funções com um grande número de parâmetros, muitas vezes é útil criar dicionários e passá-los como argumentos para especificar as opções usadas com maior frequência.
