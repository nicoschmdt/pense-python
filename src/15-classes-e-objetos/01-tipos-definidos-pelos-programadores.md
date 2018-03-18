## 15.1 - Tipos definidos pelos programadores

Já usamos muitos tipos integrados do Python; agora vamos definir um tipo próprio. Como exemplo, criaremos um tipo chamado `Point`, que representa um ponto no espaço bidimensional.

Na notação matemática, os pontos muitas vezes são escritos entre parênteses, com uma vírgula separando as coordenadas. Por exemplo, (0,0) representa a origem e (x, y) representa o ponto que está x unidades à direita e y unidades acima da origem.

Há várias formas para representar pontos no Python:

* Podemos armazenar as coordenadas separadamente em duas variáveis, x e y.

* Podemos armazenar as coordenadas como elementos em uma lista ou tupla.

* Podemos criar um tipo para representar pontos como objetos.

Criar um tipo é mais complicado que outras opções, mas tem vantagens que logo ficarão evidentes.

Um tipo definido pelo programador também é chamado de classe. Uma definição de classe pode ser assim:

```python
class Point:
    """Represents a point in 2-D space."""
```

O cabeçalho indica que a nova classe se chama `Point`. O corpo é uma docstring que explica para que a classe serve. Você pode definir variáveis e métodos dentro de uma definição de classe, mas voltaremos a isso depois.

Definir uma classe denominada `Point` cria um objeto de classe:

```python
>>> Point
<class '__main__.Point'>
```

Como `Point` é definido no nível superior, seu “nome completo” é `__main__.Point`.

O objeto de classe é como uma fábrica para criar objetos. Para criar um `Point`, você chama `Point` como se fosse uma função:


```python
>>> blank = Point()
>>> blank
<__main__.Point object at 0xb7e9d3ac>
```

O valor de retorno é uma referência a um objeto `Point`, ao qual atribuímos blank.

Criar um objeto chama-se instanciação, e o objeto é uma instância da classe.

Quando você exibe uma instância, o Python diz a que classe ela pertence e onde está armazenada na memória (o prefixo o 0x significa que o número seguinte está em formato hexadecimal).

Cada objeto é uma instância de alguma classe, então “objeto” e “instância” são intercambiáveis. Porém, neste capítulo uso “instância” para indicar que estou falando sobre um tipo definido pelo programador.
