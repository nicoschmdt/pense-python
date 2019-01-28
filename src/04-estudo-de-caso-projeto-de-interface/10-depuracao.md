## 4.10 - Depuração

Uma [interface](11-glossario.md#interface) é como um contrato entre uma função e quem a chama. Quem chama concorda em fornecer certos parâmetros e a função concorda em fazer certa ação.

Por exemplo, polyline precisa de quatro argumentos: t tem que ser um Turtle; n tem que ser um número inteiro; length deve ser um número positivo; e o angle tem que ser um número, que se espera estar em graus.

Essas exigências são chamadas de precondições porque se supõe que sejam verdade antes que a função seja executada. De forma inversa, as condições no fim da função são pós-condições. As pós-condições incluem o efeito desejado da função (como o desenho de segmentos de reta) e qualquer efeito colateral (como mover o Turtle ou fazer outras mudanças).

Precondições são responsabilidade de quem chama. Se quem chama violar uma [precondição](11-glossario.md#precondição) (adequadamente documentada!) e a função não funcionar corretamente, o problema está nesta pessoa, não na função.

Se as precondições forem satisfeitas e as pós-condições não forem, o problema está na função. Se as suas precondições e pós-condições forem claras, elas podem ajudar na depuração.
