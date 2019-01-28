## 11.1 - Um [dicionário](09-glossario.md#dicionário) é um [mapeamento](09-glossario.md#mapeamento)

Um dicionário se parece com uma lista, mas é mais geral. Em uma lista, os índices têm que ser números inteiros; em um dicionário, eles podem ser de (quase) qualquer tipo.

Um dicionário contém uma coleção de índices, que se chamam chaves e uma coleção de valores. Cada [chave](09-glossario.md#chave) é associada com um único [valor](09-glossario.md#valor). A associação de uma chave e um valor chama-se [par chave-valor](09-glossario.md#par-chave-valor) ou [item](09-glossario.md#item).

Em linguagem matemática, um dicionário representa um mapeamento de chaves a valores, para que você possa dizer que cada chave “mostra o mapa a” um valor. Como exemplo, vamos construir um dicionário que faz o mapa de palavras do inglês ao espanhol, portanto as chaves e os valores são todos strings.

A função dict cria um novo dicionário sem itens. Como dict é o nome de uma função integrada, você deve evitar usá-lo como nome de variável.


```python
>>> eng2sp = dict()
>>> eng2sp
{}
```

As chaves {} representam um dicionário vazio. Para acrescentar itens ao dicionário, você pode usar colchetes:

```python
>>> eng2sp['one'] = 'uno'
```

Esta linha cria um item que mapeia da chave 'one' ao valor 'uno'. Se imprimirmos o dicionário novamente, vemos um par chave-valor com dois pontos entre a chave e o valor:

```python
>>> eng2sp
{'one': 'uno'}
```

Este formato de saída também é um formato de entrada. Por exemplo, você pode criar um dicionário com três itens:

```python
>>> eng2sp = {'one': 'uno', 'two': 'dos', 'three': 'tres'}
```

Porém, se exibir `eng2sp`, pode se surpreender:

```python
>>> eng2sp
{'one': 'uno', 'three': 'tres', 'two': 'dos'}
```

A ordem dos pares chave-valor pode não ser a mesma. Se você digitar o mesmo exemplo no seu computador, pode receber um resultado diferente. Em geral, a ordem dos itens em um dicionário é imprevisível.

No entanto, isso não é um problema porque os elementos de um dicionário nunca são indexados com índices de números inteiros. Em vez disso, você usa as chaves para procurar os valores correspondentes:

```python
>>> eng2sp['two']
'dos'
```

A chave `'two'` sempre mapeia ao valor `'dos'`, assim a ordem dos itens não importa.

Se a chave não estiver no dicionário, você recebe uma exceção:

```python
>>> eng2sp['four']
KeyError: 'four'
```

A função `len` é compatível com dicionários; ela devolve o número de pares chave-valor:

```python
>>> len(eng2sp)
3
```

O operador `in` funciona em dicionários também; ele acusa se algo aparece como chave no dicionário (aparecer como valor não é o suficiente).

```python
>>> 'one' in eng2sp
True
>>> 'uno' in eng2sp
False
```

Para ver se algo aparece como um valor em um dicionário, você pode usar o método `values`, que devolve uma coleção de valores, e então usar o operador `in`:

```python
>>> vals = eng2sp.values()
>>> 'uno' in vals
True
```

O operador `in` usa algoritmos diferentes para listas e dicionários. Para listas, ele procura os elementos da lista em ordem, como descrito em “Busca”, na página 123. Conforme a lista torna-se mais longa, o tempo de [busca](09-glossario.md#busca) também fica proporcionalmente mais longo.

Para dicionários, o Python usa um algoritmo chamado [hashtable](09-glossario.md#hashtable) (tabela de dispersão), que tem uma propriedade notável: o operador `in` leva praticamente o mesmo tempo na busca, não importa quantos itens estejam no dicionário. Eu explico como isso é possível em “Hashtables”, na página 302, mas a explicação pode não fazer sentido até que você tenha lido mais alguns capítulos.
