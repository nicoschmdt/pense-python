## 13.7 - Palavras aleatórias

Para escolher uma palavra aleatória do histograma, o algoritmo mais simples é construir uma lista com várias cópias de cada palavra, segundo a frequência observada, e então escolher da lista:

```python
def random_word(h):
    t = []
    for word, freq in h.items():
        t.extend([word] * freq)
    return random.choice(t)
```

A expressão `[word] * freq` cria uma lista com `freq` cópias da string `word`. O método `extend` é similar a `append`, exceto pelo argumento, que é uma sequência.

Esse algoritmo funciona, mas não é muito eficiente; cada vez que você escolhe uma palavra aleatória, ele reconstrói a lista, que é tão grande quanto o livro original. Uma melhoria óbvia é construir a lista uma vez e então fazer seleções múltiplas, mas a lista ainda é grande.

Uma alternativa é:

1. Usar `keys` para conseguir uma lista das palavras no livro.

2. Construir uma lista que contenha a soma cumulativa das frequências das palavras (veja o Exercício 10.2). O último item desta lista é o número total de palavras no livro, n.

3. Escolher um número aleatório de 1 a n. Use uma pesquisa de bisseção (veja o Exercício 10.10) para encontrar o índice onde o número aleatório seria inserido na soma cumulativa.

4. Usar o índice para encontrar a palavra correspondente na lista de palavras.

### Exercício 13.7

Escreva um programa que use este algoritmo para escolher uma palavra aleatória do livro.

Solução: [http://thinkpython2.com/code/analyze_book3.py](http://thinkpython2.com/code/analyze_book3.py).
