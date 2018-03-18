## 6.9 - Depuração

Quebrar um grande programa em funções menores cria controles naturais da depuração. Se uma função não estiver funcionando, há três possibilidades a considerar:

* Há algo errado com os argumentos que a função está recebendo; uma precondição está sendo violada.

* Há algo errado com a função; uma pós-condição foi violada.

* Há algo errado com o valor de retorno ou a forma na qual está sendo usado.

Para excluir a primeira possibilidade, você pode acrescentar uma instrução print no início da função e exibir os valores dos parâmetros (e talvez os seus tipos). Ou escrever código que verifique as precondições explicitamente.

Se os parâmetros parecerem bons, acrescente uma instrução print antes de cada instrução return e exiba o valor de retorno. Se possível, verifique o resultado à mão. Uma possibilidade é chamar a função com valores facilitem a verificação do resultado (como no “Desenvolvimento incremental”, da página 94).

Se a função parecer funcionar, veja a chamada da função para ter certeza de que o valor de retorno está sendo usado corretamente (ou se está sendo usado mesmo!).

Acrescentar instruções de exibição no começo e no fim de uma função pode ajudar a tornar o fluxo de execução mais visível. Por exemplo, aqui está uma versão de factorial com instruções de exibição:

```python
def factorial(n):
    space = ' ' * (4 * n)
    print(space, 'factorial', n)
    if n == 0:
        print(space, 'returning 1')
        return 1
    else:
        recurse = factorial(n-1)
        result = n * recurse
        print(space, 'returning', result)
        return result
```

space é uma string de caracteres especiais que controla a endentação da saída. Aqui está o resultado de factorial(4):

```
                factorial 4
            factorial 3
        factorial 2
    factorial 1
factorial 0
returning 1
    returning 1
        returning 2
            returning 6
                returning 24
```

Se o fluxo de execução parecer confuso a você, este tipo de saída pode ser útil. Leva um tempo para desenvolver um scaffolding eficaz, mas um pouco dele pode economizar muita depuração.
