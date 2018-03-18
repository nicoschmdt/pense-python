## 4.12 - Exercícios

### Exercício 4.1

Baixe o código deste capítulo no site http://thinkpython2.com/code/polygon.py.

1. Desenhe um diagrama da pilha que mostre o estado do programa enquanto executa circle (bob, radius). Você pode fazer a aritmética à mão ou acrescentar instruções print ao código.

2. A versão de `arc` na seção <a href="#sec:4.7 - Refatoração">4.7 - Refatoração</a> não é muito precisa porque a aproximação linear do círculo está sempre do lado de fora do círculo verdadeiro. Consequentemente, o Turtle acaba ficando alguns píxeis de distância do destino correto. Minha solução mostra um modo de reduzir o efeito deste erro. Leia o código e veja se faz sentido para você. Se desenhar um diagrama, poderá ver como funciona.

### Exercício 4.2

Escreva um conjunto de funções adequadamente geral que possa desenhar flores como as da Figura 4.1.

![Figura 4.1 – Flores de tartaruga.](fig/tnkp_0401.png)
<br>_Figura 4.1 – Flores de tartaruga._

Solução: http://thinkpython2.com/code/flower.py, também exige http://thinkpython2.com/code/polygon.py.

### Exercício 4.3

Escreva um conjunto de funções adequadamente geral que possa desenhar formas como as da Figura 4.2.

![Figura 4.2 – Tortas de tartaruga.](fig/tnkp_0402.png)
<br>_Figura 4.2 – Tortas de tartaruga._

Solução: http://thinkpython2.com/code/pie.py.


### Exercício 4.4

As letras do alfabeto podem ser construídas a partir de um número moderado de elementos básicos, como linhas verticais e horizontais e algumas curvas. Crie um alfabeto que possa ser desenhado com um número mínimo de elementos básicos e então escreva funções que desenhem as letras.

Você deve escrever uma função para cada letra, com os nomes draw\_a, draw\_b etc., e colocar suas funções em um arquivo chamado letters.py. Você pode baixar uma “máquina de escrever de turtle” no site http://thinkpython2.com/code/typewriter.py para ajudar a testar o seu código.

Você pode ver uma solução no site http://thinkpython2.com/code/letters.py; ela também exige http://thinkpython2.com/code/polygon.py.

### Exercício 4.5

Leia sobre espirais em https://pt.wikipedia.org/wiki/Espiral; então escreva um programa que desenhe uma espiral de Arquimedes (ou um dos outros tipos).

[1] _turtle graphics_ ou gráficos de tartaruga é o sistema de desenho popularizado pela linguagem Logo, onde os comandos movimentam um cursor triangular pela tela, conhecido como _turtle_ ou tartaruga. A tartaruga deixa um rastro à medida que é movimentada, e é com esses rastros que se forma um desenho. Diferente dos sistemas usuais de desenho em computação gráfica, o sistema _turtle graphics_ não exige o uso de coordenadas cartesianas.
