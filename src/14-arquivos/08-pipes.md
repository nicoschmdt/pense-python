## 14.8 - Pipes

A maior parte dos sistemas operacionais fornece uma interface de linha de comando, conhecida como [shell](11-glossario.md#shell). Shells normalmente fornecem comandos para navegar nos sistemas de arquivos e executar programas. Por exemplo, em Unix você pode alterar diretórios com `cd`, exibir o conteúdo de um [diretório](11-glossario.md#diretório) com `ls` e abrir um navegador web digitando (por exemplo) `firefox`.

Qualquer programa que possa ser aberto no shell também pode ser aberto no Python usando um [objeto pipe](11-glossario.md#objeto-pipe), que representa um programa em execução.

Por exemplo, o comando Unix `ls -l` normalmente exibe o conteúdo do diretório atual no formato longo. Você pode abrir ls com `os.popen[1]`:

```python
>>> cmd = 'ls -l'
>>> fp = os.popen(cmd)
```

O argumento é uma string que contém um comando shell. O valor de retorno é um objeto que se comporta como um arquivo aberto. É possível ler a saída do processo ls uma linha por vez com readline ou receber tudo de uma vez com read:

```python
>>> res = fp.read()
```

Ao terminar, feche o pipe como se fosse um arquivo:


```python
>>> stat = fp.close()
>>> print(stat)
None
```

O valor de retorno é o status final do processo `ls`; `None` significa que terminou normalmente (sem erros).

Por exemplo, a maior parte dos sistemas Unix oferece um comando chamado `md5sum`, que lê o conteúdo de um arquivo e calcula uma assinatura digital. Você pode ler sobre o MD5 em [http://en.wikipedia.org/wiki/Md5](http://en.wikipedia.org/wiki/Md5). Este comando fornece uma forma eficiente de verificar se dois arquivos têm o mesmo conteúdo. A probabilidade de dois conteúdos diferentes produzirem a mesma assinatura digital é muito pequena (isto é, muito pouco provável que aconteça antes do colapso do universo).

Você pode usar um pipe para executar o `md5sum` do Python e receber o resultado:

```python
>>> filename = 'book.tex'
>>> cmd = 'md5sum ' + filename
>>> fp = os.popen(cmd)
>>> res = fp.read()
>>> stat = fp.close()
>>> print(res)
1e0033f0ed0656636de0d75144ba32e0 book.tex
>>> print(stat)
None
```
