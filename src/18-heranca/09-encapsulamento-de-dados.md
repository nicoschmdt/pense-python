## 18.9 - Encapsulamento de dados

Os capítulos anteriores demonstram um plano de desenvolvimento que poderíamos chamar de “projeto orientado a objeto”. Identificamos os objetos de que precisamos – como Point, Rectangle e Time – e definimos classes para representá-los. Em cada caso há uma correspondência óbvia entre o objeto e alguma entidade no mundo real (ou, pelo menos, no mundo matemático).

Mas, às vezes, é menos óbvio quais objetos você precisa e como eles devem interagir. Nesse caso é necessário um plano de desenvolvimento diferente. Da mesma forma em que descobrimos interfaces de função por encapsulamento e generalização, podemos descobrir interfaces de classe por encapsulamento de dados.

A análise de Markov, de “Análise de Markov”, na página 200, apresenta um bom exemplo. Se baixar o meu código em [http://thinkpython2.com/code/markov.py](http://thinkpython2.com/code/markov.py), você vai ver que ele usa duas variáveis globais – suffix\_map e prefix – que são lidas e escritas a partir de várias funções.

```python
suffix_map = {}
prefix = ()
```

Como essas variáveis são globais, só podemos executar uma análise de cada vez. Se lermos dois textos, seus prefixos e sufixos seriam acrescentados às mesmas estruturas de dados (o que geraria textos interessantes).

Para executar análises múltiplas e guardá-las separadamente, podemos encapsular o estado de cada análise em um objeto. É assim que fica:

```python
class Markov:
    def __init__(self):
        self.suffix_map = {}
        self.prefix = ()
```

Em seguida, transformamos as funções em métodos. Por exemplo, aqui está process_word:

```python
def process_word(self, word, order=2):
    if len(self.prefix) < order:
        self.prefix += (word)
        return
    try:
        self.suffix_map[self.prefix].append(word)
    except KeyError:
        # se não houver entradas deste prefixo, crie uma.
        self.suffix_map[self.prefix] = [word]

    self.prefix = shift(self.prefix, word)
```

Transformar um programa como esse – alterando o projeto sem mudar o comportamento – é outro exemplo de refatoração (veja “Refatoração”, na página 70).

Este exemplo sugere um plano de desenvolvimento para projetar objetos e métodos:

1. Comece escrevendo funções que leiam e criem variáveis globais (quando necessário).

2. Uma vez que o programa esteja funcionando, procure associações entre variáveis globais e funções que as usem.

3. Encapsule variáveis relacionadas como atributos de objeto.

4. Transforme as funções associadas em métodos da nova classe.

Como exercício, baixe o meu código de Markov de [http://thinkpython2.com/code/markov.py](http://thinkpython2.com/code/markov.py) e siga os passos descritos acima para encapsular as variáveis globais como atributos de uma nova classe chamada Markov.

Solução: [http://thinkpython2.com/code/Markov.py](http://thinkpython2.com/code/Markov.py) (observe o M maiúsculo).
