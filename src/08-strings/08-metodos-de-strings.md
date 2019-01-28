## 8.8 - Métodos de strings

As strings oferecem métodos que executam várias operações úteis. Um método é semelhante a uma função – toma argumentos e devolve um valor –, mas a sintaxe é diferente. Por exemplo, o método upper recebe uma string e devolve uma nova string com todas as letras maiúsculas.

Em vez da sintaxe de função `upper(word)`, ela usa a sintaxe de método `word.upper()`:

```python
>>> word = 'banana'
>>> new_word = word.upper()
>>> new_word
'BANANA'
```

Esta forma de notação de ponto especifica o nome do método, `upper` e o nome da string, `word`, à qual o método será aplicado. Os parênteses vazios indicam que este método não toma nenhum argumento.

Uma chamada de método denomina-se [invocação](12-glossario.md#invocação); neste caso, diríamos que estamos invocando `upper` em `word`.

E, na verdade, há um método de string denominado `find`, que é notavelmente semelhante à função que escrevemos:

```python
>>> word = 'banana'
>>> index = word.find('a')
>>> index
1
```

Neste exemplo, invocamos `find` em `word` e passamos a letra que estamos procurando como um parâmetro.

Na verdade, o método `find` é mais geral que a nossa função; ele pode encontrar substrings, não apenas caracteres:

```python
>>> word.find('na')
2
```

Por padrão, `find` inicia no começo da string, mas pode receber um segundo argumento, o [índice](12-glossario.md#índice) onde deve começar:

```python
>>> word.find('na', 3)
4
```

Este é um exemplo de um [argumento opcional](12-glossario.md#argumento-opcional). `find` também pode receber um terceiro argumento, o índice para onde deve parar:

```python
>>> name = 'bob'
>>> name.find('b', 1, 2)
-1
```

Esta [busca](12-glossario.md#busca) falha porque `'b'` não aparece no intervalo do índice de 1 a 2, não incluindo 2. Fazer buscas até (mas não incluindo) o segundo índice torna `find` similar ao operador de fatiamento.
