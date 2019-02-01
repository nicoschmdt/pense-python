## 11.8 - Depuração

Ao trabalhar com conjuntos de dados maiores, depurar exibindo e verificando a saída à mão pode ser trabalhoso. Aqui estão algumas sugestões para depurar grandes conjuntos de dados:



##### Reduza a entrada

  &nbsp;&nbsp;&nbsp;&nbsp;Se for possível, reduza o tamanho do conjunto de dados. Por exemplo, se o programa lê um arquivo de texto, comece com apenas as 10 primeiras linhas, ou com o menor exemplo que puder encontrar. Você pode editar os próprios arquivos ou alterar o programa para que leia só as primeiras n linhas (é melhor).

  &nbsp;&nbsp;&nbsp;&nbsp;Se houver um erro, você pode reduzir n ao menor [valor](09-glossario.md#valor) que manifeste o erro, e então aumentá-lo gradativamente até encontrar e corrigir o erro.

##### Verifique os resumos e tipos

  &nbsp;&nbsp;&nbsp;&nbsp;Em vez de imprimir e verificar o conjunto de dados inteiro, pense em exibir resumos dos dados: por exemplo, o número de itens em um [dicionário](09-glossario.md#dicionário) ou o total de uma lista de números.

  &nbsp;&nbsp;&nbsp;&nbsp;Uma causa comum de erros em tempo de execução são valores de tipo incompatível. Para depurar essa espécie de erro, muitas vezes basta exibir o tipo de um valor.

##### Crie autoverificações

  &nbsp;&nbsp;&nbsp;&nbsp;É possível escrever o código para verificar erros automaticamente. Por exemplo, se estiver calculando a média de uma lista de números, você pode verificar se o resultado não é mais alto que o maior elemento da lista ou mais baixo que o menor. Isso é chamado de “verificação de sanidade” porque descobre resultados “insanos”.

  &nbsp;&nbsp;&nbsp;&nbsp;Outro tipo de verificação compara os resultados de dois cálculos diferentes para ver se são consistentes. Isso é chamado de “verificação de consistência”.

##### Formate a saída

  &nbsp;&nbsp;&nbsp;&nbsp;A formatação da saída para depuração pode facilitar a [busca](09-glossario.md#busca) de erros. Vimos um exemplo em “Depuração”, na página 172. O módulo `pprint` apresenta uma função `pprint` que exibe tipos integrados em um formato mais legível para humanos (`pprint` é a abreviação de “pretty print” (bela exibição)).



Reforçando, o tempo que você passar construindo o scaffolding (o andaime) pode reduzir o tempo de depuração.

