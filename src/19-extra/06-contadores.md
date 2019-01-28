## 19.6 - Contadores

Um contador é como um conjunto, exceto que se um elemento aparecer mais de uma vez, o contador registra quantas vezes ele aparece. Se tiver familiaridade com a ideia matemática de um [multiconjunto](10-glossario.md#multiconjunto) (multiset), um contador é uma forma natural de representar um multiconjunto.

Contadores são definidos em um módulo padrão chamado `collections`, portanto é preciso importá-lo. Você pode inicializar um contador com uma string, lista ou alguma outra coisa que seja compatível com iteração:

```python
>>> from collections import Counter
>>> count = Counter('parrot')
>>> count
Counter({'r': 2, 't': 1, 'o': 1, 'p': 1, 'a': 1})
```

Os contadores comportam-se como dicionários de muitas formas; eles mapeiam cada chave ao número de vezes que aparece. Como em dicionários, as chaves têm de ser hashable.

Ao contrário de dicionários, os contadores não causam uma exceção se você acessar um elemento que não aparece. Em vez disso, retornam 0:

```python
>>> count['d']
0
```

Podemos usar contadores para reescrever `is_anagram` do Exercício 10.6:

```python
def is_anagram(word1, word2):
    return Counter(word1) == Counter(word2)
```

Se duas palavras forem anagramas, elas contêm as mesmas letras com as mesmas contagens, então seus contadores são equivalentes.

Os contadores oferecem métodos e operadores para executar operações similares às dos conjuntos, incluindo adição, subtração, união e intersecção. E eles fornecem um método muitas vezes útil, most_common, que retorna uma lista de pares frequência-valor, organizados do mais ao menos comum:

```python
>>> count = Counter('parrot')
>>> for val, freq in count.most_common(3):
...     print(val, freq)
r 2
p 1
a 1
```
