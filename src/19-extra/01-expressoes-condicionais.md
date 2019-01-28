## 19.1 - Expressões condicionais

Vimos instruções condicionais em “Execução condicional”, na página 78. As instruções condicionais muitas vezes são usadas para escolher um entre dois valores; por exemplo:

```python
if x > 0:
    y = math.log(x)
else:
    y = float('nan')
```

Esta instrução verifica se x é positivo. Nesse caso, ela calcula math.log. Do contrário, math.log causaria um ValueError. Para evitar interromper o programa, geramos um “NaN”, que é um valor de ponto flutuante especial que representa um “Não número”.

Podemos escrever essa instrução de forma mais concisa usando uma [expressão condicional](10-glossario.md#expressão-condicional):

```python
y = math.log(x) if x > 0 else float('nan')
```

Você quase pode ler esta linha como se tivesse sido escrita em inglês: “y recebe log-x se x for maior que 0; do contrário, ele recebe NaN”.

As funções recursivas por vezes podem ser reescritas usando expressões condicionais. Por exemplo, aqui está uma versão recursiva de factorial:

```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)
```

Podemos reescrevê-la assim:

```python
def factorial(n):
    return 1 if n == 0 else n * factorial(n-1)
```
Outro uso de expressões condicionais é lidar com argumentos opcionais. Por exemplo, aqui está o método init de GoodKangaroo (veja o Exercício 17.2):


```python
def __init__(self, name, contents=None):
    self.name = name
    if contents == None:
        contents = []
    self.pouch_contents = contents
```

Podemos reescrevê-lo assim:

```python
def __init__(self, name, contents=None):
    self.name = name
    self.pouch_contents = [] if contents == None else contents
```

Em geral, é possível substituir uma instrução condicional por uma expressão condicional se ambos os ramos contiverem expressões simples que sejam retornadas ou atribuídas à mesma variável.
