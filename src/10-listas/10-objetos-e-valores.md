## 10.10 - Objetos e valores

Se executarmos essas instruções de atribuição:

```python
a = 'banana'
b = 'banana'
```

Sabemos que a e b se referem a uma string, mas não sabemos se elas se referem à mesma string. Há dois estados possíveis, mostrados na Figura 10.2.

![Figura 10.2 – Diagramas de estado possíveis com duas variáveis.](fig/tnkp_1002.png)
<br>_Figura 10.2 – Diagramas de estado possíveis com duas variáveis._

Em um caso, a e b se referem a dois objetos diferentes que têm o mesmo valor. No segundo caso, elas se referem ao mesmo objeto.

Para verificar se duas variáveis se referem ao mesmo objeto, você pode usar o operador is:


```python
>>> a = 'banana'
>>> b = 'banana'
>>> a is b
True
```

Nesse exemplo, o Python criou apenas um objeto de string e tanto a quanto b se referem a ele. Mas quando você cria duas listas, você tem dois objetos:


```python
>>> a = [1, 2, 3]
>>> b = [1, 2, 3]
>>> a is b
False
```

Então o diagrama de estado fica igual ao da Figura 10.3.

![Figura 10.3 – Diagrama de estado com variáveis associadas a listas distintas, de mesmo valor.](fig/tnkp_1003.png)
<br>_Figura 10.3 – Diagrama de estado com variáveis associadas a listas distintas, de mesmo valor._

Nesse caso, diríamos que as duas listas são equivalentes, porque elas têm os mesmos elementos, mas não idênticas, porque elas não são o mesmo objeto. Se dois objetos forem idênticos, eles também são equivalentes, mas se eles forem equivalentes, não são necessariamente idênticos.

Até agora, temos usado “objeto” e “valor” de forma intercambiável, mas é mais exato dizer que um objeto tem um valor. Se avaliar [1, 2, 3], você tem um objeto de lista cujo valor é uma sequência de números inteiros. Se outra lista tem os mesmos elementos, dizemos que tem o mesmo valor, mas não é o mesmo objeto.
