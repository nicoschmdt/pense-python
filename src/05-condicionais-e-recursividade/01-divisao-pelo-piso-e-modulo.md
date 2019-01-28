## 5.1 - Divisão pelo piso e módulo

O operador de [divisão pelo piso](13-glossario.md#divisão-pelo piso), //, divide dois números e arredonda o resultado para um número inteiro para baixo. Por exemplo, suponha que o tempo de execução de um filme seja de 105 minutos. Você pode querer saber a quanto isso corresponde em horas. A divisão convencional devolve um número de ponto flutuante:


```python
>>> minutes = 105
>>> minutes / 60
1.75
```

Mas não é comum escrever horas com pontos decimais. A divisão pelo piso devolve o número inteiro de horas, ignorando a parte fracionária:


```python
>>> minutes = 105
>>> hours = minutes // 60
>>> hours
1
```

Para obter o resto, você pode subtrair uma hora em minutos:


```python
>>> remainder = minutes - hours * 60
>>> remainder
45
```

Uma alternativa é usar o [operador módulo](13-glossario.md#operador-módulo), %, que divide dois números e devolve o resto:


```python
>>> remainder = minutes % 60
>>> remainder
45
```

O operador módulo é mais útil do que parece. Por exemplo, é possível verificar se um número é divisível por outro – se x % y for zero, então x é divisível por y.

Além disso, você pode extrair o dígito ou dígitos mais à direita de um número. Por exemplo, x % 10 produz o dígito mais à direita de x (na base 10). Da mesma forma x % 100 produz os dois últimos dígitos.

Se estiver usando o Python 2, a divisão funciona de forma diferente. O operador de divisão, /, executa a divisão pelo piso se ambos os operandos forem números inteiros e faz a divisão de ponto flutuante se pelo menos um dos operandos for do tipo float.
