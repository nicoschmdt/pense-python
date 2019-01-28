## 16.5 - Depuração

Um objeto `Time` é bem formado se os valores de `minute` e `second` estiverem entre 0 e 60 (incluindo 0, mas não 60) e se `hour` for positivo. `hour` e `minute` devem ser valores inteiros, mas podemos permitir que `second` tenha uma parte fracionária.

Requisitos como esses chamam-se invariáveis porque sempre devem ser verdadeiros. Para dizer de outra forma, se não forem verdadeiros, algo deu errado.

Escrever código para verificar requisitos invariáveis pode ajudar a descobrir erros e encontrar suas causas. Por exemplo, você pode ter uma função como valid\_time, que receba um objeto Time e retorne False se ele violar um requisito [invariável](06-glossario.md#invariável):

```python
def valid_time(time):
    if time.hour < 0 or time.minute < 0 or time.second < 0:
        return False
    if time.minute >= 60 or time.second >= 60:
        return False
    return True
```

No início de cada função você pode verificar os argumentos para ter certeza de que são válidos:

```python
def add_time(t1, t2):
    if not valid_time(t1) or not valid_time(t2):
        raise ValueError('invalid Time object in add_time')

    seconds = time_to_int(t1) + time_to_int(t2)
    return int_to_time(seconds)
```

Ou você pode usar uma instrução `assert`, que verifica determinado requisito invariável e cria uma exceção se ela falhar:

```python
def add_time(t1, t2):
    assert valid_time(t1) and valid_time(t2)
    seconds = time_to_int(t1) + time_to_int(t2)
    return int_to_time(seconds)
```

Instruções assert são úteis porque distinguem o código que lida com condições normais do código que verifica erros.
