## 13.3 - Histograma de palavras

É uma boa ideia tentar fazer os exercícios anteriores antes de continuar. Você pode baixar minha solução em http://thinkpython2.com/code/analyze_book1.py. Também vai precisar de http://thinkpython2.com/code/emma.txt.

Aqui está um programa que lê um arquivo e constrói um histograma das palavras no arquivo:

```python
import string

def process_file(filename):
    hist = dict()
    fp = open(filename)
    for line in fp:
        process_line(line, hist)
    return hist

def process_line(line, hist):
    line = line.replace('-', ' ')
    for word in line.split():
        word = word.strip(string.punctuation + string.whitespace)
        word = word.lower()
        hist[word] = hist.get(word, 0) + 1

hist = process_file('emma.txt')
```

Este programa lê `emma.txt`, que contém o texto de _Emma_, de Jane Austen.

`process_file` faz o loop pelas linhas do arquivo, passando-as uma a uma para `process_line`. O histograma hist está sendo usado como um acumulador.

`process_line` usa o método de string replace para substituir hifens por espaços antes de usar split para quebrar a linha em uma lista de strings. Ele atravessa a lista de palavras e usa strip e lower para retirar a pontuação e converter tudo em letras minúsculas. (Dizer que as strings “são convertidas” é uma forma simples de explicar a coisa; lembre-se de que as strings são imutáveis, então métodos como strip e lower retornam novas strings.)

Finalmente, `process_line` atualiza o histograma, criando um novo item ou incrementando um existente.

Para contar o número total de palavras no arquivo, podemos somar as frequências no histograma:

```python
def total_words(hist):
    return sum(hist.values())
```

O número de palavras diferentes é somente o número de itens no dicionário:


```python
def different_words(hist):
    return len(hist)
```

Aqui está o código para exibir os resultados:

```python
print('Total number of words:', total_words(hist))
print('Number of different words:', different_words(hist))
```

E os resultados:

```python
Total number of words: 161080
Number of different words: 7214
```
