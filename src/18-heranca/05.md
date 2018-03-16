## 18.5 - Exibição do baralho

Aqui está um método __str__ para Deck:

```python
# dentro da classe Deck:

    def __str__(self):
        res = []
        for card in self.cards:
            res.append(str(card))
        return '\n'.join(res)
```

Este método demonstra uma forma eficiente de acumular uma string grande: a criação de uma lista de strings e a utilização do método de string join. A função integrada str invoca o método `__str__` em cada carta e retorna a representação da string.

Como invocamos join em um caractere newline, as cartas são separadas por quebras de linha. O resultado é esse:

```python
>>> deck = Deck()
>>> print(deck)
Ace of Clubs
2 of Clubs
3 of Clubs
...
10 of Spades
Jack of Spades
Queen of Spades
King of Spades
```

Embora o resultado apareça em 52 linhas, na verdade ele é uma string longa com quebras de linha.
