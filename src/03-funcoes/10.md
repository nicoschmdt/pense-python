## 3.10 - Funções com resultado e funções nulas

Algumas funções que usamos, como as funções matemáticas, devolvem resultados; por falta de um nome melhor, vou chamá-las de funções com resultados. Outras funções, como print\_twice, executam uma ação, mas não devolvem um valor. Elas são chamadas de funções nulas.

Quando você chama uma função com resultado, quase sempre quer fazer algo com o resultado; por exemplo, você pode atribui-lo a uma variável ou usá-la como parte de uma expressão:

```python
x = math.cos(radians)
golden = (math.sqrt(5) + 1) / 2
```

Quando você chama uma função no modo interativo, o Python exibe o resultado:

```python
>>> math.sqrt(5)
2.2360679774997898
```

Mas em um script, se você chamar uma função com resultado e mais nada, o valor de retorno é perdido para sempre!

```python
math.sqrt(5)
```

Este script calcula a raiz quadrada de 5, mas como não armazena ou exibe o resultado, não é muito útil.

As funções nulas podem exibir algo na tela ou ter algum outro efeito, mas não têm um valor de retorno. Se você atribuir o resultado a uma variável, recebe um valor especial chamado None:

```python
>>> result = print_twice('Bing')
Bing
Bing
>>> print(result)
None
```

O valor `None` não é o mesmo que a string `'None'`. É um valor especial que tem seu próprio tipo:

```python
>>> print(type(None))
<class 'NoneType'>
```

As funções que apresentamos por enquanto são todas nulas. Vamos apresentar funções com resultado mais adiante.
