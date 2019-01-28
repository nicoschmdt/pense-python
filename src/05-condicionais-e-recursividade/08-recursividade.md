## 5.8 - Recursividade

É legal para uma função chamar outra; também é legal para uma função chamar a si própria. Pode não ser óbvio porque isso é uma coisa boa, mas na verdade é uma das coisas mais mágicas que um programa pode fazer. Por exemplo, veja a seguinte função:



```python
def countdown(n):
    if n <= 0:
        print('Blastoff!')
    else:
        print(n)
        countdown(n-1)
```

Se n for 0 ou negativo, a palavra “Blastoff!” é exibida, senão a saída é n e então a função countdown é chamada – por si mesma – passando n-1 como argumento.

O que acontece se chamarmos esta função assim?

```python
>>> countdown(3)
```

A execução de countdown inicia com n=3 e como n é maior que 0, ela produz o valor 3 e então chama a si mesma...

&nbsp;&nbsp;&nbsp;&nbsp;A execução de countdown inicia com n=2 e como n é maior que 0, ela produz o valor 2 e então chama a si mesma...

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A execução de countdown inicia com n=1 e como n é maior que 0, ela produz o valor 1 e então chama a si mesma...

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A execução de countdown inicia com n=0 e como n não é maior que 0, ela produz a palavra “Blastoff!” e então retorna.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;O countdown que recebeu n=1 retorna.

&nbsp;&nbsp;&nbsp;&nbsp;O countdown que recebeu n=2 retorna.

O countdown que recebeu n=3 retorna.

E então você está de volta ao `__main__`. Então a saída completa será assim:


```python
3
2
1
Blastoff!
```

Uma função que chama a si mesma é dita recursiva; o processo para executá-la é a [recursividade](13-glossario.md#recursividade).

Como em outro exemplo, podemos escrever uma função que exiba uma string n vezes:

```python
def print_n(s, n):
    if n <= 0:
        return
    print(s)
    print_n(s, n-1)
```

Se `n <= 0` a instrução `return` causa a saída da função. O fluxo de execução volta imediatamente a quem fez a chamada, e as linhas restantes da função não são executadas.

O resto da função é similar à countdown: ela mostra s e então chama a si mesma para mostrar s mais n-1 vezes. Então o número de linhas da saída é 1 + (n - 1), até chegar a n.

Para exemplos simples como esse, provavelmente é mais fácil usar um loop for. Mais adiante veremos exemplos que são difíceis de escrever com um loop for e fáceis de escrever com recursividade, então é bom começar cedo.
