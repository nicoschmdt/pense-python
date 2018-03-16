## 4.6 - Projeto da interface

O próximo passo é escrever circle, que recebe um raio r, como parâmetro. Aqui está uma solução simples que usa o polygon para desenhar um polígono de 50 lados:

```python
import math
def circle(t, r):
    circumference = 2 * math.pi * r
    n = 50
    length = circumference / n
    polygon(t, n, length)
```

A primeira linha calcula a circunferência de um círculo com o raio r usando a fórmula 2πr. Já que usamos math.pi, temos que importar math. Por convenção, instruções import normalmente ficam no início do script.

n é o número de segmentos de reta na nossa aproximação de um círculo, então length é o comprimento de cada segmento. Assim, polygon desenha um polígono 50 lados que se aproxima de um círculo com o raio r.

Uma limitação desta solução é que n é uma constante. Para círculos muito grandes, os segmentos de reta são longos demais, e para círculos pequenos, perdemos tempo desenhando segmentos muito pequenos. Uma solução seria generalizar a função tomando n como parâmetro. Isso daria ao usuário (seja quem for que chame circle) mais controle, mas a interface seria menos limpa.

A interface de uma função é um resumo de como ela é usada: Quais são os parâmetros? O que a função faz? E qual é o valor de retorno? Uma interface é “limpa” se permitir à pessoa que a chama fazer o que quiser sem ter que lidar com detalhes desnecessários.

Neste exemplo, r pertence à interface porque especifica o círculo a ser desenhado. n é menos adequado porque pertence aos detalhes de como o círculo deve ser apresentado.

Em vez de poluir a interface, é melhor escolher um valor adequado para n, dependendo da circumference:

```python
def circle(t, r):
    circumference = 2 * math.pi * r
    n = int(circumference / 3) + 1
    length = circumference / n
    polygon(t, n, length)
```

Neste ponto, o número de segmentos é um número inteiro próximo a circumference/3, então o comprimento de cada segmento é aproximadamente 3, pequeno o suficiente para que os círculos fiquem bons, mas grandes o suficiente para serem eficientes e aceitáveis para círculos de qualquer tamanho.

<a id="sec:4.7 - Refatoração"></a>