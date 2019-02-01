## 18.12 - Exercícios

### Exercício 18.1

Para o seguinte programa, desenhe um [diagrama de classe](11-glossario.md#diagrama-de classe) UML que mostre estas classes e as relações entre elas.

```python
class PingPongParent:
    pass

class Ping(PingPongParent):
    def __init__(self, pong):
        self.pong = pong

class Pong(PingPongParent):
    def __init__(self, pings=None):
        if pings is None:
            self.pings = []
        else:
            self.pings = pings
    def add_ping(self, ping):
        self.pings.append(ping)

pong = Pong()
ping = Ping(pong)
pong.add_ping(ping)
```

### Exercício 18.2

Escreva um método Deck chamado `deal_hands` que receba dois parâmetros: o número de mãos e o número de cartas por mão. Ele deve criar o número adequado de objetos Hand, lidar com o número adequado de cartas por mão e retornar uma lista de Hands.

### Exercício 18.3

A seguir, as mãos possíveis no pôquer, em ordem crescente de valor e ordem decrescente de probabilidade:


##### par
&nbsp;&nbsp;&nbsp;&nbsp;Duas cartas com o mesmo valor.

##### dois pares
&nbsp;&nbsp;&nbsp;&nbsp;Dois pares de cartas com o mesmo valor.

##### trinca
&nbsp;&nbsp;&nbsp;&nbsp;Três cartas com o mesmo valor.

##### sequência
&nbsp;&nbsp;&nbsp;&nbsp;Cinco cartas com valores em sequência (os ases podem ser altos ou baixos, então Ace-2-3-4-5 é uma sequência, assim como 10-Jack-Queen-King-Ace, mas Queen-King-Ace-2-3 não é)

##### flush
&nbsp;&nbsp;&nbsp;&nbsp;Cinco cartas com o mesmo naipe.

##### full house
&nbsp;&nbsp;&nbsp;&nbsp;Três cartas com um valor, duas cartas com outro.

##### quadra
&nbsp;&nbsp;&nbsp;&nbsp;Quatro cartas com o mesmo valor.

##### straight flush
&nbsp;&nbsp;&nbsp;&nbsp;Cinco cartas em sequência (como definido acima) e com o mesmo naipe.



A meta desses exercícios é estimar a probabilidade de ter estas várias mãos.

1. Baixe os seguintes arquivos de [http://thinkpython2.com/code:](http://thinkpython2.com/code:)

 * `Card.py`: Versão completa das classes Card, Deck e Hand deste capítulo.

 * `PokerHand.py`: Uma implementação incompleta de uma classe que representa uma mão de pôquer e código para testá-la.

2. Se executar PokerHand.py, você verá que o programa cria mãos de pôquer com 7 cartas e verifica se alguma delas contém um flush. Leia este código com atenção antes de continuar.

3. Acrescente métodos a PokerHand.py chamados `has_pair`, `has_twopair`, etc. que retornem True ou False conforme a mão cumpra os critérios em questão. Seu código deve funcionar corretamente para “mãos” que contenham qualquer número de cartas (embora 5 e 7 sejam as quantidades mais comuns).

4. Escreva um método chamado classify que descubra a classificação do valor mais alto para uma mão e estabeleça o atributo label em questão. Por exemplo, uma mão de 7 cartas poderia conter um flush e um par; ela deve ser marcada como “flush”.

5. Quando se convencer de que os seus métodos de classificação estão funcionando, o próximo passo deve ser estimar as probabilidades de várias mãos. Escreva uma função em PokerHand.py que embaralhe cartas, divida-as em mãos, classifique as mãos e conte o número de vezes em que várias classificações aparecem.

6. Exiba uma tabela das classificações e suas probabilidades. Execute seu programa com números cada vez maiores de mãos até que os valores de saída convirjam a um grau razoável de exatidão. Compare seus resultados com os valores em [http://en.wikipedia.org/wiki/Hand_rankings](http://en.wikipedia.org/wiki/Hand_rankings).

Solução: [http://thinkpython2.com/code/PokerHandSoln.py](http://thinkpython2.com/code/PokerHandSoln.py).
