## 18.7 - Herança

A herança é a capacidade de definir uma nova classe que seja uma versão modificada de uma classe existente. Como exemplo, digamos que queremos que uma classe represente uma “mão”, isto é, as cartas mantidas por um jogador. Uma mão é semelhante a um baralho: ambos são compostos por uma coleção de cartas, e ambos exigem operações como adicionar e remover cartas.

Uma mão também é diferente de um baralho; há operações que queremos para mãos que não fazem sentido para um baralho. Por exemplo, no pôquer poderíamos comparar duas mãos para ver qual ganha. No bridge, poderíamos calcular a pontuação de uma mão para fazer uma aposta.

Essa relação entre classes – semelhante, mas diferente – adequa-se à herança. Para definir uma nova classe que herda algo de uma classe existente, basta colocar o nome da classe existente entre parênteses:

```python
class Hand(Deck):
    """Represents a hand of playing cards."""
```

Esta definição indica que Hand herda de Deck; isso significa que podemos usar métodos como pop\_card e add\_card para Hand bem como para Deck.

Quando uma nova classe herda de uma existente, a existente chama-se pai e a nova classe chama-se filho.

Neste exemplo, Hand herda `__init__` de Deck, mas na verdade não faz o que queremos: em vez de preencher a mão com 52 cartas novas, o método init de Hand deve inicializar card com uma lista vazia.

Se fornecermos um método init na classe Hand, ele ignora o da classe Deck:

```python
# dentro da classe Hand:

    def __init__(self, label=''):
        self.cards = []
        self.label = label
```

Ao criar Hand, o Python invoca este método init, não o de Deck.

```python
>>> hand = Hand('new hand')
>>> hand.cards
[]
>>> hand.label
'new hand'
```

Outros métodos são herdados de Deck, portanto podemos usar `pop_card` e `add_card` para lidar com uma carta:

```python
>>> deck = Deck()
>>> card = deck.pop_card()
>>> hand.add_card(card)
>>> print(hand)
King of Spades
```

Um próximo passo natural seria encapsular este código em um método chamado `move_cards`:

```python
# dentro da classe Deck:

    def move_cards(self, hand, num):
        for i in range(num):
            hand.add_card(self.pop_card())
```

`move_cards` recebe dois argumentos, um objeto Hand e o número de cartas com que vai lidar. Ele altera tanto self como hand e retorna None.

Em alguns jogos, as cartas são movidas de uma mão a outra, ou de uma mão de volta ao baralho. É possível usar `move_cards` para algumas dessas operações: self pode ser um Deck ou Hand, e hand, apesar do nome, também pode ser um Deck.

A herança é um recurso útil. Alguns programas que poderiam ser repetitivos sem herança podem ser escritos de forma mais elegante com ela. A herança pode facilitar a reutilização de código, já que você pode personalizar o comportamento de classes pais sem ter que alterá-las. Em alguns casos, a estrutura de herança reflete a estrutura natural do problema, o que torna o projeto mais fácil de entender.

De outro lado, a herança pode tornar os programas difíceis de ler. Quando um método é invocado, às vezes não está claro onde encontrar sua definição. O código relevante pode ser espalhado por vários módulos. Além disso, muitas das coisas que podem ser feitas usando a herança podem ser feitas sem elas, às vezes, até de forma melhor.
