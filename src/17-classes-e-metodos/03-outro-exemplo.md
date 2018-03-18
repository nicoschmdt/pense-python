## 17.3 - Outro exemplo

Aqui está uma versão de increment (de “Modificadores”, na página 233) reescrita como método:

```python
# dentro da classe Time:
    def increment(self, seconds):
        seconds += self.time_to_int()
        return int_to_time(seconds)
```

Essa versão assume que `time_to_int` seja escrita como método. Além disso, observe que é uma função pura, não um modificador.

É assim que eu invocaria increment:

```python
>>> start.print_time()
09:45:00
>>> end = start.increment(1337)
>>> end.print_time()
10:07:17
```

O sujeito, start, é atribuído ao primeiro parâmetro, self. O argumento, 1337, é atribuído ao segundo parâmetro, seconds.

Esse mecanismo pode ser confuso, especialmente se você fizer um erro. Por exemplo, se invocar increment com dois argumentos, recebe:

```python
>>> end = start.increment(1337, 460)
TypeError: increment() takes 2 positional arguments but 3 were given
```

A mensagem de erro é inicialmente confusa, porque há só dois argumentos entre parênteses. No entanto, o sujeito também é considerado um argumento, então, somando tudo, são três.

A propósito, um argumento posicional é o que não tem um nome de parâmetro; isto é, não é um argumento de palavra-chave. Nesta chamada da função:

```python
sketch(parrot, cage, dead=True)
```

parrot e cage são posicionais, e dead é um argumento de palavra-chave.
