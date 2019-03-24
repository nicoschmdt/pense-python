## 14.6 - Bancos de dados

Um [banco de dados](11-glossario.md#banco-de-dados) é um arquivo organizado para armazenar dados. Muitos bancos de dados são organizados como um dicionário, porque mapeiam chaves a valores. A maior diferença entre um banco de dados e um dicionário é que o banco de dados está em um disco (ou outro armazenamento permanente), portanto persiste depois que o programa termina.

O módulo dbm fornece uma interface para criar e atualizar arquivos de banco de dados. Como exemplo, criarei um banco de dados que contém legendas de arquivos de imagem.

Abrir um banco de dados é semelhante à abertura de outros arquivos:

```python
>>> import dbm
>>> db = dbm.open('captions', 'c')
```

O modo 'c' significa que o banco de dados deve ser criado, se ainda não existir. O resultado é um objeto de banco de dados que pode ser usado (para a maior parte das operações) como um dicionário.

Quando você cria um novo item, dbm atualiza o arquivo de banco de dados:

```python
>>> db['cleese.png'] = 'Photo of John Cleese.'
```

Quando você acessa um dos itens, dbm lê o arquivo:

```python
>>> db['cleese.png']
b'Photo of John Cleese.'
```

O resultado é um objeto `bytes`, o que explica o prefixo `b`. Um objeto `bytes` é semelhante a uma string, em muitos aspectos. Quando você avançar no Python, a diferença se tornará importante, mas, por enquanto, podemos ignorá-la.

Se fizer outra atribuição a uma chave existente, o dbm substitui o valor antigo:

```python
>>> db['cleese.png'] = 'Photo of John Cleese doing a silly walk.'
>>> db['cleese.png']
b'Photo of John Cleese doing a silly walk.'
```

Alguns métodos de dicionário, como keys e items, não funcionam com objetos de banco de dados. No entanto, a iteração com um loop `for`, sim:

```python
for key in db:
    print(key, db[key])
```

Como em outros arquivos, você deve fechar o banco de dados quando terminar:

```python
>>> db.close()
```
