## 8.10 - Comparação de strings

Os operadores relacionais funcionam em strings. Para ver se duas strings são iguais:

```python
if word == 'banana':
    print('All right, bananas.')
```

Outras operações relacionais são úteis para colocar palavras em ordem alfabética:

```python
if word < 'banana':
    print('Your word, ' + word + ', comes before banana.')
elif word > 'banana':
    print('Your word, ' + word + ', comes after banana.')
else:
    print('All right, bananas.')
```

O Python não lida com letras maiúsculas e minúsculas do mesmo jeito que as pessoas. Todas as letras maiúsculas vêm antes de todas as letras minúsculas, portanto:

```python
Your word, Pineapple, comes before banana.
```

Uma forma comum de lidar com este problema é converter strings em um formato padrão, como letras minúsculas, antes de executar a comparação. Lembre-se disso caso tenha que se defender de um homem armado com um abacaxi.
