## 14.9 - Escrevendo módulos

Qualquer arquivo que contenha código do Python pode ser importado como um módulo. Por exemplo, vamos supor que você tenha um arquivo chamado `wc.py` com o seguinte código:

```python
def linecount(filename):
    count = 0
    for line in open(filename):
        count += 1
    return count

print(linecount('wc.py'))
```

Quando este programa é executado, ele lê a si mesmo e exibe o número de linhas no arquivo, que é 7. Você também pode importá-lo desta forma:

```python
>>> import wc
7
```

Agora você tem um objeto de módulo wc:

```python
>>> wc
<module 'wc' from 'wc.py'>
```

O objeto de módulo fornece o linecount:

```python
>>> wc.linecount('wc.py')
7
```

Então é assim que se escreve módulos no Python.

O único problema com este exemplo é que quando você importa o módulo, ele executa o código de teste no final. Normalmente, quando se importa um módulo, ele define novas funções, mas não as executa.

Os programas que serão importados como módulos muitas vezes usam a seguinte expressão:

```python
if __name__ == '__main__':
    print(linecount('wc.py'))
```

`__name__` é uma variável integrada, estabelecida quando o programa inicia. Se o programa estiver rodando como um script, `__name__` tem o valor `'__main__'`; neste caso, o código de teste é executado. Do contrário, se o módulo está sendo importado, o código de teste é ignorado.

Como exercício, digite este exemplo em um arquivo chamado wc.py e execute-o como um script. Então execute o interpretador do Python e import wc. Qual é o valor de `__name__` quando o módulo está sendo importado?

Atenção: se você importar um módulo que já tenha sido importado, o Python não faz nada. Ele não relê o arquivo, mesmo se tiver sido alterado.

Se quiser recarregar um módulo, você pode usar a função integrada `reload`, mas isso pode causar problemas, então o mais seguro é reiniciar o interpretador e importar o módulo novamente.
