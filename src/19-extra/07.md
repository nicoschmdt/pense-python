## 19.7 - defaultdict

O módulo `collections` também tem `defaultdict`, que se parece com um dicionário, exceto pelo fato de que se você acessar uma chave que não existe, um novo valor pode ser gerado automaticamente.

Quando você cria um defaultdict, fornece uma função usada para criar valores. Uma função usada para criar objetos às vezes é chamada de factory (fábrica). As funções integradas que criam listas, conjuntos e outros tipos podem ser usadas como fábricas:

```python
>>> from collections import defaultdict
>>> d = defaultdict(list)
```

Note que o argumento é list, que é um objeto de classe, não list(), que é uma nova lista. A função que você fornece não é chamada a menos que você acesse uma chave que não existe:

```python
>>> t = d['new key']
>>> t
[]
```

A nova lista, que estamos chamando de t, também é adicionada ao dicionário. Então, se alterarmos t, a mudança aparece em d:

```python
>>> t.append('new value')
>>> d
defaultdict(<class 'list'>, {'new key': ['new value']})
```

Se estiver fazendo um dicionário de listas, você pode escrever um código mais simples usando defaultdict. Na minha solução para o Exercício 12.2, que você pode ver em http://thinkpython2.com/code/anagram\_sets.py, faço um dicionário que mapeia uma string organizada de letras a uma lista de palavras que pode ser soletrada com essas letras. Por exemplo, 'opst' mapeia para a lista `['opts', 'post', 'pots', 'spot', 'stop', 'tops']`.

Aqui está o código original:

```python
def all_anagrams(filename):
    d = {}
    for line in open(filename):
        word = line.strip().lower()
        t = signature(word)
        if t not in d:
            d[t] = [word]
        else:
            d[t].append(word)
    return d
```

Isso pode ser simplificado usando setdefault, que você poderia ter usado no Exercício 11.2:

```python
def all_anagrams(filename):
    d = {}
    for line in open(filename):
        word = line.strip().lower()
        t = signature(word)
        d.setdefault(t, []).append(word)
    return d
```

O problema dessa solução é que ela faz uma lista nova a cada vez, mesmo que não seja necessário. Para listas, isso não é grande coisa, mas se a função fábrica for complicada, poderia ser.

Podemos evitar este problema e simplificar o código usando um defaultdict:

```python
def all_anagrams(filename):
    d = defaultdict(list)
    for line in open(filename):
        word = line.strip().lower()
        t = signature(word)
        d[t].append(word)
    return d
```

A minha solução para o Exercício 18.3, que você pode baixar em http://thinkpython2.com/code/PokerHandSoln.py, usa setdefault na função `has_straightflush`. O problema dessa solução é criar um objeto Hand cada vez que passa pelo loop, seja ele necessário ou não. Como exercício, reescreva-a usando um defaultdict.
