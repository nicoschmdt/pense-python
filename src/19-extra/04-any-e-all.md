## 19.4 - any e all

O Python tem uma função integrada, any, que recebe uma sequência de valores booleanos e retorna True se algum dos valores for True. Ela funciona em listas:

```python
>>> any([False, False, True])
True
```

Entretanto, muitas vezes é usada com expressões geradoras:

```python
>>> any(letter == 't' for letter in 'monty')
True
```

Esse exemplo não é muito útil porque faz a mesma coisa que o operador in. Porém, podemos usar any para reescrever algumas das funções de pesquisa que escrevemos em “Busca”, na página 136. Por exemplo, poderíamos escrever avoids dessa forma:

```python
def avoids(word, forbidden):
    return not any(letter in forbidden for letter in word)
```

A função quase pode ser lida como uma frase em inglês: “word evita forbidden se não houver nenhuma letra proibida em word”.

Usar `any` com uma expressão geradora é eficiente porque ela retorna imediatamente se encontrar um valor True, então não é preciso avaliar a sequência inteira.

O Python oferece outra função integrada, `all`, que retorna True se todos os elementos da sequência forem True. Como exercício, use all para reescrever `uses_all` de “Busca”, na página 136.
