## 3.8 - As variáveis e os parâmetros são locais

Quando você cria uma variável dentro de uma [função](13-glossario.md#função), ela é local, ou seja, ela só existe dentro da função. Por exemplo:


```python
def cat_twice(part1, part2):
    cat = part1 + part2
    print_twice(cat)
```

Esta função recebe dois argumentos, concatena-os e exibe o resultado duas vezes. Aqui está um exemplo que a usa:



```python
>>> line1 = 'Bing tiddle '
>>> line2 = 'tiddle bang.'
>>> cat_twice(line1, line2)
Bing tiddle tiddle bang.
Bing tiddle tiddle bang.
```

Quando `cat_twice` é encerrada, a variável `cat` é destruída. Se tentarmos exibi-la, recebemos uma exceção:

```python
>>> print(cat)
NameError: name 'cat' is not defined
```

Os parâmetros também são locais. Por exemplo, além de print\_twice, não existe o bruce.
