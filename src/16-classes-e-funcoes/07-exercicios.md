## 16.7 - Exercícios

Os exemplos de código deste capítulo estão disponíveis em [http://thinkpython2.com/code/Time1.py](http://thinkpython2.com/code/Time1.py); as soluções para os exercícios estão disponíveis em [http://thinkpython2.com/code/Time1_soln.py](http://thinkpython2.com/code/Time1_soln.py).

### Exercício 16.1

Escreva uma função chamada `mul_time` que receba um objeto `Time` e um número e retorne um novo objeto `Time` que contenha o produto do `Time` original e do número.

Então use `mul_time` para escrever uma função que receba um objeto `Time` representando o tempo até o fim de uma corrida e um número que represente a distância, e retorne um objeto `Time` com o passo médio (tempo por milha).

### Exercício 16.2

O módulo `datetime` fornece objetos `time` que são semelhantes aos objetos `Time` deste capítulo, mas ele oferece um grande conjunto de métodos e operadores. Leia a documentação em [http://docs.python.org/3/library/datetime.html](http://docs.python.org/3/library/datetime.html).

1. Use o módulo `datetime` para escrever um programa que receba a data atual e exiba o dia da semana.

2. Escreva um programa que receba um aniversário como entrada e exiba a idade do usuário e o número de dias, horas, minutos e segundos até o seu próximo aniversário.

3. Para duas pessoas nascidas em dias diferentes, há um dia em que a idade de uma equivale a duas vezes a da outra. Este é o Dia Duplo delas. Escreva um programa que receba dois aniversários e calcule o Dia Duplo dos aniversariantes.

4. Para um desafio um pouco maior, escreva a versão mais geral que calcule o dia em que uma pessoa é N vezes mais velha que a outra.
