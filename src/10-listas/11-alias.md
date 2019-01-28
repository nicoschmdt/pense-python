## 10.11 - Alias

Se a se refere a um [objeto](14-glossario.md#objeto) e você atribui b = a, então ambas as variáveis se referem ao mesmo objeto.

```python
>>> a = [1, 2, 3]
>>> b = a
>>> b is a
True
```
O diagrama de estado ficará igual à Figura 10.4.

![Figura 10.4 – Diagrama de estado com duas variáveis associadas à mesma [lista](14-glossario.md#lista)](/fig/tnkp_1004.png).
<br>_Figura 10.4 – Diagrama de estado com duas variáveis associadas à mesma lista._

A associação de uma variável com um objeto é chamada de [referência](14-glossario.md#referência). Neste exemplo, há duas referências ao mesmo objeto.

Um objeto com mais de uma referência tem mais de um nome, então dizemos que o objeto tem um [alias](14-glossario.md#alias).

Se o objeto com alias é mutável, alterações feitas em um alias afetam o outro também.


```python
>>> b[0] = 42
>>> a
[42, 2, 3]
```

Apesar de esse comportamento poder ser útil, ele é passível de erros. Em geral, é mais seguro evitar usar alias ao trabalhar com objetos mutáveis.

Para objetos imutáveis como strings, usar alias não é um problema tão grande. Neste exemplo:

```python
a = 'banana'
b = 'banana'
```

Quase nunca faz diferença se a e b se referem à mesma string ou não.
