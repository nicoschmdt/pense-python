## 8.6 - Buscando

```python
O que faz a seguinte função?
def find(word, letter):
    index = 0
    while index < len(word):
        if word[index] == letter:
            return index
        index = index + 1
    return-1
```

De certo modo, `find` é o inverso do operador `[]`. Em vez de tomar um índice e extrair o caractere correspondente, ele toma um caractere e encontra o índice onde aquele caractere aparece. Se o caractere não for encontrado, a função retorna -1.

Esse é o primeiro exemplo que vimos de uma instrução `return` dentro de um loop. Se `word[index] == letter`, a função sai do loop e retorna imediatamente.

Se o caractere não aparecer na string, o programa sai do loop normalmente e devolve -1.

Este modelo de cálculo – atravessar uma sequência e retornar quando encontramos o que estamos procurando – chama-se busca.

Como exercício, altere `find` para que tenha um terceiro parâmetro: o índice em `word` onde deve começar a busca.
