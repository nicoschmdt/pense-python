## 4.2 - Repetição simples

Provavelmente você escreveu algo assim:

```python
bob.fd(100)
bob.lt(90)
bob.fd(100)
bob.lt(90)
bob.fd(100)
bob.lt(90)
bob.fd(100)
```

Podemos fazer a mesma coisa de forma mais concisa com uma instrução for. Acrescente este exemplo a mypolygon.py e execute-o novamente:

```python
for i in range(4):
    print('Hello!')
```

Você deve ver algo assim:

```python
Hello!
Hello!
Hello!
Hello!
```

Este é o uso mais simples da instrução for; depois veremos mais sobre isso. Mas isso deve ser o suficiente para que você possa reescrever o seu programa de desenhar quadrados. Não continue a leitura até que dê certo.

Aqui está uma instrução for que desenha um quadrado:


```python
for i in range(4):
    bob.fd(100)
    bob.lt(90)
```

A sintaxe de uma instrução for é semelhante à definição de uma função. Tem um cabeçalho que termina em dois pontos e um corpo indentado. O corpo pode conter qualquer número de instruções.

Uma instrução for também é chamada de [loop](11-glossario.md#loop) porque o fluxo da execução passa pelo corpo e depois volta ao topo. Neste caso, ele passa pelo corpo quatro vezes.

Esta versão, na verdade, é um pouco diferente do código anterior que desenha quadrados porque faz outra volta depois de desenhar o último lado do quadrado. A volta extra leva mais tempo, mas simplifica o código se fizermos a mesma coisa a cada vez pelo loop. Esta versão também tem o efeito de trazer o turtle de volta à posição inicial, de frente para a mesma direção em que estava.
