## 6.8 - Verificação de tipos

O que acontece se chamarmos factorial e usarmos 1.5 como argumento?

```python
>>> factorial(1.5)
RuntimeError: Maximum recursion depth exceeded
```

Parece uma recursividade infinita. No entanto, por que isso acontece? A função tem um caso-base – quando n == 0. Mas se n não é um número inteiro, podemos perder o caso-base e recorrer para sempre.

Na primeira chamada recursiva, o valor de n é 0.5. No seguinte, é -0.5. Daí, torna-se menor (mais negativo), mas nunca será 0.

Temos duas escolhas. Podemos tentar generalizar a função factorial para trabalhar com números de ponto flutuante, ou podemos fazer factorial controlar o tipo de argumento que recebe. A primeira opção chama-se função gamma e está um pouco além do alcance deste livro. Então usaremos a segunda opção.

Podemos usar a função integrada isinstance para verificar o tipo de argumento. E vamos aproveitar para verificar também se o argumento é positivo:

```python
def factorial (n):
    if not isinstance(n, int):
        print('Factorial is only defined for integers.')
        return None
    elif n < 0:
        print('Factorial is not defined for negative integers.')
        return None
    elif n == 0:
        return 1
    else:
        return n * factorial(n-1)
```

O primeiro caso-base lida com números não inteiros; o segundo, com números inteiros negativos. Em ambos os casos o programa exibe uma mensagem de erro e retorna None para indicar que algo deu errado:

```python
>>> factorial('fred')
Factorial is only defined for integers.
None
>>> factorial(-2)
Factorial is not defined for negative integers.
None
```

Se passarmos por ambas as verificações, sabemos que n é positivo ou zero, então podemos comprovar que a recursividade termina.

Esse programa demonstra um padrão às vezes chamado de [guardião](10-glossario.md#guardião). As duas primeiras condicionais atuam como guardiãs, protegendo o código que segue de valores que poderiam causar um erro. As guardiãs permitem comprovar a correção do código.

Na “Busca reversa”, na página 165, veremos uma alternativa mais flexível para a exibição de uma mensagem de erro: o levantamento de exceções.
