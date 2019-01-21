## 16.1 - Time

Para ter mais um exemplo de tipo definido pelo programador, criaremos uma classe chamada `Time` (hora), que registra um horário no dia. A definição da classe é assim:


```python
class Time:
    """Represents the time of day.
    attributes: hour, minute, second
    """
```

Podemos criar um objeto `Time` e ter atributos para horas, minutos e segundos:

```python
time = Time()
time.hour = 11
time.minute = 59
time.second = 30
```

O diagrama de estado do objeto Time está na Figura 16.1.

![Figura 16.1 – Diagrama de um objeto Time](/fig/tnkp_1601.png).
<br>_Figura 16.1 – Diagrama de um objeto_ `Time`.

Como exercício, escreva uma função chamada `print_time`, que receba um objeto Time e o exiba na forma hour:minute:second. Dica: a sequência de formatação `'%.2d'` exibe um número inteiro com, pelo menos, dois dígitos, incluindo um zero à esquerda, se for necessário.

Escreva uma função booleana chamada `is_after`, que receba dois objetos Time, `t1` e `t2`, e devolva `True` se `t1` for cronologicamente depois de `t2` e `False` se não for. Desafio: não use uma instrução `if`.
