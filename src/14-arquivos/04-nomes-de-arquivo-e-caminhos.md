## 14.4 - Nomes de arquivo e caminhos

Os arquivos são organizados em diretórios (também chamados de “pastas”). Cada programa em execução tem um “[diretório](11-glossario.md#diretório) atual”, que é o diretório-padrão da maior parte das operações. Por exemplo, quando você abre um arquivo de leitura, Python o procura no diretório atual.

O módulo `os` fornece funções para trabalhar com arquivos e diretórios (“os” é a abreviação de “sistema operacional” em inglês). `os.getcwd` devolve o nome do diretório atual:


```python
>>> import os
>>> cwd = os.getcwd()
>>> cwd
'/home/dinsdale'
```

`cwd` é a abreviação de “diretório de trabalho atual” em inglês. O resultado neste exemplo é `/home/dinsdale`, que é o diretório-padrão de um usuário chamado “dinsdale”.

Uma string como `'/home/dinsdale'`, que identifica um arquivo ou diretório, é chamada de [caminho](11-glossario.md#caminho) (path).

Um nome de arquivo simples, como `memo.txt`, também é considerado um caminho, mas é um [caminho relativo](11-glossario.md#caminho-relativo), porque se relaciona ao diretório atual. Se o diretório atual é `/home/dinsdale`, o nome de arquivo `memo.txt` se referiria a `/home/dinsdale/memo.txt`.

Um caminho que começa com `/` não depende do diretório atual; isso é chamado de [caminho absoluto](11-glossario.md#caminho-absoluto). Para encontrar o caminho absoluto para um arquivo, você pode usar `os.path.abspath`:

```python
>>> os.path.abspath('memo.txt')
'/home/dinsdale/memo.txt'
```

`os.path` fornece outras funções para trabalhar com nomes de arquivo e caminhos. Por exemplo, `os.path.exists` que verifica se um arquivo ou diretório existe:

```python
>>> os.path.exists('memo.txt')
True
```

Se existir, `os.path.isdir` verifica se é um diretório:

```python
>>> os.path.isdir('memo.txt')
False
>>> os.path.isdir('/home/dinsdale')
True
```

De forma similar, `os.path.isfile` verifica se é um arquivo.

os.listdir retorna uma lista dos arquivos (e outros diretórios) no diretório dado:

```python
 >>> os.listdir(cwd)
['music', 'photos', 'memo.txt']
```

Para demonstrar essas funções, o exemplo seguinte “passeia” por um diretório, exibe os nomes de todos os arquivos e chama a si mesmo recursivamente em todos os diretórios:

```python
def walk(dirname):
    for name in os.listdir(dirname):
        path = os.path.join(dirname, name)
        if os.path.isfile(path):
            print(path)
        else:
            walk(path)
```

`os.path.join` recebe um diretório e um nome de arquivo e os une em um caminho completo.

O módulo `os` fornece uma função chamada `walk`, que é semelhante, só que mais versátil. Como exercício, leia a documentação e use-a para exibir os nomes dos arquivos em um diretório dado e seus subdiretórios. Você pode baixar minha solução em [http://thinkpython2.com/code/walk.py](http://thinkpython2.com/code/walk.py).
