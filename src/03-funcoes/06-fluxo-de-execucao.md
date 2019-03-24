## 3.6 - Fluxo de execução

Para garantir que uma [função](13-glossario.md#função) seja definida antes do seu primeiro uso, é preciso saber a ordem na qual as instruções serão executadas. Isso é chamado de [fluxo de execução](13-glossario.md#fluxo-de-execução).

A execução sempre começa na primeira instrução do programa. As instruções são executadas uma após a outra, de cima para baixo.

As definições de função não alteram o fluxo da execução do programa, mas lembre-se de que as instruções dentro da função não são executadas até a função ser chamada.

Uma [chamada de função](13-glossario.md#chamada-de-função) é como um desvio no fluxo de execução. Em vez de ir à próxima instrução, o fluxo salta para o [corpo](13-glossario.md#corpo) da função, executa as instruções lá, e então volta para continuar de onde parou.

Parece bastante simples, até você lembrar que uma função pode chamar outra. Enquanto estiver no meio de uma função, o programa pode ter que executar as instruções em outra função. Então, enquanto estiver executando a nova função, o programa pode ter que executar mais uma função!

Felizmente, o Python é bom em não perder o fio da meada, então cada vez que uma função é concluída, o programa continua de onde parou na função que o chamou. Quando chega no fim do programa, ele é encerrado.

Resumindo, nem sempre se deve ler um programa de cima para baixo. Às vezes faz mais sentido seguir o fluxo de execução.
