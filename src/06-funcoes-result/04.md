## 6.4 - Funções booleanas

As funções podem retornar booleans, o que pode ser conveniente para esconder testes complicados dentro de funções. Por exemplo:

```python
def is_divisible(x, y):
    if x % y == 0:
        return True
    else:
        return False
```

É comum dar nomes de funções booleanas que pareçam perguntas de sim ou não; is\_divisible retorna True ou False para indicar se x é divisível por y.

Aqui está um exemplo:

```python
>>> is_divisible(6, 4)
False
>>> is_divisible(6, 3)
True
```

O resultado do operador == é um booleano, então podemos escrever a função de forma mais concisa, retornando-o diretamente:

```python
def is_divisible(x, y):
    return x % y == 0
```

As funções booleanas muitas vezes são usadas em instruções condicionais:

```python
if is_divisible(x, y):
    print('x is divisible by y')
```

Pode ser tentador escrever algo assim:

```python
if is_divisible(x, y) == True:
    print('x is divisible by y')
```

Mas a comparação extra é desnecessária.

Como um exercício, escreva uma função `is_between(x, y, z)` que retorne True, se x ≤ y ≤ z, ou False, se não for o caso.
