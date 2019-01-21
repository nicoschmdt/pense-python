## 18.8 - Diagramas de classe

Por enquanto vimos diagramas de pilha, que mostram o estado de um programa e diagramas de objeto, que mostram os atributos de um objeto e seus valores. Esses diagramas representam um retrato da execução de um programa, então eles mudam no decorrer da execução do programa.

Eles também são altamente detalhados; para alguns objetivos, detalhados demais. Um diagrama de classe é uma representação mais abstrata da estrutura de um programa. Em vez de mostrar objetos individuais, ele mostra classes e as relações entre elas.

Há vários tipos de relações entre as classes:

* Os objetos de uma classe podem conter referências a objetos em outra classe. Por exemplo, cada Rectangle contém uma referência a um Point, e cada Deck contém referências a muitos Cards. Esse tipo de relação chama-se composição. É uma relação do tipo HAS-A (tem um), com a ideia de “um Rectangle tem um Point”.

* Uma classe pode herdar de outra. Esta relação chama-se IS-A (é um), com a ideia de “um Hand é um tipo de Deck”.

* Uma classe pode depender de outra no sentido de que os objetos em uma classe possam receber objetos na segunda classe como parâmetros ou usar esses objetos como parte de um cálculo. Este tipo de relação chama-se dependência.

Um diagrama de classe é uma representação gráfica dessas relações. Por exemplo, a Figura 18.2 mostra as relações entre Card, Deck e Hand.

![Figura 18.2 – Diagrama de classes.](/fig/tnkp_1802.png)
<br>_Figura 18.2 – Diagrama de classes._

A flecha com um triângulo oco representa uma relação IS-A; nesse caso, indica que Hand herda de Deck.

A ponta de flecha padrão representa uma relação HAS-A; nesse caso, um Deck tem referências a objetos Card.

A estrela __*__  perto da ponta de flecha indica a multiplicidade; ela indica quantos Cards um Deck tem. Uma multiplicidade pode ser um número simples como 52, um intervalo como 5..7 ou uma estrela, que indica que um Deck pode ter qualquer número de Cards.

Não há nenhuma dependência neste diagrama. Elas normalmente apareceriam com uma flecha tracejada. Ou, se houver muitas dependências, às vezes elas são omitidas.

Um diagrama mais detalhado poderia mostrar que um Deck na verdade contém uma lista de Cards, mas os tipos integrados como lista e dict não são normalmente incluídos em diagramas de classe.
