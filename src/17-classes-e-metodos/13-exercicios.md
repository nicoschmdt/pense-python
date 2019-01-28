## 17.13 - Exercícios

### Exercício 17.1

Baixe o código deste capítulo em [http://thinkpython2.com/code/Time2.py](http://thinkpython2.com/code/Time2.py). Altere os atributos de Time para que um número inteiro único represente os segundos decorridos desde a meia-noite. Então altere os métodos (e a função int\_to\_time) para funcionar com a nova implementação. Você não deve modificar o código de teste em main. Ao terminar, a saída deve ser a mesma que antes.

Solução: [http://thinkpython2.com/code/Time2_soln.py](http://thinkpython2.com/code/Time2_soln.py).

### Exercício 17.2

Este exercício é uma história com moral sobre um dos erros mais comuns e difíceis de encontrar no Python. Escreva uma definição de classe chamada Kangaroo com os seguintes métodos:

1. Um [método](12-glossario.md#método) `__init__` que inicialize um atributo chamado `pouch_contents`  em uma lista vazia.

2. Um método chamado `put_in_pouch` que receba um objeto de qualquer tipo e o acrescente a `pouch_contents`.

3. Um método `__str__` que retorne uma representação de string do objeto Kangaroo e os conteúdos de pouch (bolsa).

Teste o seu código criando dois objetos Kangaroo, atribuindo-os a variáveis chamadas kanga e roo, e então acrescentando roo ao conteúdo da bolsa de kanga.

Baixe [http://thinkpython2.com/code/BadKangaroo.py](http://thinkpython2.com/code/BadKangaroo.py). Ele contém uma solução para o problema anterior com um defeito bem grande e bem feio. Encontre e corrija o defeito.

Se não conseguir achar a solução, você pode baixar [http://thinkpython2.com/code/GoodKangaroo.py](http://thinkpython2.com/code/GoodKangaroo.py), que explica o problema e demonstra uma solução.
