## 5.11 - Entrada de teclado

Os programas que escrevemos até agora não aceitam entradas do usuário. Eles sempre fazem a mesma coisa cada vez.

O Python fornece uma função integrada chamada `input` que interrompe o programa e espera que o usuário digite algo. Quando o usuário pressionar Return ou Enter, o programa volta a ser executado e input retorna o que o usuário digitou como uma string. No Python 2, a mesma função é chamada `raw_input`.

```python
>>> text = input()
What are you waiting for?
>>> text
What are you waiting for?
```

Antes de receber entradas do usuário, é uma boa ideia exibir um prompt dizendo ao usuário o que ele deve digitar. input pode ter um prompt como argumento:

```python
>>> name = input('What...is your name?\\n')
What...is your name?
Arthur, King of the Britons!
>>> name
Arthur, King of the Britons!
```

A sequência `\n` no final do prompt representa um newline, que é um caractere especial de quebra de linha. É por isso que a entrada do usuário aparece abaixo do prompt.

Se esperar que o usuário digite um número inteiro, você pode tentar converter o valor de retorno para int:

```python
>>> prompt = 'What...is the airspeed velocity of an unladen swallow?\\n'
>>> speed = input(prompt)
What...is the airspeed velocity of an unladen swallow?
42
>>> int(speed)
42
```

Mas se o usuário digitar algo além de uma série de dígitos, você recebe um erro:

```python
>>> speed = input(prompt)
What...is the airspeed velocity of an unladen swallow?
What do you mean, an African or a European swallow?
>>> int(speed)
ValueError: invalid literal for int() with base 10
```

Veremos como tratar este tipo de erro mais adiante.
