## 8.9 - Operador in

A palavra `in` é um operador booleano que recebe duas strings e retorna `True` se a primeira aparecer como uma substring da segunda:

```python
>>> 'a' in 'banana'
True
>>> 'seed' in 'banana'
False
```

Por exemplo, a seguinte função imprime todas as letras de `word1` que também aparecem em `word2`:

```python
def in_both(word1, word2):
    for letter in word1:
        if letter in word2:
            print(letter)
```

Com nomes de variáveis bem escolhidos, o Python às vezes pode ser lido como um texto em inglês. Você pode ler este loop, “para (cada) letra em (a primeira) palavra, se (a) letra (aparecer) em (a segunda) palavra, exiba (a) letra”.

Veja o que é apresentado ao se comparar maçãs e laranjas:

```python
>>> in_both('apples', 'oranges')
a
e
s
```
