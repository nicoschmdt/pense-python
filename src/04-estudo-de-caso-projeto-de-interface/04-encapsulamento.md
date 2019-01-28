## 4.4 - Encapsulamento

O primeiro exercício pede que você ponha seu código para desenhar quadrados em uma definição de função e então chame a função, passando o turtle como parâmetro. Aqui está uma solução:

```python
def square(t):
    for i in range(4):
        t.fd(100)
        t.lt(90)

square(bob)
```

As instruções mais internas, fd e lt, são endentadas duas vezes para mostrar que estão dentro do [loop](11-glossario.md#loop) for, que está dentro da definição da função. A linha seguinte, square(bob), está alinhada à margem esquerda, o que indica tanto o fim do loop for como da definição de função.

Dentro da função, o t indica o mesmo turtle bob, então t.lt (90) tem o mesmo efeito que bob.lt (90). Neste caso, por que não chamar o parâmetro bob? A ideia é que t pode ser qualquer turtle, não apenas bob, então você pode criar um segundo turtle e passá-lo como argumento ao square:

```python
alice = turtle.Turtle()
square(alice)
```

Incluir uma parte do código em uma função chama-se [encapsulamento](11-glossario.md#encapsulamento). Um dos benefícios do encapsulamento é que ele atribui um nome ao código, o que serve como uma espécie de documentação. Outra vantagem é que se você reutilizar o código, é mais conciso chamar uma função duas vezes que copiar e colar o corpo!
