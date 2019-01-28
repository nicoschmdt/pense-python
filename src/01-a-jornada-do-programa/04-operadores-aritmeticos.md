## 1.4 - Operadores aritméticos

Depois do “Hello, World”, o próximo passo é a aritmética. O Python tem operadores, que são símbolos especiais representando operações de computação, como adição e multiplicação.

Os operadores +, - e \* executam a adição, a subtração e a multiplicação, como nos seguintes exemplos:

```python
>>> 40 + 2
42
>>> 43 - 1
42
>>> 6 * 7
42
O [operador](08-glossario.md#operador) / executa a divisão:
>>> 84 / 2
42.0
```

Pode ser que você fique intrigado pelo resultado ser 42.0 em vez de 42. Vou explicar isso na próxima seção.

Finalmente, o operador \*\* executa a exponenciação; isto é, eleva um número a uma potência:

```python
>>> 6 ** 2 + 6
42
```

Em algumas outras linguagens, o ^ é usado para a exponenciação, mas no Python é um operador bitwise, chamado XOR. Se não tiver familiaridade com operadores bitwise, o resultado o surpreenderá:

```python
>>> 6 ^ 2
4
```

Não abordarei operadores bitwise neste livro, mas você pode ler sobre eles em [http://wiki.python.org/moin/BitwiseOperators](http://wiki.python.org/moin/BitwiseOperators).
