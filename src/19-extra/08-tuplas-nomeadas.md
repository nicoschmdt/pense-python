## 19.8 - Tuplas nomeadas

Muitos objetos simples são basicamente coleções de valores relacionados. Por exemplo, o objeto Point, definido no Capítulo 15, contém dois números, x e y. Ao definir uma classe como essa, normalmente você começa com um método init e um método str:

```python
class Point:
    def __init__(self, x=0, y=0):
        self.x = x
        self.y = y
    def __str__(self):
        return '(%g, %g)' % (self.x, self.y)
```

É muito código para transmitir pouca informação. O Python tem uma forma mais concisa de dizer a mesma coisa:

```python
from collections import namedtuple
Point = namedtuple('Point', ['x', 'y'])
```

O primeiro argumento é o nome da classe que você quer criar. O segundo é uma lista dos atributos que o objeto Point deve ter, como strings. O valor de retorno de namedtuple é um objeto de classe:

```python
>>> Point
<class '__main__.Point'>
```

Point fornece automaticamente métodos como `__init__` e `__str__` então não é preciso escrevê-los.

Para criar um objeto Point, você usa a classe Point como uma função:

```python
>>> p = Point(1, 2)
>>> p
Point(x=1, y=2)
```

O método `__init__` atribui os argumentos a atributos usando os nomes que você forneceu. O método `__str__` exibe uma representação do objeto Point e seus atributos.

Você pode acessar os elementos da tupla nomeada pelo nome:

```python
>>> p.x, p.y
(1, 2)
```

Mas também pode tratar uma tupla nomeada como uma tupla:

```python
>>> p[0], p[1]
(1, 2)
>>> x, y = p
>>> x, y
(1, 2)
```

Tuplas nomeadas fornecem uma forma rápida de definir classes simples. O problema é que classes simples não ficam sempre simples. Mais adiante você poderá decidir que quer acrescentar métodos a uma tupla nomeada. Nesse caso, você poderá definir uma nova classe que herde da tupla nomeada:

```python
class Pointier(Point):
    # adicionar mais métodos aqui
```

Ou poderá mudar para uma definição de classe convencional.
