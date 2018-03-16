## 19.5 - Conjuntos

Na seção “Subtração de dicionário”, da página 198, uso dicionários para encontrar as palavras que aparecem em um documento, mas não numa lista de palavras. A função que escrevi recebe d1, que contém as palavras do documento como chaves e d2, que contém a lista de palavras. Ela retorna um dicionário que contém as chaves de d1 que não estão em d2:

```python
def subtract(d1, d2):
    res = dict()
    for key in d1:
        if key not in d2:
            res[key] = None
    return res
```

Em todos esses dicionários, os valores não são None porque nunca os usamos. O resultado é que desperdiçamos espaço de armazenamento.

O Python fornece outro tipo integrado, chamado set (conjunto), que se comporta como uma coleção de chaves de dicionário sem valores. Acrescentar elementos a um conjunto é rápido; assim como verificar a adesão. E os conjuntos fornecem métodos e operadores para calcular operações de conjuntos.

Por exemplo, a subtração de conjuntos está disponível como um método chamado difference ou como um operador, -. Portanto, podemos reescrever subtract desta forma:

```python
def subtract(d1, d2):
    return set(d1) - set(d2)
```

O resultado é um conjunto em vez de um dicionário, mas, para operações como iteração, o comportamento é o mesmo.

Alguns exercícios neste livro podem ser feitos de forma concisa e eficiente com conjuntos. Por exemplo, aqui está uma solução para has\_duplicates, do Exercício 10.7, que usa um dicionário:

```python
def has_duplicates(t):
    d = {}
    for x in t:
        if x in d:
            return True
        d[x] = True
    return False
```

Quando um elemento aparece pela primeira vez, ele é acrescentado ao dicionário. Se o mesmo elemento aparece novamente, a função retorna True.

Usando conjuntos, podemos escrever a mesma função dessa forma:

```python
def has_duplicates(t):
    return len(set(t)) < len(t)
```

Um elemento só pode aparecer em um conjunto uma vez, portanto, se um elemento em t aparecer mais de uma vez, o conjunto será menor que t. Se não houver duplicatas, o conjunto terá o mesmo tamanho que t.

Também podemos usar conjuntos para fazer alguns exercícios no Capítulo 9. Por exemplo, aqui está uma versão de uses\_only com um loop:

```python
def uses_only(word, available):
    for letter in word:
        if letter not in available:
            return False
    return True
```

`uses_only` verifica se todas as cartas em word estão em available. Podemos reescrevê-la assim:

```python
def uses_only(word, available):
    return set(word) <= set(available)
```

O operador `<=` verifica se um conjunto é um subconjunto ou outro, incluindo a possibilidade de que sejam iguais, o que é verdade se todas as letras de word aparecerem em available.

Como exercício, reescreva avoids usando conjuntos.
