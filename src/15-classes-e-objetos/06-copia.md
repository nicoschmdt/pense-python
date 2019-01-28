## 15.6 - Cópia

Alias podem tornar um programa difícil de ler porque as alterações em um lugar podem ter efeitos inesperados em outro lugar. É difícil monitorar todas as variáveis que podem referir-se a um dado objeto.

Em vez de usar alias, copiar o objeto pode ser uma alternativa. O módulo `copy` contém uma função chamada `copy` que pode duplicar qualquer objeto:

```python
>>> p1 = Point()
>>> p1.x = 3.0
>>> p1.y = 4.0
>>> import copy
>>> p2 = copy.copy(p1)
```

`p1` e `p2` contêm os mesmos dados, mas não são o mesmo `Point`:

```python
>>> print_point(p1)
(3, 4)
>>> print_point(p2)
(3, 4)
>>> p1 is p2
False
>>> p1 == p2
False
```

O operador `is` indica que `p1` e `p2` não são o mesmo objeto, que é o que esperamos. Porém, você poderia ter esperado que `==` fosse apresentado como `True`, porque esses pontos contêm os mesmos dados. Nesse caso, pode ficar desapontado ao saber que, para instâncias, o comportamento padrão do operador `==` é o mesmo que o do operador `is`; ele verifica a identidade dos objetos, não a sua equivalência. Isso acontece porque, para tipos definidos pelo programador, o Python não sabe o que deve ser considerado equivalente. Pelo menos, ainda não.

Se você usar `copy.copy` para duplicar um retângulo, descobrirá que ele copia o objeto `Rectangle`, mas não o `Point` embutido nele:

```python
>>> box2 = copy.copy(box)
>>> box2 is box
False
>>> box2.corner is box.corner
True
```

A Figura 15.3 mostra como fica o [diagrama de objeto](08-glossario.md#diagrama-de objeto). Esta operação chama-se [cópia superficial](08-glossario.md#cópia-superficial) porque copia o objeto e qualquer referência que contenha, mas não os objetos integrados.

![Figura 15.3 – Diagrama: dois objetos Rectangle compartilhando o mesmo Point](/fig/tnkp_1503.png).
<br>_Figura 15.3 – Diagrama: dois objetos_ `Rectangle` _compartilhando o mesmo_ `Point`.

Para a maior parte das aplicações, não é isso que você quer. Nesse exemplo, invocar `grow_rectangle` em um dos Rectangles não afetaria o outro, mas invocar `move_rectangle` em qualquer um deles afetaria a ambos! Esse comportamento é confuso e propenso a erros.

Felizmente, o módulo `copy` oferece um método chamado `deepcopy` que copia não só o objeto, mas também os objetos aos quais ele se refere, e os objetos aos quais estes se referem, e assim por diante. Você não se surpreenderá ao descobrir que esta operação se chama [cópia profunda](08-glossario.md#cópia-profunda).

```python
>>> box3 = copy.deepcopy(box)
>>> box3 is box
False
>>> box3.corner is box.corner
False
box3 e box são objetos completamente separados.
```

Como exercício, escreva uma versão de `move_rectangle` que cria e retorne um novo retângulo em vez de alterar o antigo.
