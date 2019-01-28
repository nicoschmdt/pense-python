## 10.3 - Percorrendo uma [lista](14-glossario.md#lista)

A forma mais comum de percorrer os elementos em uma lista é com um loop for. A sintaxe é a mesma que a das strings:

```python
for cheese in cheeses:
    print(cheese)
```

Isso funciona bem se você precisa apenas ler os elementos da lista. Mas se você quer escrever ou atualizar os elementos, você precisa dos índices. Uma forma comum de fazer isso é combinar as funções integradas range e len:

```python
for i in range(len(numbers)):
    numbers[i] = numbers[i] * 2
```

Este loop percorre a lista e atualiza cada [elemento](14-glossario.md#elemento). len retorna o número de elementos na lista. range retorna uma lista de índices de 0 a n-1, em que n é o comprimento da lista. Cada vez que passa pelo loop, i recebe o índice do próximo elemento. A instrução de atribuição no corpo usa i para ler o valor antigo do elemento e atribuir o novo valor.

Um loop for que passe por uma lista vazia nunca executa o corpo:

```python
for x in []:
    print('This never happens.')
```

Apesar de uma lista poder conter outra lista, a [lista aninhada](14-glossario.md#lista-aninhada) ainda conta como um único elemento. O comprimento desta lista é quatro:

```python
['spam', 1, ['Brie', 'Roquefort', 'Pol le Veq'], [1, 2, 3]]
```
