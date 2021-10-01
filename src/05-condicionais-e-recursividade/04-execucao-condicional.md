## 5.4 - Execução condicional

Para escrever programas úteis, quase sempre precisamos da capacidade de verificar condições e mudar o comportamento do programa de acordo com elas. Instruções condicionais nos dão esta capacidade. A forma mais simples é a instrução if:

```python
if x > 0:
    print('x is positive')
```

A [expressão booleana](13-glossario.md#expressão-booleana) depois do if é chamada de [condição](13-glossario.md#condição). Se for verdadeira, a instrução endentada é executada. Se não, nada acontece.

Instruções if têm a mesma estrutura que definições de função: um cabeçalho seguido de um corpo indentado. Instruções como essa são chamadas de instruções compostas.

Não há limite para o número de instruções que podem aparecer no corpo, mas deve haver pelo menos uma. Ocasionalmente, é útil ter um corpo sem instruções (normalmente como um espaço reservado para código que ainda não foi escrito). Neste caso, você pode usar a instrução pass, que não faz nada.

```python
if x < 0:
    pass          # A FAZER: lidar com valores negativos!
```
