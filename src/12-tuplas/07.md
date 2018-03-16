## 12.7 - Sequências de sequências

Eu me concentrei em listas de tuplas, mas quase todos os exemplos neste capítulo também funcionam com listas de listas, tuplas de tuplas e tuplas de listas. Para evitar enumerar as combinações possíveis, às vezes é mais fácil falar sobre sequências de sequências.

Em muitos contextos, os tipos diferentes de sequências (strings, listas e tuplas) podem ser usados de forma intercambiável. Então, como escolher uma em vez da outra?

Para começar com o óbvio, as strings são mais limitadas que outras sequências porque os elementos têm de ser caracteres. Também são imutáveis. Se precisar da capacidade de alterar caracteres em uma string (em vez de criar outra string) você pode querer usar uma lista de caracteres.

As listas são mais comuns que as tuplas, principalmente porque são mutáveis. Mas há alguns casos em que você pode preferir tuplas:

1. Em alguns contextos, como em uma instrução `return`, é sintaticamente mais simples criar uma tupla que uma lista.

2. Se quiser usar uma sequência como uma chave de dicionário, é preciso usar um tipo imutável como uma tupla ou string.

3. Se estiver passando uma sequência como um argumento a uma função, usar tuplas reduz o potencial de comportamento inesperado devido a alias.

Como tuplas são imutáveis, elas não fornecem métodos como `sort` e `reverse`, que alteram listas existentes. Porém, o Python fornece a função integrada `sorted`, que recebe qualquer sequência e retorna uma nova lista com os mesmos elementos ordenados, e `reversed`, que recebe uma sequência e retorna um iterador que percorre a lista em ordem reversa.
