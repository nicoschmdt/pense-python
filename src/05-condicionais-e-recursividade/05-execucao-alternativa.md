## 5.5 - Execução alternativa

Uma segunda forma da instrução if é a “execução alternativa”, na qual há duas possibilidades e a [condição](13-glossario.md#condição) determina qual será executada. A sintaxe pode ser algo assim:

```python
if x % 2 == 0:
    print('x is even')
else:
    print('x is odd')
```

Se o resto quando x for dividido por 2 for 0, então sabemos que x é par e o programa exibe uma mensagem adequada. Se a condição for falsa, o segundo conjunto de instruções é executado. Como a condição deve ser verdadeira ou falsa, exatamente uma das alternativas será executada. As alternativas são chamadas de ramos (branches), porque são ramos no fluxo da execução.
