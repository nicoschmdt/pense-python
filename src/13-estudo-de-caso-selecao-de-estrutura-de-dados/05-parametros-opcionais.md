## 13.5 - Parâmetros opcionais

Vimos funções integradas e métodos que recebem argumentos opcionais. É possível escrever funções definidas pelos programadores com argumentos opcionais, também. Por exemplo, aqui está uma função que exibe as palavras mais comuns em um histograma:

```python
def print_most_common(hist, num=10):
    t = most_common(hist)
    print('The most common words are:')
    for freq, word in t[:num]:
        print(word, freq, sep='\\t')
```

O primeiro parâmetro é necessário; o segundo é opcional. O valor padrão de `num` é 10.

Se você só fornecer um argumento:

```python
print_most_common(hist)
```

num recebe o valor padrão. Se fornecer dois argumentos:

```python
print_most_common(hist, 20)
```

num recebe o valor do argumento em vez disso. Em outras palavras, o argumento opcional ignora o valor padrão.

Se uma função tem ambos os parâmetros obrigatório e opcional, todos os parâmetros necessários têm que vir primeiro, seguidos pelos opcionais.
