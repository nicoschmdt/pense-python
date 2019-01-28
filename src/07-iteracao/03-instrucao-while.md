## 7.3 - Instrução while

Os computadores muitas vezes são usados para automatizar tarefas repetitivas. A repetição de tarefas idênticas ou semelhantes sem fazer erros é algo que os computadores fazem bem e as pessoas não. Em um programa de computador, a repetição também é chamada de [iteração](08-glossario.md#iteração).

Já vimos duas funções, `countdown` e `print_n`, que se repetem usando recursividade. Como a iteração é bem comum, o Python fornece recursos de linguagem para facilitá-la. Um deles é a instrução `for` que vimos em “Repetição simples”, na página 65. Voltaremos a isso mais adiante.

Outra é a instrução `while`. Aqui está uma versão de countdown que usa a instrução `while`:

```python
def countdown(n):
    while n > 0:
        print(n)
        n = n - 1
    print('Blastoff!')
```

Você até pode ler a instrução `while` como se fosse uma tradução do inglês. Significa “Enquanto `n` for maior que 0, mostre o valor de `n` e então decremente `n`. Quando chegar a 0, mostre a palavra Blastoff!”

Mais formalmente, aqui está o fluxo de execução para uma instrução while:

1. Determine se a condição é verdadeira ou falsa.

2. Se for falsa, saia da instrução while e continue a execução da próxima instrução.

3. Se a condição for verdadeira, execute o corpo e então volte ao passo 1.

Este tipo de fluxo chama-se loop (laço), porque o terceiro passo faz um loop de volta ao topo.

O corpo do loop deve mudar o valor de uma ou mais variáveis para que, a certa altura, a condição fique falsa e o loop termine. Senão o loop vai se repetir para sempre, o que é chamado de [loop infinito](08-glossario.md#loop-infinito). Uma fonte infindável de divertimento para cientistas da computação é a observação das instruções no xampu, “Faça espuma, enxágue, repita”, que são parte de um loop infinito.

No caso de countdown, podemos provar que o loop termina: se `n` for zero ou negativo, o loop nunca é executado. Senão, `n` fica cada vez menor ao passar pelo loop, até eventualmente chegar a 0.

Para alguns outros loops, não é tão fácil perceber isso. Por exemplo:

```python
def sequence(n):
    while n != 1:
        print(n)
        if n % 2 == 0:        # n é par
            n = n / 2
        else:                 # n é ímpar
            n = n * 3 + 1
```

A condição deste loop é `n != 1`, então o loop continuará até que `n` seja 1, o que torna a condição falsa.

Cada vez que passa pelo loop, o programa produz o valor de `n` e então verifica se é par ou ímpar. Se for par, `n` é dividido por 2. Se for ímpar, o valor de `n` é substituído por `n * 3 + 1`. Por exemplo, se o argumento passado a sequence for 3, os valores resultantes de `n` são 3, 10, 5, 16, 8, 4, 2, 1.

Como `n` às vezes aumenta e às vezes diminui, não há nenhuma prova óbvia de que `n` chegará eventualmente a 1, ou que o programa terminará. Para alguns valores de `n`, podemos provar o término. Por exemplo, se o valor inicial for uma potência de dois, `n` será par cada vez que passar pelo loop até que chegue a 1. O exemplo anterior termina com uma sequência assim, que inicia com 16.

A questão difícil é se podemos provar que este programa termina para todos os valores positivos de `n`. Por enquanto, ninguém foi capaz de comprovar ou refutar isso! (Veja [http://en.wikipedia.org/wiki/Collatz\_conjecture](http://en.wikipedia.org/wiki/Collatz\_conjecture).)

Como um exercício, reescreva a função print\_n de “Recursividade”, na página 81, usando a iteração em vez da recursividade.
