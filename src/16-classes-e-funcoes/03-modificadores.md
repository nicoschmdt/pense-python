## 16.3 - Modificadores

Às vezes é útil uma função alterar os objetos que recebe como parâmetros. Nesse caso, as mudanças são visíveis a quem chama a função. As funções que fazem isso chamam-se modificadores.

`increment`, que acrescenta um dado número de segundos a um objeto `Time`, pode ser escrita naturalmente como um [modificador](06-glossario.md#modificador). Aqui está um primeiro esboço:

```python
def increment(time, seconds):
    time.second += seconds
    if time.second >= 60:
        time.second -= 60
        time.minute += 1
    if time.minute >= 60:
        time.minute -= 60
        time.hour += 1
```

A primeira linha executa a operação básica; o resto lida com os casos especiais que vimos antes.

Esta função está correta? O que acontece se `second` for muito mais que 60?

Neste caso não basta transportar uma vez, temos que continuar fazendo isso até que time.second seja menos de 60. Uma solução é substituir a instrução `if` pela instrução `while`. Isso tornaria a função correta, mas não muito eficiente. Como exercício, escreva uma versão correta de `increment` que não contenha loops.

O que se faz com modificadores também pode ser feito com funções puras. Na verdade, algumas linguagens de programação só permitem funções puras. Há evidências de que os programas que usam funções puras são mais rápidos para serem desenvolvidos e menos propensos a erros que programas que usam modificadores. No entanto, modificadores são convenientes de vez em quando, e os programas funcionais tendem a ser menos eficientes.

De forma geral, recomendo que você escreva funções puras sempre que achar razoável e recorra a modificadores só se houver alguma vantagem clara. Esta abordagem pode ser chamada de __programação funcional__.

Como exercício, escreva uma versão “pura” de increment que cria e retorna um objeto `Time` em vez de alterar o parâmetro.
