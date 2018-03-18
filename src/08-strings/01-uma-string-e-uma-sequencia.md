## 8.1 - Uma string é uma sequência

Uma string é uma sequência de caracteres. Você pode acessar um caractere de cada vez com o operador de colchete:

```python
>>> fruit = 'banana'
>>> letter = fruit[1]
```

A segunda instrução seleciona o caractere número 1 de fruit e o atribui a letter.

A expressão entre colchetes chama-se índice. O índice aponta qual caractere da sequência você quer (daí o nome).


```python
Mas pode ser que você não obtenha o que espera:
>>> letter
'a'
```

Para a maior parte das pessoas, a primeira letra de 'banana' é b, não a. Mas para os cientistas da computação, o índice é uma referência do começo da string, e a referência da primeira letra é zero.


```python
>>> letter = fruit[0]
>>> letter
'b'
```

Então b é a 0ª (“zerésima”) letra de 'banana', a é a 1ª (primeira) letra e n é a 2ª (segunda) letra.

Você pode usar uma expressão que contenha variáveis e operadores como índice:



```python
>>> i = 1
>>> fruit[i]
'a'
>>> fruit[i+1]
'n'
```

Porém, o valor do índice tem que ser um número inteiro. Se não for, é isso que aparece:

```python
>>> letter = fruit[1.5]
TypeError: string indices must be integers
```
