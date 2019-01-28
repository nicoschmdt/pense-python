## 8.2 - len

len é uma função integrada que devolve o número de caracteres em uma string:


```python
>>> fruit = 'banana'
>>> len(fruit)
6
```

Para obter a última letra de uma string, pode parecer uma boa ideia tentar algo assim:


```python
>>> length = len(fruit)
>>> last = fruit[length]
IndexError: string index out of range
```

A razão de haver um IndexError aqui é que não há nenhuma letra em 'banana' com o [índice](12-glossario.md#índice) 6. Como a contagem inicia no zero, as seis letras são numeradas de 0 a 5. Para obter o último caractere, você deve subtrair 1 de length:


```python
>>> last = fruit[length-1]
>>> last
'a'
```

Ou você pode usar índices negativos, que contam de trás para a frente a partir do fim da string. A expressão fruit[-1] apresenta a última letra, fruit[-2] apresenta a segunda letra de trás para a frente, e assim por diante.
