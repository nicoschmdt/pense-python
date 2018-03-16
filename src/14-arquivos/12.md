## 14.12 - Exercícios

### Exercício 14.1

Escreva uma função chamada sed que receba como argumentos uma string-padrão, uma string de substituição e dois nomes de arquivo; ela deve ler o primeiro arquivo e escrever o conteúdo no segundo arquivo (criando-o, se necessário). Se a string-padrão aparecer em algum lugar do arquivo, ela deve ser substituída pela string de substituição.

Se ocorrer um erro durante a abertura, leitura, escrita ou fechamento dos arquivos, seu programa deve capturar a exceção, exibir uma mensagem de erro e encerrar.

Solução: http://thinkpython2.com/code/sed.py.

### Exercício 14.2

Se você baixar minha solução do Exercício 12.2 em http://thinkpython2.com/code/anagram_sets.py, verá que ela cria um dicionário que mapeia uma string ordenada de letras à lista de palavras que podem ser soletradas com aquelas letras. Por exemplo, `'opst'` mapeia à lista `['opts', 'post', 'pots', 'spot', 'stop', 'tops']`.

Escreva um módulo que importe `anagram_sets` e forneça duas novas funções: `store_anagrams` deve guardar o dicionário de anagramas em uma “prateleira” (objeto criado pelo módulo `sheve`); `read_anagrams` deve procurar uma palavra e devolver uma lista dos seus anagramas.

Solução: http://thinkpython2.com/code/anagram_db.py.

### Exercício 14.3

Em uma grande coleção de arquivos MP3 pode haver mais de uma cópia da mesma música, guardada em diretórios diferentes ou com nomes de arquivo diferentes. A meta deste exercício é procurar duplicatas.

1. Escreva um programa que procure um diretório e todos os seus subdiretórios, recursivamente, e retorne uma lista de caminhos completos de todos os arquivos com um dado sufixo (como .mp3). Dica: os.path fornece várias funções úteis para manipular nomes de caminhos e de arquivos.

2. Para reconhecer duplicatas, você pode usar md5sum para calcular uma “soma de controle” para cada arquivo. Se dois arquivos tiverem a mesma soma de controle, provavelmente têm o mesmo conteúdo.

3. Para conferir o resultado, você pode usar o comando Unix `diff`.

Solução: http://thinkpython2.com/code/find\_duplicates.py.
