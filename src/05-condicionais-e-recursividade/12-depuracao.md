## 5.12 - Depuração

Quando um erro de sintaxe ou de tempo de execução ocorre, a mensagem de erro contém muita informação, às vezes, até demais. As partes mais úteis são normalmente:

* que tipo de erro foi;

* onde ocorreu.

Erros de sintaxe são normalmente fáceis de encontrar, mas há algumas pegadinhas. Erros de whitespace podem ser complicados porque os espaços e tabulações são invisíveis e estamos acostumados a ignorá-los.

```python
>>> x = 5
>>> y = 6
  File "<stdin>", line 1
    y = 6
    ^
IndentationError: unexpected indent
```

Neste exemplo, o problema é que a segunda linha está endentada por um espaço. Mas a mensagem de erro aponta para y, o que pode ser capcioso. Em geral, mensagens de erro indicam onde o problema foi descoberto, mas o erro real pode estar em outra parte do código, às vezes, em uma linha anterior.

O mesmo acontece com erros em tempo de execução. Suponha que você esteja tentando calcular a proporção de sinal a ruído em decibéis. A fórmula é SNRdb = 10 log10 (Psignal/Pnoise). No Python, você poderia escrever algo assim:

```python
import math
signal_power = 9
noise_power = 10
ratio = signal_power // noise_power
decibels = 10 * math.log10(ratio)
print(decibels)
```

Ao executar este programa, você recebe uma exceção:

```python
Traceback (most recent call last):
  File "snr.py", line 5, in ?
    decibels = 10 * math.log10(ratio)
ValueError: math domain error
```

A mensagem de erro indica a linha 5, mas não há nada de errado com esta linha. Uma opção para encontrar o verdadeiro erro é exibir o valor de ratio, que acaba sendo 0. O problema está na linha 4, que usa a [divisão pelo piso](13-glossario.md#divisão-pelo piso) em vez da divisão de ponto flutuante.

É preciso ler as mensagens de erro com atenção, mas não assumir que tudo que dizem esteja correto.
