## 4.7 - Refatoração

Quando escrevi circle, pude reutilizar polygon porque um polígono de muitos lados é uma boa aproximação de um círculo. Mas o arc não é tão cooperativo; não podemos usar polygon ou circle para desenhar um arco.

Uma alternativa é começar com uma cópia de polygon e transformá-la em arc. O resultado poderia ser algo assim:

```python
def arc(t, r, angle):
    arc_length = 2 * math.pi * r * angle / 360
    n = int(arc_length / 3) + 1
    step_length = arc_length / n
    step_angle = angle / n
    for i in range(n):
        t.fd(step_length)
        t.lt(step_angle)
```

A segunda metade desta função parece com a do polygon, mas não é possível reutilizar o polygon sem mudar a [interface](11-glossario.md#interface). Poderíamos generalizar polygon para receber um ângulo como um terceiro argumento, mas então polygon não seria mais um nome adequado! Em vez disso, vamos chamar a função mais geral de polyline:

```python
def polyline(t, n, length, angle):
    for i in range(n):
        t.fd(length)
        t.lt(angle)
```

Agora podemos reescrever polygon e arc para usar polyline:

```python
def polygon(t, n, length):
    angle = 360.0 / n
    polyline(t, n, length, angle)
def arc(t, r, angle):
    arc_length = 2 * math.pi * r * angle / 360
    n = int(arc_length / 3) + 1
    step_length = arc_length / n
    step_angle = float(angle) / n
    polyline(t, n, step_length, step_angle)
```

Finalmente, podemos reescrever circle para usar arc:

```python
def circle(t, r):
    arc(t, r, 360)
```

Este processo – recompor um programa para melhorar interfaces e facilitar a reutilização do código – é chamado de [refatoração](11-glossario.md#refatoração). Neste caso, notamos que houve código semelhante em arc e polygon, então nós o “fatoramos” no polyline.

Se tivéssemos planejado, poderíamos ter escrito polyline primeiro e evitado a refatoração, mas muitas vezes não sabemos o suficiente já no início de um projeto para projetar todas as interfaces. Quando começarmos a escrever código, entenderemos melhor o problema. Às vezes, a refatoração é um sinal de que aprendemos algo.
