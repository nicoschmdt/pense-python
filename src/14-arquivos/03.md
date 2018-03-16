## 14.3 - Operador de formatação

O argumento de `write` tem que ser uma string, então, se quisermos inserir outros valores em um arquivo, precisamos convertê-los em strings. O modo mais fácil de fazer isso é com `str`:

```python
>>> x = 52
>>> fout.write(str(x))
```

Uma alternativa é usar o operador de formatação, `%`. Quando aplicado a números inteiros, `%` é o operador de módulo. No entanto, quando o primeiro operando é uma string, `%` é o operador de formatação.

O primeiro operando é a string de formatação, que contém uma ou várias sequências de formatação que especificam como o segundo operando deve ser formatado. O resultado é uma string.

Por exemplo, a sequência de formatação '%d' significa que o segundo operando deve ser formatado como um número inteiro decimal:

```python
>>> camels = 42
>>> '%d' % camels
'42'
```

O resultado é a string `'42'`, que não deve ser confundida com o valor inteiro `42`.

Uma sequência de formatação pode aparecer em qualquer lugar na string, então você pode embutir um valor em uma sentença:

```python
>>> 'I have spotted %d camels.' % camels
'I have spotted 42 camels.'
```

Se houver mais de uma sequência de formatação na string, o segundo argumento tem que ser uma tupla. Cada sequência de formatação é combinada com um elemento da tupla, nesta ordem.

O seguinte exemplo usa `'%d'` para formatar um número inteiro, `'%g'` para formatar um número de ponto flutuante e `'%s'` para formatar qualquer objeto como uma string:

```python
>>> 'In %d years I have spotted %g %s.' % (3, 0.1, 'camels')
'In 3 years I have spotted 0.1 camels.'
```

O número de elementos na tupla tem de corresponder ao número de sequências de formatação na string. Além disso, os tipos dos elementos têm de corresponder às sequências de formatação:

```python
>>> '%d %d %d' % (1, 2)
TypeError: not enough arguments for format string
>>> '%d' % 'dollars'
TypeError: %d format: a number is required, not str
```

No primeiro exemplo não há elementos suficientes; no segundo, o elemento é do tipo incorreto.

Para obter mais informações sobre o operador de formato, veja https://docs.python.org/3/library/stdtypes.html#printf-style-string-formatting. Você pode ler sobre uma alternativa mais eficiente, o método de formatação de strings, em https://docs.python.org/3/library/stdtypes.html#str.format.
