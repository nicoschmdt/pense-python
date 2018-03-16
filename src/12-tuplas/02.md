## 12.2 - Atribuição de tuplas

Muitas vezes, é útil trocar os valores de duas variáveis. Com a atribuição convencional, é preciso usar uma variável temporária. Por exemplo, trocar a e b.

```python
>>> temp = a
>>> a = b
>>> b = temp
```

Essa solução é trabalhosa; a atribuição de tuplas é mais elegante:

```python
>>> a, b = b, a
```

O lado esquerdo é uma tupla de variáveis; o lado direito é uma tupla de expressões. Cada valor é atribuído à sua respectiva variável. Todas as expressões no lado direito são avaliadas antes de todas as atribuições.

O número de variáveis à esquerda e o número de valores à direita precisam ser iguais:

```python
>>> a, b = 1, 2, 3
ValueError: too many values to unpack
```

De forma geral, o lado direito pode ter qualquer tipo de sequência (string, lista ou tupla). Por exemplo, para dividir um endereço de email em um nome de usuário e um domínio, você poderia escrever:

```python
>>> addr = 'monty@python.org'
>>> uname, domain = addr.split('@')
```

O valor de retorno do `split` é uma lista com dois elementos; o primeiro elemento é atribuído a `uname`, o segundo a `domain`:

```python
>>> uname
'monty'
>>> domain
'python.org'
```
