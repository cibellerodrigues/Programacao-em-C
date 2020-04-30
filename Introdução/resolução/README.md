# Resolução de problemas

A ciência da computação trata de solucionar problemas por meio de um computador, sejam eles concretos ou abstratos. Para solucioná-los precisamos abordá-los de modo sistemático. E um sistema possível consiste de 4 passos:

1. Entender o problema;
2. Formular um modelo;
3. Desenvolver um algoritmo;
4. Revisar e testar a solução.

Para compreender essa abordagem, usaremos o problema de calcular o valor de uma n-ésima entrada da sequência de Fibonacci.

## Entender o problema

É tolice responder uma pergunta na qual você não entendeu. Portanto, o primeiro passo para resolver qualquer problema é garantir que você entenda o problema que está tentando resolver. Para isso, você precisa perguntar:

- Quais dados/informações de entrada estão disponíveis?
- Quais dados de saída estou tentando gerar?
- O que eles representam?
- O que eu vou ter que realizar?
- Tenho tudo que preciso?

Para solucionar o problema proposto, questionaremos:

- Quais dados/informações de entrada estão disponíveis? Um número inteiro.
- Quais dados de saída estou tentando gerar? Um inteiro.
- O que eles representam? Uma posição na sequência e seu valor correspondente.
- O que eu vou ter que realizar? Descobrir o valor de saída a partir do valor de entrada.
- Tenho tudo que preciso? Sim. Pois sabemos o que devemos fazer e a sequência é: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597, 2584, ... 

## Formular o modelo

Sabendo o que é o problema, você precisa modelar a solução. Ou seja, como irá realizar o processamento para obtenção da saída a partir dos dados de entrada.

Se observar a sequência com cuidado é possível ver que um número é a soma dos dois antecessores. Matemáticamente podemos definir como:

![\left\{ \begin{matrix} F_1=&0 \\ F_2=&1 \\  F_n=&F_{n-1}&+&F_{n-2} \end{matrix} \right.](https://render.githubusercontent.com/render/math?math=%5Cleft%5C%7B%20%5Cbegin%7Bmatrix%7D%20F_1%3D%260%20%5C%5C%20F_2%3D%261%20%5C%5C%20%20F_n%3D%26F_%7Bn-1%7D%26%2B%26F_%7Bn-2%7D%20%5Cend%7Bmatrix%7D%20%5Cright.)


Assim, é possível calcular o valor relacionado a qualquer posição. Exemplo, o valor da posição 5 é calculado da forma seguinte:
1. $$F(1) = 0, F(2) = 1$$
2. $$F(3) = F(2) + F(1) = 1 + 0 = 1$$
3. $$F(4) = F(3) + F(2) = 1 + 1 = 2$$
4. $$F(5) = F(4) + F(3) = 2 + 1 = 3$$