## 7.2 - Atualização de variáveis

Um tipo comum de reatribuição é uma atualização, onde o novo valor da variável depende do velho.

```python
>>> x = x + 1
```

Isso significa “pegue o valor atual de x, acrescente um, e então atualize x para o novo valor”.

Se você tentar atualizar uma variável que não existe, recebe um erro porque o Python avalia o lado direito antes de atribuir um valor a x:

```python
>>> x = x + 1
NameError: name 'x' is not defined
```

Antes de poder atualizar uma variável é preciso inicializá-la, normalmente com uma atribuição simples:

```python
>>> x = 0
>>> x = x + 1
```

Atualizar uma variável acrescentando 1 chama-se incremento; subtrair 1 chama-se decremento.
