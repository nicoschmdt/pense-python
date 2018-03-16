## 15.7 - Depuração

Ao começar a trabalhar com objetos, provavelmente você encontrará algumas novas exceções. Se tentar acessar um atributo que não existe, recebe um `AttributeError`:

```python
>>> p = Point()
>>> p.x = 3
>>> p.y = 4
>>> p.z
AttributeError: Point instance has no attribute 'z'
```

Se não estiver certo sobre o tipo que um objeto é, pode perguntar:

```python
>>> type(p)
<class '__main__.Point'>
```

Você também pode usar `isinstance` para verificar se um objeto é uma instância de uma classe:

```python
>>> isinstance(p, Point)
True
```

Caso não tenha certeza se um objeto tem determinado atributo, você pode usar a função integrada `hasattr`:

```python
>>> hasattr(p, 'x')
True
>>> hasattr(p, 'z')
False
```

O primeiro argumento pode ser qualquer objeto; o segundo argumento é uma `string` com o nome do atributo.

Você também pode usar uma instrução `try` para ver se o objeto tem os atributos de que precisa:


```python
try:
    x = p.x
except AttributeError:
    x = 0
```

Essa abordagem pode facilitar a escrita de funções que atuam com tipos diferentes; você verá mais informações sobre isso em “Polimorfismo”, na página 248.
