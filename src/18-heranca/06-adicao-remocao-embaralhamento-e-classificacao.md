## 18.6 - Adição, remoção, embaralhamento e classificação

Para lidar com as cartas, gostaríamos de ter um método que removesse uma carta do baralho e a devolvesse. O método de lista pop oferece uma forma conveniente de fazer isso:

```python
# dentro da classe Deck:

    def pop_card(self):
        return self.cards.pop()
```

Como pop retira a última carta na lista, estamos lidando com o fundo do baralho.

Para adicionar uma carta, podemos usar o método de lista append:

```python
# dentro da classe Deck:

    def add_card(self, card):
        self.cards.append(card)
```

Um método como esse, que usa outro método sem dar muito trabalho, às vezes é chamado de folheado. A metáfora vem do trabalho em madeira, onde o folheado é uma camada fina de madeira de boa qualidade colada à superfície de uma madeira mais barata para melhorar a aparência.

Nesse caso, `add_card` é um método “fino” que expressa uma operação de lista em termos adequados a baralhos. Ele melhora a aparência ou interface da implementação.

Em outro exemplo, podemos escrever um método Deck denominado shuffle, usando a função shuffle do módulo random:


```python
# dentro da classe Deck:

    def shuffle(self):
        random.shuffle(self.cards)
```

Não se esqueça de importar random.

Como exercício, escreva um método de Deck chamado sort, que use o método de lista sort para classificar as cartas em um Deck. sort usa o método `__lt__` que definimos para determinar a ordem.
