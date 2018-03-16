## 3.7 - Parâmetros e argumentos

Algumas funções que vimos exigem argumentos. Por exemplo, ao chamar math.sin, você usa um número como argumento. Algumas funções exigem mais de um argumento: o math.pow exige dois, a base e o expoente.

Dentro da função, os argumentos são atribuídos a variáveis chamadas parâmetros. Aqui está a definição de uma função que precisa de um argumento:


```python
def print_twice(bruce):
    print(bruce)
    print(bruce)
```

Esta função atribui o argumento a um parâmetro chamado bruce. Quando a função é chamada, ela exibe o valor do parâmetro (seja qual for) duas vezes.

Esta função funciona com qualquer valor que possa ser exibido:

```python
>>> print_twice('Spam')
Spam
Spam
>>> print_twice(42)
42
42
>>> print_twice(math.pi)
3.14159265359
3.14159265359
```

As mesmas regras de composição usadas para funções integradas também são aplicadas a funções definidas pelos programadores, então podemos usar qualquer tipo de expressão como argumento para `print_twice`:


```python
>>> print_twice('Spam '*4)
Spam Spam Spam Spam
Spam Spam Spam Spam
>>> print_twice(math.cos(math.pi))
-1.0
-1.0
```

O argumento é avaliado antes de a função ser chamada. Então, nos exemplos, as expressões `'Spam * 4` e `math.cos(math.pi)` só são avaliadas uma vez.


```python
Você também pode usar uma variável como argumento:
>>> michael = 'Eric, the half a bee.'
>>> print_twice(michael)
Eric, the half a bee.
Eric, the half a bee.
```

O nome da variável que passamos como argumento (michael) não tem nada a ver com o nome do parâmetro (bruce). Não importa que o valor tenha sido chamado de volta (em quem chama); aqui em `print_twice`, chamamos todo mundo de bruce.
