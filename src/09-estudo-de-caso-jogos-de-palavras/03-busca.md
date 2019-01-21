## 9.3 - Busca

Todos os exercícios na seção anterior têm algo em comum; eles podem ser resolvidos com o modelo de busca que vimos em [Buscando](../08-strings/06-buscando.md). O exemplo mais simples é:

```python
def has_no_e(word):
    for letter in word:
        if letter == 'e':
            return False
    return True
```

O loop for atravessa os caracteres em word. Se encontrarmos a letra “e”, podemos retornar False imediatamente; se não for o caso, temos que ir à letra seguinte. Se sairmos do loop normalmente, isso quer dizer que não encontramos um “e”, então retornamos True.

Você pode escrever esta função de forma mais concisa usando o operador in, mas comecei com esta versão porque ela demonstra a lógica do modelo de busca.

`avoids` é uma versão mais geral de `has_no_e`, mas tem a mesma estrutura:


```python
def avoids(word, forbidden):
    for letter in word:
        if letter in forbidden:
            return False
    return True
```

Podemos retornar `False` logo que encontrarmos uma letra proibida; se chegarmos ao fim do loop, retornamos `True`.

`uses_only` é semelhante, exceto pelo sentido da condição, que se inverte:

```python
def uses_only(word, available):
    for letter in word:
        if letter not in available:
            return False
    return True
```

Em vez de uma lista de letras proibidas, temos uma lista de letras disponíveis. Se encontrarmos uma letra em word que não está em `available`, podemos retornar `False`.

`uses_all` é semelhante, mas invertemos a função da palavra e a string de letras:

```python
def uses_all(word, required):
    for letter in required:
        if letter not in word:
            return False
    return True
```

Em vez de atravessar as letras em `word`, o loop atravessa as letras obrigatórias. Se alguma das letras obrigatórias não aparecer na palavra, podemos retornar `False`.

Se você realmente estivesse pensando como um cientista da computação, teria reconhecido que `uses_all` foi um exemplo de um problema resolvido anteriormente e escreveria:

```python
def uses_all(word, required):
    return uses_only(required, word)
```

Esse é um exemplo de um plano de desenvolvimento de programa chamado __redução a um problema resolvido anteriormente__, ou seja, você reconhece o problema no qual está trabalhando como um exemplo de um problema já resolvido e aplica uma solução existente.
