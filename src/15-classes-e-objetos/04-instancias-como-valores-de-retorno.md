## 15.4 - Instâncias como valores de retorno

As funções podem retornar instâncias. Por exemplo, `find_center` recebe um `Rectangle` como argumento e devolve um `Point`, que contém as coordenadas do centro do retângulo:

```python
def find_center(rect):
    p = Point()
    p.x = rect.corner.x + rect.width/2
    p.y = rect.corner.y + rect.height/2
    return p
```

Aqui está um exemplo que passa `box` como um argumento para `find_center` e atribui o `ponto` resultante à variável `center`:

```python
>>> center = find_center(box)
>>> print_point(center)
(50, 100)
```
