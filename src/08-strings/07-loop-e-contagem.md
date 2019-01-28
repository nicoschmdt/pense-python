## 8.7 - Loop e contagem

O seguinte programa conta o número de vezes que a letra a aparece em uma string:

```python
word = 'banana'
count = 0
for letter in word:
    if letter == 'a':
        count = count + 1
print(count)
```

Este programa demonstra outro padrão de computação chamado [contador](12-glossario.md#contador). A variável `count` é inicializada com 0 e então incrementada cada vez que um a é encontrado. Ao sair do loop, `count` contém o resultado – o número total de letras `'a'`.

Como exercício, encapsule este código em uma função denominada `count` e generalize-o para que aceite a string e a letra como argumentos.

Então reescreva a função para que, em vez de [atravessar](12-glossario.md#atravessar) a string, ela use a versão de três parâmetros do find da seção anterior.
