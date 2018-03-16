## 11.8 - Depuração

Ao trabalhar com conjuntos de dados maiores, depurar exibindo e verificando a saída à mão pode ser trabalhoso. Aqui estão algumas sugestões para depurar grandes conjuntos de dados:

<dl>

<dt>Reduza a entrada</dt>

  <dd>Se for possível, reduza o tamanho do conjunto de dados. Por exemplo, se o programa lê um arquivo de texto, comece com apenas as 10 primeiras linhas, ou com o menor exemplo que puder encontrar. Você pode editar os próprios arquivos ou alterar o programa para que leia só as primeiras n linhas (é melhor).</dd>

  <dd>Se houver um erro, você pode reduzir n ao menor valor que manifeste o erro, e então aumentá-lo gradativamente até encontrar e corrigir o erro.</dd>

<dt>Verifique os resumos e tipos</dt>

  <dd>Em vez de imprimir e verificar o conjunto de dados inteiro, pense em exibir resumos dos dados: por exemplo, o número de itens em um dicionário ou o total de uma lista de números.</dd>

  <dd>Uma causa comum de erros em tempo de execução são valores de tipo incompatível. Para depurar essa espécie de erro, muitas vezes basta exibir o tipo de um valor.</dd>

<dt>Crie autoverificações</dt>

  <dd>É possível escrever o código para verificar erros automaticamente. Por exemplo, se estiver calculando a média de uma lista de números, você pode verificar se o resultado não é mais alto que o maior elemento da lista ou mais baixo que o menor. Isso é chamado de “verificação de sanidade” porque descobre resultados “insanos”.</dd>

  <dd>Outro tipo de verificação compara os resultados de dois cálculos diferentes para ver se são consistentes. Isso é chamado de “verificação de consistência”.</dd>

<dt>Formate a saída</dt>

  <dd>A formatação da saída para depuração pode facilitar a busca de erros. Vimos um exemplo em “Depuração”, na página 172. O módulo `pprint` apresenta uma função `pprint` que exibe tipos integrados em um formato mais legível para humanos (`pprint` é a abreviação de “pretty print” (bela exibição)).</dd>

</dl>

Reforçando, o tempo que você passar construindo o scaffolding (o andaime) pode reduzir o tempo de depuração.

