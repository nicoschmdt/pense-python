## 14.2 - Leitura e escrita

Um arquivo de texto é uma sequência de caracteres armazenados em um meio permanente como uma unidade de disco rígido, pendrive ou CD-ROM. Vimos como abrir e ler um arquivo em “Leitura de listas de palavras” na página 133.

Para escrever um arquivo texto, é preciso abri-lo com o modo `'w'` como segundo parâmetro:

```python
>>> fout = open('output.txt', 'w')
```

Se o arquivo já existe, abri-lo em modo de escrita elimina os dados antigos e começa tudo de novo, então tenha cuidado! Se o arquivo não existir, é criado um arquivo novo.

`open` retorna um objeto de arquivo que fornece métodos para trabalhar com o arquivo. O método write põe dados no arquivo:


```python
>>> line1 = "This here's the wattle,\n"
>>> fout.write(line1)
24
```

O valor devolvido é o número de caracteres que foram escritos. O objeto de arquivo monitora a posição em que está, então se você chamar `write` novamente, os novos dados são acrescentados ao fim do arquivo:


```python
>>> line2 = "the emblem of our land.\n"
>>> fout.write(line2)
24
```

Ao terminar de escrever, você deve fechar o arquivo:

```python
>>> fout.close()
```

Se não fechar o arquivo, ele é fechado para você quando o programa termina.
