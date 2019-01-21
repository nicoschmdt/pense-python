## 3.14 - Exercícios

### Exercício 3.1

Escreva uma função chamada right\_justify, que receba uma string chamada s como parâmetro e exiba a string com espaços suficientes à frente para que a última letra da string esteja na coluna 70 da tela:

```python
>>> right_justify('monty')
                                                                       monty
```

Dica: Use concatenação de strings e repetição. Além disso, o Python oferece uma função integrada chamada len, que apresenta o comprimento de uma string, então o valor de `len('monty')` é 5.

### Exercício 3.2

Um objeto de função é um valor que pode ser atribuído a uma variável ou passado como argumento. Por exemplo, do\_twice é uma função que toma um objeto de função como argumento e o chama duas vezes:


```python
def do_twice(f):
    f()
    f()
```

Aqui está um exemplo que usa do\_twice para chamar uma função chamada print\_spam duas vezes:


```python
def print_spam():
    print('spam')
do_twice(print_spam)
```

1. Digite este exemplo em um script e teste-o.

2. Altere `do_twice` para que receba dois argumentos, um objeto de função e um valor, e chame a função duas vezes, passando o valor como um argumento.

3. Copie a definição de `print_twice` que aparece anteriormente neste capítulo no seu script.

4. Use a versão alterada de `do_twice` para chamar `print_twice` duas vezes, passando `'spam'` como um argumento.

5. Defina uma função nova chamada `do_four` que receba um objeto de função e um valor e chame a função quatro vezes, passando o valor como um parâmetro. Deve haver só duas afirmações no corpo desta função, não quatro.

Solução: [http://thinkpython2.com/code/do_four.py](http://thinkpython2.com/code/do_four.py).


### Exercício 3.3

> Nota: Este exercício deve ser feito usando-se apenas as instruções e os outros recursos que aprendemos até agora.

1. Escreva uma função que desenhe uma grade como a seguinte:

```
        + - - - - + - - - - +
        |         |         |
        |         |         |
        |         |         |
        |         |         |
        + - - - - + - - - - +
        |         |         |
        |         |         |
        |         |         |
        |         |         |
        + - - - - + - - - - +
```

> Dica: para exibir mais de um valor em uma linha, podemos usar uma sequência de valores separados por vírgula:
> ```python
> print('+', '-')
> ```
> Por padrão, print avança para a linha seguinte, mas podemos ignorar esse comportamento e inserir um espaço no fim, desta forma:
> ```python
> print('+', end=' ')
>  print('-')
>  ```
> A saída dessas instruções é `+ -`.
> Uma instrução `print` sem argumento termina a linha atual e vai para a próxima linha.

2. Escreva uma função que desenhe uma grade semelhante com quatro linhas e quatro colunas.

Solução: [http://thinkpython2.com/code/grid.py](http://thinkpython2.com/code/grid.py). Crédito: Este exercício é baseado em outro apresentado por Oualline, em Practical C Programming, Third Edition, O’Reilly Media, 1997.
