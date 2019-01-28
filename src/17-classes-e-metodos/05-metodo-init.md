## 17.5 - Método init

O [método](12-glossario.md#método) `__init__` (abreviação da palavra em inglês para “inicialização”) é um método especial, invocado quando um objeto é instanciado. Seu nome completo é `__init__` (dois caracteres de sublinhado, seguidos de init, e mais dois sublinhados). Um método `__init__` da classe Time pode ser algo assim:

```python
# dentro da classe Time:

    def __init__(self, hour=0, minute=0, second=0):
        self.hour = hour
        self.minute = minute
        self.second = second
```

É comum que os parâmetros de `__init__` tenham os mesmos nomes que os atributos. A instrução

```python
        self.hour = hour
```

guarda o valor do parâmetro `hour` como um atributo de `self`.

Os parâmetros são opcionais, então, se você chamar Time sem argumentos, recebe os valores padrão:

```python
>>> time = Time()
>>> time.print_time()
00:00:00
```

Se incluir um argumento, ele define hour.

```python
>>> time = Time (9)
>>> time.print_time()
09:00:00
```

Se fornecer dois argumentos, hour e minute serão definidos:

```python
>>> time = Time(9, 45)
>>> time.print_time()
09:45:00
```

E se você fornecer três argumentos, os três valores serão definidos.

Como exercício, escreva um método init da classe Point que receba x e y como parâmetros opcionais e os relacione aos atributos correspondentes.
