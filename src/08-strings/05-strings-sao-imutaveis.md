## 8.5 - Strings são imutáveis

É tentador usar o operador `[]` no lado esquerdo de uma atribuição, com a intenção de alterar um caractere em uma string. Por exemplo:

```python
>>> greeting = 'Hello, world!'
>>> greeting[0] = 'J'
TypeError: 'str' object does not support item assignment
```

O “objeto” neste caso é a string e o “item” é o caractere que você tentou atribuir. Por enquanto, um objeto é a mesma coisa que um valor, mas refinaremos esta definição mais adiante ([Objetos e valores](<a href="10-listas.md#sec:10.10"), no capítulo 10).

A razão do erro é que as strings são imutáveis, o que significa que você não pode alterar uma string existente. O melhor que você pode fazer é criar uma string que seja uma variação da original:

```python
>>> greeting = 'Hello, world!'
>>> new_greeting = 'J' + greeting[1:]
>>> new_greeting
'Jello, world!'
```

Esse exemplo concatena uma nova primeira letra a uma fatia de `greeting`. Não tem efeito sobre a string original.
