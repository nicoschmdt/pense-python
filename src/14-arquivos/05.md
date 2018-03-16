## 14.5 - Captura de exceções

Muitas coisas podem dar errado quando você tenta ler e escrever arquivos. Se tentar abrir um arquivo que não existe, você recebe um `IOError`:

```python
>>> fin = open('bad_file')
IOError: [Errno 2] No such file or directory: 'bad\_file'
```

Se não tiver permissão para acessar um arquivo:

```python
>>> fout = open('/etc/passwd', 'w')
PermissionError: [Errno 13] Permission denied: '/etc/passwd'
```

E se tentar abrir um diretório para leitura, recebe

```python
>>> fin = open('/home')
IsADirectoryError: [Errno 21] Is a directory: '/home'
```

Para evitar esses erros, você pode usar funções como `os.path.exists` e `os.path.isfile`, mas levaria muito tempo e código para verificar todas as possibilidades (se "Errno 21" significa algo, pode ser que pelo menos 21 coisas podem dar errado).

É melhor ir em frente e tentar, e lidar com problemas se eles surgirem, que é exatamente o que a instrução `try` faz. A sintaxe é semelhante à da instrução `if…else`:

```python
try:
    fin = open('bad_file')
except:
    print('Something went wrong.')
```

O Python começa executando a cláusula `try`. Se tudo for bem, ele ignora a cláusula `except` e prossegue. Se ocorrer uma exceção, o programa sai da cláusula `try` e executa a cláusula `except`.

Lidar com exceções usando uma instrução `try` chama-se capturar uma exceção. Neste exemplo, a cláusula `except` exibe uma mensagem de erro que não é muito útil. Em geral, a captura de uma exceção oferece a oportunidade de corrigir o problema ou tentar novamente, ou, ao menos, de terminar o programa adequadamente.
