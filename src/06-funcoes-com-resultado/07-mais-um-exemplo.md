## 6.7 - Mais um exemplo

Depois do factorial, o exemplo mais comum de uma função matemática definida recursivamente é fibonacci, que tem a seguinte definição (ver http://en.wikipedia.org/wiki/Fibonacci_number):

```
fibonacci(0) = 0
fibonacci(1) = 1
fibonacci(n) = fibonacci(n − 1) + fibonacci(n − 2)
```

Traduzida para Python, ela fica assim:

```python
def fibonacci (n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n-1) + fibonacci(n-2)
```

Se tentar seguir o fluxo de execução aqui, até para valores razoavelmente pequenos de n, sua cabeça explode. Porém, seguindo o salto de fé, supondo que as duas chamadas recursivas funcionem corretamente, então é claro que vai receber o resultado correto adicionando-as juntas.
