## 7.7 - Depuração

Ao começar a escrever programas maiores, pode ser que você passe mais tempo depurando. Mais código significa mais possibilidades fazer erros e mais lugares para esconder defeitos.

Uma forma de cortar o tempo de depuração é “depurar por bisseção”. Por exemplo, se há 100 linhas no seu programa e você as verifica uma a uma, seriam 100 passos a tomar.

Em vez disso, tente quebrar o problema pela metade. Olhe para o meio do programa, ou perto disso, para um valor intermediário que possa verificar. Acrescente uma instrução print (ou outra coisa que tenha um efeito verificável) e execute o programa.

Se a verificação do ponto central for incorreta, deve haver um problema na primeira metade do programa. Se for correta, o problema está na segunda metade.

Cada vez que executar uma verificação assim, divida ao meio o número de linhas a serem verificadas. Depois de seis passos (que é menos de 100), você teria menos de uma ou duas linhas do código para verificar, pelo menos em teoria.

Na prática, nem sempre é claro o que representa o “meio do programa” e nem sempre é possível verificá-lo. Não faz sentido contar linhas e encontrar o ponto central exato. Em vez disso, pense em lugares no programa onde poderia haver erros e lugares onde é fácil inserir um ponto de verificação. Então escolha um lugar onde as possibilidades são basicamente as mesmas de que o defeito esteja antes ou depois da verificação.
