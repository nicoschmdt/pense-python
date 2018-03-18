## 11.7 - Variáveis globais

No exemplo anterior, known é criada fora da função, então pertence ao frame especial chamado `__main__`. As variáveis em `__main__` às vezes são chamadas de globais, porque podem ser acessadas de qualquer função. Em contraste com as variáveis locais, que desaparecem quando sua função termina, as variáveis globais persistem de uma chamada da função à seguinte.

É comum usar variáveis globais para `flags`; isto é, variáveis booleanas que indicam (“flag”) se uma condição é verdadeira. Por exemplo, alguns programas usam um `flag` denominado verbose para controlar o nível de detalhe da saída:

```python
verbose = True
def example1():
    if verbose:
        print('Running example1')
```

Se tentar reatribuir uma variável global, você pode se surpreender. O próximo exemplo mostra como acompanhar se a função foi chamada:

```python
been_called = False
def example2():
    been_called = True        # ERRADO
```

Porém, se executá-la, você verá que o valor de `been_called` não se altera. O problema é que `example2` cria uma nova variável local chamada `been_called`. A variável local some quando a função termina e não tem efeito sobre a variável global.

Para reatribuir uma variável global dentro de uma função é preciso declarar a variável como global antes de usá-la:

```python
been_called = False
def example2():
    global been_called
    been_called = True
```

A instrução `global` diz ao interpretador algo como “Nesta função, quando digo `been_called`, estou falando da variável global; não crie uma local”.

Aqui está um exemplo que tenta atualizar uma variável global:

```python
count = 0
def example3():
    count = count + 1        # ERRADO
```

Se executá-la, você recebe:

```python
UnboundLocalError: local variable 'count' referenced before assignment
```

O Python supõe que `count` seja local, e dentro desta suposição, a variável está sendo lida antes de ser escrita. A solução, mais uma vez, é declarar `count` como global:

```python
def example3():
    global count
    count += 1
```

Se uma variável global se referir a um valor mutável, você pode alterar o valor sem declarar a variável:

```python
known = {0:0, 1:1}
def example4():
    known[2] = 1
```

Então você pode adicionar, retirar e substituir elementos de uma lista global ou dicionário, mas se quiser reatribuir a variável, precisa declará-la:

```python
def example5():
    global known
    known = dict()
```

As variáveis globais podem ser úteis, mas se você tiver muitas delas e alterá-las com frequência, isso poderá dificultar a depuração do programa.
