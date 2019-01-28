## 10.7 - Mapeamento, [filtragem](14-glossario.md#filtragem) e [redução](14-glossario.md#redução)

Para somar o total de todos os números em uma [lista](14-glossario.md#lista), você pode usar um loop como esse:

```python
def add_all(t):
    total = 0
    for x in t:
        total += x
    return total
```

`total` é inicializado com 0. Cada vez que o programa passa pelo loop, `x` recebe um [elemento](14-glossario.md#elemento) da lista. O operador `+=` oferece uma forma curta de atualizar uma variável. Esta instrução de [atribuição aumentada](14-glossario.md#atribuição-aumentada),

```python
total += x
```
é [equivalente](14-glossario.md#equivalente) a

```python
total = total + x
```
No decorrer da execução do loop, `total` acumula a soma dos elementos; uma variável usada desta forma às vezes é chamada de [acumuladora](14-glossario.md#acumuladora).

Somar todos elementos de uma lista é uma operação tão comum que o Python a oferece como uma função integrada, `sum`:

```python
>>> t = [1, 2, 3]
>>> sum(t)
6
```

Uma operação como essa, que combina uma sequência de elementos em um único valor, às vezes é chamada de redução.

Algumas vezes você quer percorrer uma lista enquanto cria outra. Por exemplo, a função seguinte recebe uma lista de strings e retorna uma nova lista que contém strings com letras maiúsculas:

```python
def capitalize_all(t):
    res = []
    for s in t:
        res.append(s.capitalize())
    return res
```

`res` é inicializado com uma lista vazia; cada vez que o programa passa pelo loop, acrescentamos o próximo elemento. Então `res` é outro tipo de acumulador.

Uma operação como `capitalize_all` às vezes é chamada de [mapeamento](14-glossario.md#mapeamento) porque ela “mapeia” uma função (nesse caso o método `capitalize`) sobre cada um dos elementos em uma sequência.

Outra operação comum é selecionar alguns dos elementos de uma lista e retornar uma sublista. Por exemplo, a função seguinte recebe uma lista de strings e retorna uma lista que contém apenas strings em letra maiúscula:

```python
def only_upper(t):
    res = []
    for s in t:
        if s.isupper():
            res.append(s)
    return res
```

`isupper` é um método de string que retorna True se a string contiver apenas letras maiúsculas.

Uma operação como `only_upper` é chamada de filtragem porque filtra alguns dos elementos e desconsidera outros.

As operações de lista mais comuns podem ser expressas como uma combinação de mapeamento, filtragem e redução.
