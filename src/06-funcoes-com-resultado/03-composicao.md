## 6.3 - Composição

Como você já deveria esperar a essa altura, é possível chamar uma função de dentro de outra. Como exemplo, escreveremos uma função que recebe dois pontos, o centro do círculo e um ponto no perímetro, para calcular a área do círculo.

Suponha que o ponto do centro seja guardado nas variáveis xc e yc e o ponto de perímetro está em xp e yp. O primeiro passo deve ser encontrar o raio do círculo, que é a distância entre os dois pontos. Acabamos de escrever uma função, distance, que faz isto:

```python
radius = distance(xc, yc, xp, yp)
```

O próximo passo deve ser encontrar a área de um círculo com aquele raio; acabamos de escrever isso também:

```python
result = area(radius)
```

Encapsulando esses passos em uma função, temos:

```python
def circle_area(xc, yc, xp, yp):
    radius = distance(xc, yc, xp, yp)
    result = area(radius)
    return result
```

As variáveis temporárias radius e result são úteis para desenvolvimento e depuração, e uma vez que o programa esteja funcionando podemos torná-lo mais conciso compondo chamadas de função:

```python
def circle_area(xc, yc, xp, yp):
    return area(distance(xc, yc, xp, yp))
```
