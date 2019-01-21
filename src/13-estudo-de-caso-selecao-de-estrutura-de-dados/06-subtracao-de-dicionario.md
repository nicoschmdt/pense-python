## 13.6 - Subtração de dicionário

Encontrar as palavras do livro que não estão na lista de palavras de words.txt é um problema que você pode reconhecer como subtração de conjuntos; isto é, queremos encontrar todas as palavras de um conjunto (as palavras no livro) que não estão no outro (as palavras na lista).

`subtract` recebe os dicionários `d1` e `d2` e devolve um novo dicionário que contém todas as chaves de `d1` que não estão em `d2`. Como não nos preocupamos com os valores, estabelecemos todos como `None`:

```python
def subtract(d1, d2):
    res = dict()
    for key in d1:
        if key not in d2:
            res[key] = None
    return res
```

Para encontrar as palavras no livro que não estão em words.txt, podemos usar `process_file` para construir um histograma para words.txt, e então subtrair:

```python
words = process_file('words.txt')
diff = subtract(hist, words)
print("Words in the book that aren't in the word list:")
for word in diff:
    print(word, end=' ')
```


Aqui estão alguns resultados de Emma:

```
Words in the book that aren't in the word list:
rencontre jane's blanche woodhouses disingenuousness
friend's venice apartment ...
```

Algumas dessas palavras são nomes e possessivos. Os outros, como “rencontre”, já não são de uso comum. Mas algumas são palavras comuns que realmente deveriam estar na lista!

### Exercício 13.6

O Python fornece uma estrutura de dados chamada `set`, que fornece muitas operações de conjunto. Você pode ler sobre elas em “Conjuntos”, na página 274, ou ler a documentação em [http://docs.python.org/3/library/stdtypes.html#types-set](http://docs.python.org/3/library/stdtypes.html#types-set).

Escreva um programa que use a subtração de conjuntos para encontrar palavras no livro que não estão na lista de palavras.

Solução: [http://thinkpython2.com/code/analyze_book2.py](http://thinkpython2.com/code/analyze_book2.py).
