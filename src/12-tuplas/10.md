## 12.10 - Exercícios

### Exercício 12.1

Escreva uma função chamada `most_frequent` que receba uma string e exiba as letras em ordem decrescente de frequência. Encontre amostras de texto de vários idiomas diferentes e veja como a frequência das letras varia entre os idiomas. Compare seus resultados com as tabelas em http://en.wikipedia.org/wiki/Letter_frequencies.

Solução: http://thinkpython2.com/code/most_frequent.py.

### Exercício 12.2

Mais anagramas!

1. Escreva um programa que leia uma lista de palavras de um arquivo (veja “Leitura de listas de palavras”, na página 133) e imprima todos os conjuntos de palavras que são anagramas.

        Aqui está um exemplo de como a saída pode parecer:

```python
        ['deltas', 'desalt', 'lasted', 'salted', 'slated', 'staled']
        ['retainers', 'ternaries']
        ['generating', 'greatening']
        ['resmelts', 'smelters', 'termless']
```

        Dica: você pode querer construir um dicionário que mapeie uma coleção de letras a uma lista de palavras que podem ser soletradas com essas letras. A pergunta é: como representar a coleção de letras de forma que possa ser usada como uma chave?

2. Altere o programa anterior para que exiba a lista mais longa de anagramas primeiro, seguido pela segunda mais longa, e assim por diante.

3. No Scrabble, um “bingo” é quando você joga todas as sete peças na sua estante, junto com uma peça no tabuleiro, para formar uma palavra de oito letras. Que coleção de oito letras forma o maior número possível de bingos? Dica: há sete.

Solução: http://thinkpython2.com/code/anagram_sets.py.

### Exercício 12.3

Duas palavras formam um “par de metátese” se você puder transformar uma na outra trocando duas letras, por exemplo, “converse” e “conserve”. Escreva um programa que descubra todos os pares de metátese no dicionário. Dica: não teste todos os pares de palavras e não teste todas as trocas possíveis.

Solução: http://thinkpython2.com/code/metathesis.py. Crédito: este exercício foi inspirado por um exemplo em http://puzzlers.org.

### Exercício 12.4

Aqui está outro quebra-cabeça do programa Car Talk (http://www.cartalk.com/content/puzzlers):

Qual é a palavra inglesa mais longa, que permanece uma palavra inglesa válida, conforme vai removendo suas letras, uma após a outra?

Agora, as letras podem ser retiradas do fim ou do meio, mas você não pode reajustar nenhuma delas. Cada vez que remove uma letra, você acaba com outra palavra inglesa. Se fizer isto, eventualmente você acabará com uma letra e isso também será uma palavra inglesa; uma encontrada no dicionário. Quero saber qual é a palavra mais longa e quantas letras tem?

Vou dar um pequeno exemplo modesto: Sprite. Ok? Você começa com sprite, tira uma letra do interior da palavra, tira o r, e ficamos com a palavra spite, então tiramos o e do fim, ficamos com spit, tiramos o s, ficamos com pit, it e I.

Escreva um programa que encontre todas as palavras que podem ser reduzidas desta forma, e então encontre a mais longa.

Este exercício é um pouco mais desafiador que a maioria, então aqui estão algumas sugestões:

1. Você pode querer escrever uma função que receba uma palavra e calcule uma lista de todas as palavras que podem ser formadas retirando uma letra. Esses são os “filhos” da palavra.

2. Recursivamente, uma palavra é redutível se algum de seus filhos for redutível. Como caso base, você pode considerar a string vazia redutível.

3. A lista de palavras que forneci, words.txt, não contém palavras de uma letra só. Portanto, você pode querer acrescentar “I”, “a”, e a string vazia.

4. Para melhorar o desempenho do seu programa, você pode querer memorizar as palavras conhecidas por serem redutíveis.

Solução: http://thinkpython2.com/code/reducible.py.
