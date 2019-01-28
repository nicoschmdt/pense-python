## 2.7 - Comentários

Conforme os programas ficam maiores e mais complicados, eles são mais difíceis de ler. As linguagens formais são densas e muitas vezes é difícil ver um pedaço de código e compreender o que ele faz ou por que faz isso.

Por essa razão, é uma boa ideia acrescentar notas aos seus programas para explicar em linguagem natural o que o programa está fazendo. Essas notas são chamadas de [comentários](09-glossario.md#comentários), e começam com o símbolo `#`:


```python
# computa a percentagem da hora que passou
percentage = (minute * 100) / 60
```
Nesse caso, o comentário aparece sozinho em uma linha. Você também pode pôr comentários no fim das linhas:

```python
percentage = (minute * 100) / 60    # percentagem de uma hora
```

Tudo do `#` ao fim da linha é ignorado – não tem efeito na execução do programa.

Os comentários tornam-se mais úteis quando documentam algo no código que não está óbvio. Podemos supor que o leitor compreenda o que o código faz; assim, é mais útil explicar porque faz o que faz.

Este comentário é redundante em relação ao código, além de inútil:

```python
v = 5    # atribui 5 a v
```

Este comentário contém informações úteis que não estão no código:

```python
v = 5    # velocidade em metros/segundo.
```

Bons nomes de variáveis podem reduzir a necessidade de comentários, mas nomes longos podem tornar expressões complexas difíceis de ler, então é preciso analisar o que vale mais a pena.
