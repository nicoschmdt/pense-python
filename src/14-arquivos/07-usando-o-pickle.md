## 14.7 - Usando o Pickle

Uma limitação de `dbm` é que as chaves e os valores têm que ser strings ou bytes. Se tentar usar algum outro tipo, vai receber um erro.

O módulo `pickle` pode ajudar. Ele traduz quase qualquer tipo de objeto em uma string conveniente para o armazenamento em um [banco de dados](11-glossario.md#banco-de-dados), e então traduz strings de volta em objetos.

pickle.dumps recebe um objeto como parâmetro e retorna uma representação de string:


```python
>>> import pickle
>>> t = [1, 2, 3]
>>> pickle.dumps(t)
b'\x80\x03]q\x00(K\x01K\x02K\x03e.'
```

O formato não é óbvio para leitores humanos; o objetivo é que seja fácil para o `pickle` interpretar. `pickle.loads` reconstitui o objeto:

```python
>>> t1 = [1, 2, 3]
>>> s = pickle.dumps(t1)
>>> t2 = pickle.loads(s)
>>> t2
[1, 2, 3]
```

Embora o novo objeto tenha o mesmo valor que o antigo, não é (em geral) o mesmo objeto:

```python
>>> t1 == t2
True
>>> t1 is t2
False
```

Em outras palavras, usar o `pickle.dumps` e `pickle.loads` tem o mesmo efeito que copiar o objeto.

Você pode usar o `pickle` para guardar variáveis que não são strings em um banco de dados. Na verdade, esta combinação é tão comum que foi encapsulada em um módulo chamado `shelve`.
