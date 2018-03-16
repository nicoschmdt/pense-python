## 5.2 - Expressões booleanas

Uma expressão booleana é uma expressão que pode ser verdadeira ou falsa. Os exemplos seguintes usam o operador ==, que compara dois operandos e produz True se forem iguais e False se não forem:

```python
>>> 5 == 5
True
>>> 5 == 6
False
```

True e False são valores especiais que pertencem ao tipo bool; não são strings:

```python
>>> type(True)
<class 'bool'>
>>> type(False)
<class 'bool'>
```

O operador == é um dos operadores relacionais; os outros são:

```python
x != y                # x não é igual a y
x > y                 # x é maior que y
x < y                 # x é menor que y
x >= y                # x é maior ou igual a y
x <= y                # x é menor ou igual a y
```

Embora essas operações provavelmente sejam familiares para você, os símbolos do Python são diferentes dos símbolos matemáticos. Um erro comum é usar apenas um sinal de igual (=) em vez de um sinal duplo (==). Lembre-se de que = é um operador de atribuição e == é um operador relacional. Não existe =&lt; ou =&gt;.
