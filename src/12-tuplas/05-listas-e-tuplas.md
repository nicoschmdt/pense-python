## 12.5 - Listas e tuplas

`zip` é uma função integrada que recebe duas ou mais sequências e devolve uma lista de tuplas onde cada [tupla](09-glossario.md#tupla) contém um elemento de cada sequência. O nome da função tem a ver com o zíper, que se junta e encaixa duas carreiras de dentes.

Este exemplo encaixa uma string e uma lista:

```python
>>> s = 'abc'
>>> t = [0, 1, 2]
>>> zip(s, t)
<zip object at 0x7f7d0a9e7c48>
```

O resultado é um objeto `zip` que sabe como percorrer os pares. O uso mais comum de `zip` é em um loop `for`:

```python
>>> for pair in zip(s, t):
...     print(pair)
...
('a', 0)
('b', 1)
('c', 2)
```

Um objeto `zip` é um tipo de [iterador](09-glossario.md#iterador), ou seja, qualquer objeto que percorre ou itera sobre uma sequência. Iteradores são semelhantes a listas em alguns aspectos, mas, ao contrário de listas, não é possível usar um índice para selecionar um elemento de um iterador.

Se quiser usar operadores e métodos de lista, você pode usar um objeto `zip` para fazer uma lista:

```python
>>> list(zip(s, t))
[('a', 0), ('b', 1), ('c', 2)]
```

O resultado é uma lista de tuplas; neste exemplo, cada tupla contém um caractere da string e o elemento correspondente da lista.

Se as sequências não forem do mesmo comprimento, o resultado tem o comprimento da mais curta:

```python
>>> list(zip('Anne', 'Elk'))
[('A', 'E'), ('n', 'l'), ('n', 'k')]
```

Você pode usar a atribuição de tuplas em um loop for para atravessar uma lista de tuplas:

```python
t = [('a', 0), ('b', 1), ('c', 2)]
for letter, number in t:
    print(number, letter)
```

Cada vez que o programa passa pelo loop, o Python seleciona a próxima tupla na lista e atribui os elementos letter e number. A saída deste loop é:

```python
0 a
1 b
2 c
```

Se combinar `zip`, `for` e atribuição de tuplas, você pode fazer uma expressão útil para percorrer duas (ou mais) sequências ao mesmo tempo. Por exemplo, `has_match` recebe duas sequências, `t1` e `t2` e retorna `True` se houver um índice `i` tal que `t1[i] == t2[i]`:

```python
def has_match(t1, t2):
    for x, y in zip(t1, t2):
        if x == y:
            return True
    return False
```

Se precisar atravessar os elementos de uma sequência e seus índices, você pode usar a função integrada `enumerate`:

```python
for index, element in enumerate('abc'):
    print(index, element)
```

O resultado de `enumerate` é um objeto `enumerate`, que itera sobre uma sequência de pares; cada par contém um índice (começando de 0) e um elemento da sequência dada. Neste exemplo, a saída é

```python
0 a
1 b
2 c
```

De novo.
