## 12.6 - Dicionários e tuplas

Os dicionários têm um método chamado `items` que devolve uma sequência de tuplas, onde cada [tupla](09-glossario.md#tupla) é um par chave-valor:

```python
>>> d = {'a':0, 'b':1, 'c':2}
>>> t = d.items()
>>> t
dict_items([('c', 2), ('a', 0), ('b', 1)])
```

O resultado é um objeto `dict_items`, que é um [iterador](09-glossario.md#iterador) que percorre os pares chave-valor. Você pode usá-lo em um loop `for`, desta forma:

```python
>>> for key, value in d.items():
...     print(key, value)
...
c 2
a 0
b 1
```

Como se poderia esperar de um dicionário, os itens não estão em nenhuma ordem em particular.

Indo em outra direção, você pode usar uma lista de tuplas para inicializar um novo dicionário:

```python
>>> t = [('a', 0), ('c', 2), ('b', 1)]
>>> d = dict(t)
>>> d
{'a': 0, 'c': 2, 'b': 1}
```

Combinar `dict` com `zip` produz uma forma concisa de criar um dicionário:


```python
>>> d = dict(zip('abc', range(3)))
>>> d
{'a': 0, 'c': 2, 'b': 1}
```

O método de dicionário `update` também recebe uma lista de tuplas e as adiciona, como pares chave-valor, a um dicionário existente.

É comum usar tuplas como chaves em dicionários (principalmente porque você não pode usar listas). Por exemplo, uma lista telefônica poderia mapear pares de sobrenome e primeiro nome a números de telefone. Supondo que tenhamos definido last, first e number, podemos escrever:

```python
directory[last, first] = number
```

A expressão entre chaves é uma tupla. Podemos usar atribuição de tuplas para atravessar este dicionário:

```python
for last, first in directory:
    print(first, last, directory[last,first])
```

Este loop atravessa as chaves em directory, que são tuplas. Ele atribui os elementos de cada tupla para `last` e `first`, e então exibe o nome e número de telefone correspondente.

Há duas formas de representar tuplas em um diagrama de estado. A versão mais detalhada mostra os índices e elementos como aparecem em uma lista. Por exemplo, a tupla ('Cleese', 'John') apareceria como na Figura 12.1.

![Figura 12.1 – Diagrama de estado de uma tupla](/fig/tnkp_1201.png).
<br>_Figura 12.1 – Diagrama de estado de uma tupla._

No entanto, em um diagrama maior, você pode querer omitir os detalhes. Por exemplo, um diagrama da lista telefônica poderia ser como o da Figura 12.2.


![Figura 12.2 – Diagrama de estado de um dicionário com chaves do tipo tupla](/fig/tnkp_1202.png).
<br>_Figura 12.2 – Diagrama de estado de um dicionário com chaves do tipo tupla._

Aqui as tuplas são mostradas usando a sintaxe do Python para simplificar o gráfico. O número de telefone no diagrama é a linha de reclamações da BBC, então, por favor, não ligue para lá.
