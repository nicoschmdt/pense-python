## 3.1 - Chamada de [função](13-glossario.md#função)

Já vimos um exemplo de [chamada de função](13-glossario.md#chamada-de função):

```python
>>> type(42)
<class 'int'>
```

O nome da função é type. A expressão entre parênteses é chamada de [argumento](13-glossario.md#argumento) da função. Para esta função, o resultado é o tipo do argumento.

É comum dizer que uma função “recebe” um argumento e “retorna” um resultado. O resultado também é chamado de [valor de retorno](13-glossario.md#valor-de retorno).

O Python oferece funções que convertem valores de um tipo em outro. A função int recebe qualquer valor e o converte em um número inteiro, se for possível, ou declara que há um erro:


```python
>>> int('32')
32
>>> int('Hello')
ValueError: invalid literal for int(): Hello
```

`int` pode converter valores de ponto flutuante em números inteiros, mas não faz arredondamentos; ela apenas corta a parte da fração:


```python
>>> int(3.99999)
3
>>> int(-2.3)
-2
```

`float` converte números inteiros e strings em números de ponto flutuante:


```python
>>> float(32)
32.0
>>> float('3.14159')
3.14159
```

Finalmente, `str` converte o argumento em uma string:


```python
>>> str(32)
'32'
>>> str(3.14159)
'3.14159'
```
