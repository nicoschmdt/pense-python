## 7.4 - break

Às vezes você não sabe que está na hora de terminar um loop até que já esteja na metade do corpo. Neste caso pode usar a instrução break para sair do loop.

Por exemplo, suponha que você quer receber uma entrada do usuário até que este digite done. Você pode escrever:

```python
while True:
    line = input('> ')
    if line == 'done':
        break
    print(line)
print('Done!')
```

A condição do loop é True, que sempre é verdade, então o loop roda até que chegue à instrução de interrupção.

Cada vez que passa pelo loop, o programa apresenta ao usuário um colchete angular. Se o usuário digitar done, a instrução break sai do loop. Senão, o programa ecoa o que quer que o usuário digite e volta ao topo do loop. Aqui está uma amostra de execução:

```python
> not done
not done
> done
Done!
```

Esta forma de escrever loops while é comum porque podemos verificar a condição em qualquer lugar do loop (não somente no topo) e podemos exprimir a condição de parada afirmativamente (“pare quando isto acontecer”) em vez de negativamente (“continue a seguir até que isto aconteça”).
