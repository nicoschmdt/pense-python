## 15.5 - Objetos são mutáveis

Você pode alterar o estado de um objeto fazendo uma atribuição a um dos seus atributos. Por exemplo, para mudar o tamanho de um retângulo sem mudar sua posição, você pode alterar os valores de width e height:

```python
box.width = box.width + 50
box.height = box.height + 100
```

Você também pode escrever funções que alteram objetos. Por exemplo, `grow_rectangle` recebe um objeto `Rectangle` e dois números, `dwidth` e `dheight`, e adiciona os números à largura e altura do retângulo:

```python
def grow_rectangle(rect, dwidth, dheight):
    rect.width += dwidth
    rect.height += dheight
```

Eis um exemplo que demonstra o efeito:

```python
>>> box.width, box.height
(150.0, 300.0)
>>> grow_rectangle(box, 50, 100)
>>> box.width, box.height
(200.0, 400.0)
```

Dentro da função, `rect` é um alias de `box`, então quando a função altera `rect`, `box` aponta para o objeto alterado.

Como exercício, escreva uma função chamada `move_rectangle` que toma um Rectangle e dois números chamados dx e dy. Ela deve alterar a posição do retângulo, adicionando dx à coordenada x de corner e adicionando dy à coordenada y de corner.
