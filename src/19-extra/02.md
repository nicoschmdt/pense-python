## 19.2 - Abrangência de listas

Em “Mapeamento, filtragem e redução”, na página 147, vimos os padrões de filtragem e mapeamento. Por exemplo, esta função toma uma lista de strings, mapeia o método de string capitalize aos elementos, e retorna uma nova lista de strings:

```python
def capitalize_all(t):
    res = []
    for s in t:
        res.append(s.capitalize())
    return res
```

Podemos escrever isso de forma mais concisa usando abrangência de listas (list comprehension):

```python
def capitalize_all(t):
    return [s.capitalize() for s in t]
```

Os operadores de colchete indicam que estamos construindo uma nova lista. A expressão dentro dos colchetes especifica os elementos da lista, e a cláusula for indica qual sequência estamos atravessando.

A sintaxe da abrangência de listas é um pouco esquisita porque a variável de loop, s nesse exemplo, aparece na expressão antes de chegarmos à definição.

Abrangências de listas também podem ser usadas para filtragem. Por exemplo, esta função só seleciona os elementos de t que são maiúsculos, e retorna uma nova lista:

```python
def only_upper(t):
    res = []
    for s in t:
        if s.isupper():
            res.append(s)
    return res
```

Podemos reescrevê-la usando abrangência de listas:

```python
def only_upper(t):
    return [s for s in t if s.isupper()]
```

Abrangências de listas são concisas e fáceis de ler, pelo menos para expressões simples. E são normalmente mais rápidas que os loops for equivalentes, às vezes muito mais rápidas. Então, se você ficar irritado comigo por não ter mencionado isso antes, eu entendo.

Porém, em minha defesa, as abrangências de listas são mais difíceis de depurar porque não é possível ter instruções de exibição dentro do loop. Sugiro que você as use só se o cálculo for simples o suficiente para que acerte já de primeira. E para principiantes isso significa nunca.
