## 10.13 - Depuração

O uso descuidado de listas (e de outros objetos mutáveis) pode levar a longas horas de depuração. Aqui estão algumas armadilhas comuns e formas de evitá-las:

1. A maior parte dos métodos de listas alteram o argumento e retornam None. Isto é o oposto dos métodos de strings, que retornam uma nova string e deixam a original intocada.

        Se você está acostumado a escrever código de strings desta forma:

```python
        word = word.strip()
```

        É tentador escrever código de listas como este:

```python
        t = t.sort()            # ERRADO!
```

        Como sort retorna None, a próxima operação que você executar com t provavelmente vai falhar.

        Antes de usar métodos e operadores de listas, você deve ler a documentação com cuidado e testá-los no modo interativo.


2. Escolha o termo e fique com ele.

        Parte do problema com listas é que há muitas formas de fazer coisas com elas. Por exemplo, para remover um elemento de uma lista você pode usar pop, remove, del ou até uma atribuição de fatia.

        Para adicionar um elemento você pode usar o método append ou o operador +. Assumindo que t é uma lista e x é um elemento da lista, isto está correto:

```python
        t.append(x)
        t = t + [x]
        t += [x]
        E isto está errado:
        t.append([x])          # ERRADO!
        t = t.append(x)        # ERRADO!
        t + [x]                # ERRADO!
        t = t + x              # ERRADO!
```

        Experimente cada um desses exemplos no modo interativo para conferir se você entendeu o que fazem. Note que apenas o último causa um erro de tempo de execução; os outros três são legais, mas eles fazem a coisa errada.

3. Faça cópias para evitar o uso de alias.

        Se quiser usar um método como sort, que altera o argumento, mas precisa manter a lista original, você pode fazer uma cópia:



```python
        >>> t = [3, 1, 2]
        >>> t2 = t[:]
        >>> t2.sort()
        >>> t
        [3, 1, 2]
        >>> t2
        [1, 2, 3]
```

        Neste exemplo você poderia usar também a função integrada sorted, que retorna uma nova lista classificada e deixa a original intocada.



```python
        >>> t2 = sorted(t)
        >>> t
        [3, 1, 2]
        >>> t2
        [1, 2, 3]
```
