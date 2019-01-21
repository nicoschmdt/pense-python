## 5.9 - Diagramas da pilha para funções recursivas

Em “Diagrama da pilha”, na página 55, usamos um diagrama da pilha para representar o estado de um programa durante uma chamada de função. O mesmo tipo de diagrama pode ajudar a interpretar uma função recursiva.

Cada vez que uma função é chamada, o Python cria um frame para conter as variáveis locais e parâmetros da função. Para uma função recursiva, pode haver mais de um frame na pilha ao mesmo tempo.

A Figura 5.1 mostra um diagrama da pilha para `countdown` chamado com n = 3.

![Figura 5.1 – Diagrama da pilha](/fig/tnkp_0501.png).
<br>_Figura 5.1 – Diagrama da pilha._

Como de hábito, o topo da pilha é o frame de `__main__`. Está vazio porque não criamos nenhuma variável em `__main__` nem passamos argumentos a ela.

Os quatro frames do countdown têm valores diferentes para o parâmetro `n`. O fundo da pilha, onde `n = 0`, é chamado caso-base. Ele não faz uma chamada recursiva, então não há mais frames.

Como exercício, desenhe um diagrama da pilha para `print_n` chamado com `s = 'Hello'` e `n = 2`. Então escreva uma função chamada `do_n` que tome um objeto de função e um número `n` como argumentos e que chame a respectiva função `n` vezes.
