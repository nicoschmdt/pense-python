## 18.3 - Comparação de cartas

Para tipos integrados, há operadores relacionais (`<`, `>`, `==` etc.) que comparam valores e determinam quando um é maior, menor ou igual a outro. Para tipos definidos pelo programador, podemos ignorar o comportamento dos operadores integrados fornecendo um método denominado `__lt__`, que representa “menos que”.

`__lt__` recebe dois parâmetros, `self` e `other`, e `True` se self for estritamente menor que `other`.

A ordem correta das cartas não é óbvia. Por exemplo, qual é melhor, o 3 de paus ou o 2 de ouros? Uma tem o valor mais alto, mas a outra tem um naipe mais alto. Para comparar cartas, é preciso decidir o que é mais importante, o valor ou o naipe.

A resposta pode depender de que jogo você está jogando, mas, para manter a simplicidade, vamos fazer a escolha arbitrária de que o naipe é mais importante, então todas as cartas de espadas são mais importantes que as de ouros, e assim por diante.

Com isto decidido, podemos escrever `__lt__`:

```python
# dentro da classe Card:

    def __lt__(self, other):
        # conferir os naipes
        if self.suit < other.suit: return True
        if self.suit > other.suit: return False

        # os naipes são os mesmos... conferir valores
        return self.rank < other.rank
```

Você pode escrever isso de forma mais concisa usando uma comparação de tuplas:

```python
# dentro da classe Card:

    def __lt__(self, other):
        t1 = self.suit, self.rank
        t2 = other.suit, other.rank
        return t1 < t2
```

Como exercício, escreva um método `__lt__` para objetos Time. Você pode usar uma comparação de tuplas, mas também pode usar a comparação de números inteiros.
