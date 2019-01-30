## 2.8 - Depuração

Há três tipos de erros que podem ocorrer em um programa: erros de sintaxe, erros de tempo de execução e erros semânticos. É útil distinguir entre eles para rastreá-los mais rapidamente.

<dl>
<dt>Erro de sintaxe</dt>
<dd>A “sintaxe” refere-se à estrutura de um programa e suas respectivas regras. Por exemplo, os parênteses devem vir em pares correspondentes, então (1 + 2) é legal, mas 8) é um [erro de sintaxe](09-glossario.md#erro-de-sintaxe).</dd>
<dd>Se houver um erro de sintaxe em algum lugar no seu programa, o Python exibe uma mensagem de erro e para, e não será possível [executar](09-glossario.md#executar) o programa. Nas primeiras poucas semanas da sua carreira em programação, você pode passar muito tempo rastreando erros de sintaxe. Ao adquirir experiência, você fará menos erros e os encontrará mais rápido.</dd>

<dt>Erro de tempo de execução</dt>
<dd>O segundo tipo de erro é o erro de tempo de execução, assim chamado porque o erro não aparece até que o programa seja executado. Esses erros também se chamam de exceções porque normalmente indicam que algo excepcional (e ruim) aconteceu.</dd>
<dd>Os erros de tempo de execução são raros nos programas simples que veremos nos primeiros capítulos, então pode demorar um pouco até você encontrar algum.</dd>

<dt>Erro semântico</dt>
<dd>O terceiro tipo do erro é “semântico”, ou seja, relacionado ao significado. Se houver um [erro semântico](09-glossario.md#erro-semântico) no seu programa, ele será executado sem gerar mensagens de erro, mas não vai fazer a coisa certa. Vai fazer algo diferente. Especificamente, vai fazer o que você disser para fazer.</dd>
<dd>Identificar erros semânticos pode ser complicado, porque é preciso trabalhar de trás para a frente, vendo a saída do programa e tentando compreender o que ele está fazendo.</dd>
</dl>
