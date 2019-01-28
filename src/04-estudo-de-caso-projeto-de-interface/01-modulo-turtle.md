## 4.1 - Módulo turtle

Para conferir se você tem o módulo turtle, abra o interpretador do Python e digite:

```python
>>> import turtle
>>> bob = turtle.Turtle()
```

Ao executar este código o programa deve abrir uma nova janela com uma pequena flecha que representa o turtle. Feche a janela.

Crie um arquivo chamado mypolygon.py e digite o seguinte código:

```python
import turtle
bob = turtle.Turtle()
print(bob)
turtle.mainloop()
```

O módulo turtle (com t minúsculo) apresenta uma função chamada Turtle (com T maiúsculo), que cria um objeto Turtle, ao qual atribuímos uma variável chamada bob. Exibir bob faz algo assim:

```python
<turtle.Turtle object at 0xb7bfbf4c>
```

Isto significa que bob se refere a um objeto com o tipo Turtle definido no módulo turtle.

mainloop diz que a janela deve esperar que o usuário faça algo, embora neste caso não haja muito a fazer, exceto fechar a janela.

Uma vez que tenha criado o Turtle, você pode chamar um [método](11-glossario.md#método) para movê-lo pela janela. Método é semelhante a uma função, mas usa uma sintaxe ligeiramente diferente. Por exemplo, para mover o turtle para a frente:

```python
bob.fd(100)
```

O método fd é associado com o objeto turtle, que denominamos bob. Chamar de um método é como fazer um pedido: você está pedindo que bob avance.

O argumento de fd é uma distância em píxeis, então o tamanho real depende da sua tela.

Outros métodos que você pode chamar em um Turtle são bk para mover-se para trás, lt para virar à esquerda e rt para virar à direita. O argumento para lt e rt é um ângulo em graus.

Além disso, cada Turtle segura uma caneta, que está abaixada ou levantada; se a caneta estiver abaixada, o Turtle deixa um rastro quando se move. Os métodos pu e pd representam “caneta para cima” e “caneta para baixo”.

Para desenhar um ângulo reto, acrescente estas linhas ao programa (depois de criar bob e antes de chamar o mainloop):


```python
bob.fd(100)
bob.lt(90)
bob.fd(100)
```

Ao executar este programa, você deveria ver bob mover-se para o leste e depois para o norte, deixando dois segmentos de reta para trás.

Agora altere o programa para desenhar um quadrado. Só siga adiante neste capítulo se ele funcionar adequadamente!
