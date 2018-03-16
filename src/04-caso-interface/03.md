## 4.3 - Exercícios

A seguir, uma série de exercícios usando TurtleWorld. Eles servem para divertir, mas também têm outro objetivo. Enquanto trabalha neles, pense que objetivo pode ser.

As seções seguintes têm as soluções para os exercícios, mas não olhe até que tenha terminado (ou, pelo menos, tentado).

1. Escreva uma função chamada square que receba um parâmetro chamado t, que é um turtle. Ela deve usar o turtle para desenhar um quadrado.

        Escreva uma chamada de função que passe bob como um argumento para o square e então execute o programa novamente.

2. Acrescente outro parâmetro, chamado length, ao square. Altere o corpo para que o comprimento dos lados seja length e então altere a chamada da função para fornecer um segundo argumento. Execute o programa novamente. Teste o seu programa com uma variedade de valores para length.

3. Faça uma cópia do square e mude o nome para polygon. Acrescente outro parâmetro chamado n e altere o corpo para que desenhe um polígono regular de n lados.

        Dica: os ângulos exteriores de um polígono regular de n lados são 360/n graus.

4. Escreva uma função chamada circle que use o turtle, t e um raio r como parâmetros e desenhe um círculo aproximado ao chamar polygon com um comprimento e número de lados adequados. Teste a sua função com uma série de valores de r.

        Dica: descubra a circunferência do círculo e certifique-se de que length \* n = circumference.

5. Faça uma versão mais geral do circle chamada arc, que receba um parâmetro adicional de angle, para determinar qual fração do círculo deve ser desenhada. angle está em unidades de graus, então quando angle=360, o arc deve desenhar um círculo completo.
