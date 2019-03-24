## 16.4 - Prototipação versus planejamento

O plano de desenvolvimento que estou demonstrando chama-se “[protótipo e correção](06-glossario.md#protótipo-e-correção)”. Para cada função, escrevi um protótipo que executa o cálculo básico e então testa a função, corrigindo erros no decorrer do caminho.

Esta abordagem pode ser eficaz, especialmente se você ainda não tem uma compreensão profunda do problema. Porém, as correções incrementais podem gerar código que se complica desnecessariamente (pois trata de muitos casos especiais) e pouco confiáveis (já que é difícil saber se todos os erros foram encontrados).

Uma alternativa é o [desenvolvimento planejado](06-glossario.md#desenvolvimento-planejado), no qual a compreensão de alto nível do problema pode facilitar muito a programação. Neste caso, descobre-se que um objeto Time é, na verdade, um número de três dígitos na base 60 (veja [http://en.wikipedia.org/wiki/Sexagesimal](http://en.wikipedia.org/wiki/Sexagesimal))! O atributo second é a “coluna de unidades”, o atributo minute é a “coluna dos 60”, e o atributo hour é a “coluna do 3.600”.

Quando escrevemos `add_time` e `increment`, estávamos na verdade fazendo adições na base 60, e por isso transportávamos os resultados de uma coluna à seguinte.

Essa observação sugere outra abordagem para o problema inteiro – podemos converter objetos `Time` em números inteiros e aproveitar o fato de que o computador sabe trabalhar com aritmética de números inteiros.

Aqui está uma função que converte objetos `Time` em números inteiros:


```python
def time_to_int(time):
    minutes = time.hour * 60 + time.minute
    seconds = minutes * 60 + time.second
    return seconds
```

E aqui está uma função que converte um número inteiro em um `Time` (lembre-se de que `divmod` divide o primeiro argumento pelo segundo e devolve o quociente e o resto como uma tupla):

```python
def int_to_time(seconds):
    time = Time()
    minutes, time.second = divmod(seconds, 60)
    time.hour, time.minute = divmod(minutes, 60)
    return time
```

Você pode ter que pensar um pouco e fazer alguns testes, para se convencer de que essas funções estão corretas. Um modo de testá-las é ver se `time_to_int(int_to_time(x)) == x` para muitos valores de `x`. Este é um exemplo de uma verificação de consistência.

Uma vez que esteja convencido de que estão corretas, você pode usá-las para reescrever `add_time`:

```python
def add_time(t1, t2):
    seconds = time_to_int(t1) + time_to_int(t2)
    return int_to_time(seconds)
```

Esta versão é mais curta que a original, e mais fácil de verificar. Como exercício, reescreva `increment` usando `time_to_int` e `int_to_time`.

Em algumas situações, converter da base 60 para a base 10 e de volta é mais difícil que apenas lidar com as horas. A conversão de base é mais abstrata; nossa intuição para lidar com valores temporais é melhor.

No entanto, se tivermos discernimento para lidar com horas como números de base 60 e investirmos esforço em escrever as funções de conversão (`time_to_int` e `int_to_time`), chegamos a um programa que é mais curto, mais fácil de ler e depurar, e mais confiável.

Também é mais fácil acrescentar recursos depois. Por exemplo, imagine subtrair dois objetos `Time` para encontrar a duração entre eles. Uma abordagem ingênua seria implementar a subtração com transporte. Porém, usar funções de conversão seria mais fácil e, provavelmente, mais correto.

Ironicamente, tornar um problema mais difícil (ou mais geral) facilita (porque há menos casos especiais e menos oportunidades de erro).
