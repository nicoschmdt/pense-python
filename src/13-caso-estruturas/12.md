## 13.12 - Exercícios

### Exercício 13.9

A “classificação” de uma palavra é a sua posição em uma lista de palavras classificadas por frequência: a palavra mais comum tem a classificação 1, a segunda mais comum é 2 etc.

A lei de Zipf descreve a relação entre classificações e frequências das palavras em linguagens naturais (http://en.wikipedia.org/wiki/Zipf's_law). Ela prevê especificamente que a frequência, f, da palavra com classificação r é:

```python
f = cr−s
```

onde s e c são parâmetros que dependem do idioma e do texto. Se você tomar o logaritmo de ambos os lados desta equação, obtém:

```python
log f = log c − s log r
```

Se você traçar o log de f contra o log de r, terá uma linha reta com uma elevação -s e interceptar o log de c.

Escreva um programa que leia um texto em um arquivo, conte as frequências das palavras e exiba uma linha para cada palavra, em ordem descendente da frequência, com log de f e log de r. Use o programa gráfico de sua escolha para traçar os resultados e verifique se formam uma linha reta. Você pode estimar o valor de s?

Solução: http://thinkpython2.com/code/zipf.py. Para executar a minha solução, você vai precisar do módulo de gráficos `matplotlib`. Se você instalou o Anaconda, já tem o `matplotlib`; se não tiver, é preciso instalá-lo.
