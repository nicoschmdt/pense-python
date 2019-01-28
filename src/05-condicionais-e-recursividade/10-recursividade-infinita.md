## 5.10 - Recursividade infinita

Se a [recursividade](13-glossario.md#recursividade) nunca atingir um [caso-base](13-glossario.md#caso-base), continua fazendo chamadas recursivas para sempre, e o programa nunca termina. Isso é conhecido como [recursividade infinita](13-glossario.md#recursividade-infinita) e geralmente não é uma boa ideia. Aqui está um programa mínimo com recursividade infinita:

```python
def recurse():
    recurse()
```

Na maior parte dos ambientes de programação, um programa com recursividade infinita não é realmente executado para sempre. O Python exibe uma mensagem de erro quando a profundidade máxima de recursividade é atingida:

```python
  File "<stdin>", line 2, in recurse
  File "<stdin>", line 2, in recurse
  File "<stdin>", line 2, in recurse
                  .
                  .
                  .
  File "<stdin>", line 2, in recurse
RuntimeError: Maximum recursion depth exceeded
```

Este traceback é um pouco maior que o que vimos no capítulo anterior. Quando o erro ocorre, há mil frames de recurse na pilha!

Se você escrever em recursividade infinita por engano, confira se a sua função tem um caso-base que não faz uma chamada recursiva. E se houver um caso-base, verifique se você vai mesmo atingi-lo.
