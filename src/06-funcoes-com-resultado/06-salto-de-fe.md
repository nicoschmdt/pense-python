## 6.6 - Salto de fé

Seguir o fluxo da execução é uma forma de ler programas, mas poderá ser trabalhoso demais. Uma alternativa é o que chamo de “salto de fé” (leap of faith). Ao chegar a uma chamada de função, em vez de seguir o fluxo de execução suponha que a função esteja funcionando corretamente e que está retornando o resultado certo.

Na verdade, você já está praticando este salto de fé quando usa funções integradas. Quando chama math.cos ou math.exp, você não examina o corpo dessas funções. Apenas supõe que funcionem porque as pessoas que as escreveram eram bons programadores.

O mesmo acontece ao chamar uma das suas próprias funções. Por exemplo, em “Funções booleanas”, na página 97, escrevemos uma função chamada is\_divisible que determina se um número é divisível por outro. Uma vez que estejamos convencidos de que esta função está correta – examinando o código e testando – podemos usar a função sem ver o corpo novamente.

O mesmo é verdade para programas recursivos. Quando chega à chamada recursiva, em vez de seguir o fluxo de execução, você deveria supor que a chamada recursiva funcione (devolva o resultado correto) e então perguntar-se: “Supondo que eu possa encontrar o fatorial de n-1, posso calcular o fatorial de n?”. É claro que pode, multiplicando por n.

Naturalmente, é um pouco estranho supor que a função funcione corretamente quando ainda não terminou de escrevê-la, mas é por isso que se chama um salto de fé!
