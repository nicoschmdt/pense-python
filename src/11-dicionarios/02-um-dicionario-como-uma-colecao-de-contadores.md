## 11.2 - Um dicionário como uma coleção de contadores

Suponha que você receba uma string e queira contar quantas vezes cada letra aparece nela. Há vários modos de fazer isso:

1. Você pode criar 26 variáveis, uma para cada letra do alfabeto. Então pode atravessar a string e, para cada caractere, incrementar o contador correspondente, provavelmente usando uma condicional encadeada.

2. Você pode criar uma lista com 26 elementos. Então pode converter cada caractere em um número (com a função integrada ord), usar o número como índice na lista e incrementar o respectivo contador.

3. Você pode criar um dicionário com caracteres como chaves e contadores como valores correspondentes. Na primeira vez que visse um caractere, você acrescentaria um item ao dicionário. Depois disso, incrementaria o valor de um item existente.

Cada uma dessas opções executa o mesmo cálculo, mas o implementa de forma diferente.

Uma implementação é um modo de executar um cálculo; algumas implementações são melhores que outras. Por exemplo, uma vantagem da implementação de dicionários é que não precisamos saber de antemão quais letras aparecem na string e só é preciso criar espaço para as letras que realmente venham a aparecer.

O código poderia ser assim:

```python
def histogram(s):
    d = dict()
    for c in s:
        if c not in d:
            d[c] = 1
        else:
            d[c] += 1
    return d
```

O nome da função é `histogram`, um termo estatístico para uma coleção de contadores (ou frequências).

A primeira linha da função cria um dicionário vazio. O loop for atravessa a string. Cada vez que passa pelo loop, se o caractere c não estiver no dicionário, criamos um item com a chave c e o valor inicial 1 (pois já vimos esta letra uma vez). Se o c já estiver no dicionário, incrementamos d [c].

Funciona assim:

```python
>>> h = histogram('brontosaurus')
>>> h
{'a': 1, 'b': 1, 'o': 2, 'n': 1, 's': 2, 'r': 2, 'u': 2, 't': 1}
```

O histograma indica que as letras 'a' e 'b' aparecem uma vez; 'o' aparece duas vezes, e assim por diante.

Os dicionários têm um método chamado `get`, que toma uma chave e um valor padrão. Se a chave aparecer no dicionário, `get` retorna o valor correspondente; se não for o caso, ele retorna o valor padrão. Por exemplo:

```python
>>> h = histogram('a')
>>> h
{'a': 1}
>>> h.get('a', 0)
1
>>> h.get('b', 0)
0
```

Como exercício, use o `get` para escrever a função `histogram` de forma mais concisa. Tente eliminar a instrução `if`.
