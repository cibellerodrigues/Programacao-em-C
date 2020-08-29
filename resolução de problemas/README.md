# Resolução de problemas

A ciência da computação trata de solucionar problemas por meio de um computador, sejam eles concretos ou abstratos. Para solucioná-los precisamos abordá-los de modo sistemático. E um sistema possível consiste de 4 passos:

1. Entender o problema;
2. Formular um modelo;
3. Desenvolver um algoritmo;
4. Revisar e testar a solução.

Para compreender essa abordagem, usaremos o problema de calcular o valor de uma n-ésima entrada da sequência de Fibonacci.

## Apresentando o problema

Fibonacci ou Leonardo de Pisa(1170-1250), um famoso matemático italiano, criou a sequência que leva seu nome a partir da observação do crescimento de uma população de coelhos. Os números descrevem a quantidade de casais em uma população de coelhos após n meses, partindo dos seguintes pressupostos:

1. No primeiro mês nasce somente um casal;
2. Casais amadurecem sexualmente após o segundo mês de vida;
3. Não há problemas genéticos no cruzamento consanguíneo;
4. Todos os meses, cada casal dá à luz a um novo casal;
5. Os coelhos nunca morrem.

Com essas condições inicia a construção da sequência:

1. No primeiro mês há apenas um casal de coelhos.
2. Como a maturidade sexual dos coelhos dá-se somente a partir do segundo mês de vida, no segundo mês continua havendo apenas 1 casal.
3. No terceiro mês teremos o nascimento de mais um casal, totalizando 2 casais. 
4. No quarto mês, com o nascimento de mais um casal, gerado pelo casal inicial, (visto que o segundo ainda não amadureceu sexualmente) teremos 3 casais.
5. No quinto mês, com o nascimento de dois novos casais gerados pelo casal 1 e pelo casal 2, totalizam-se 5 casais.

![enter image description here](https://s1.static.brasilescola.uol.com.br/be/e/coelhos%20fibonacci.jpg)

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
1. ![F(1) = 0, F(2) = 1](https://render.githubusercontent.com/render/math?math=F(1)%20%3D%200%2C%20F(2)%20%3D%201)
2. ![F(3) = F(2) + F(1) = 1 + 0 = 1](https://render.githubusercontent.com/render/math?math=F(3)%20%3D%20F(2)%20%2B%20F(1)%20%3D%201%20%2B%200%20%3D%201)
3. ![F(4) = F(3) + F(2) = 1 + 1 = 2](https://render.githubusercontent.com/render/math?math=F(4)%20%3D%20F(3)%20%2B%20F(2)%20%3D%201%20%2B%201%20%3D%202)
4. ![F(5) = F(4) + F(3) = 2 + 1 = 3](https://render.githubusercontent.com/render/math?math=F(5)%20%3D%20F(4)%20%2B%20F(3)%20%3D%202%20%2B%201%20%3D%203)

## Desenvolver um algoritmo

Agora que entendemos o problema e formulamos um modelo é hora de desenvolver um algoritmo. Um algoritmo é uma sequência precisa de instruções para resolver um problema.

Já que sabemos o que é um algoritmo, como podemos representá-los?

Há duas representações comumente usadas para um algoritmo, que são:

- Pseudo-código: É uma sequência simples e concisa de instruções em Português. Se assemelha com uma receita. Ao aprender a programar, é importante escrever pseudo-códigos pois ajuda a entender claramente o problema que você está tentando solucionar.

- Fluxograma: É uma forma gráfica de representar instruções.

Para exemplificar o uso dessas formas de representação de um algoritmo, seguem abaixo os exemplos para um algoritmo que soluciona o problema de preparação de bifes à milanesa.

### Pseudocódigo
```
1. Limpar a peça de carne
2. Fatiar a carne em bifes
3. Colocar farinha de rosca em um prato
4. Juntar 2 ovos e mexer
5. Repetir, para cada bife
    5.1 passar o bife na mistura de farinha, nos 2 lados
    5.2 levar bife à frigideira até dourar
    5.3 aguardar dourar, virando ambas as faces
    5.4 retirar o bife colocando em papel toalha para secar
    5.5 retirar do papel toalha e juntar numa travessa
6. Se tiver molho, coloque para acompanhamento
7. Senão, jogue queijo por cima
8. Servir 
```
### Fluxograma
[![](https://mermaid.ink/img/eyJjb2RlIjoiZ3JhcGggVERcblx0QVtMaW1wYXIgY2FybmVdIC0tPiBCW0ZhdGlhciBjYXJuZV1cbiAgICBCIC0tPiBDW0NvbG9jYXIgZmFyaW5oYV1cbiAgICBDIC0tPiBEW0JhbmhhciBub3Mgb3Zvc11cbiAgICBEIC0tPiBFe0jDoSBiaWZlc31cbiAgICBFIC0tPiB8U2ltfCBGW1Bhc3NhciBiaWZlIG5hIG1pc3R1cmFdXG4gICAgRiAtLT4gR1tGcml0YXIgYmlmZV1cbiAgICBHIC0tPiBIW0RvdXJhcl1cbiAgICBIIC0tPiBJW1NlY2FyXVxuICAgIEkgLS0-IEpbQ29sb2NhciBuYSB0cmF2ZXNzYV1cbiAgICBKIC0tPiBFXG5cdEUgLS0-IHxOw6NvfCBMe1RlbSBtb2xob31cbiAgICBMIC0tPiB8U2ltfCBNW0NvbG9jYSBtb2xobyBzb2JyZSBvcyBiaWZmZXNdXG4gICAgTCAtLT4gfE7Do298IE9bQ29sb2NhIHF1ZWlqb11cbiAgICBNIC0tPiBOW1NpcnZhXVxuICAgIE8gLS0-IE4iLCJtZXJtYWlkIjp7InRoZW1lIjoiZGVmYXVsdCJ9LCJ1cGRhdGVFZGl0b3IiOmZhbHNlfQ)](https://mermaid-js.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiZ3JhcGggVERcblx0QVtMaW1wYXIgY2FybmVdIC0tPiBCW0ZhdGlhciBjYXJuZV1cbiAgICBCIC0tPiBDW0NvbG9jYXIgZmFyaW5oYV1cbiAgICBDIC0tPiBEW0JhbmhhciBub3Mgb3Zvc11cbiAgICBEIC0tPiBFe0jDoSBiaWZlc31cbiAgICBFIC0tPiB8U2ltfCBGW1Bhc3NhciBiaWZlIG5hIG1pc3R1cmFdXG4gICAgRiAtLT4gR1tGcml0YXIgYmlmZV1cbiAgICBHIC0tPiBIW0RvdXJhcl1cbiAgICBIIC0tPiBJW1NlY2FyXVxuICAgIEkgLS0-IEpbQ29sb2NhciBuYSB0cmF2ZXNzYV1cbiAgICBKIC0tPiBFXG5cdEUgLS0-IHxOw6NvfCBMe1RlbSBtb2xob31cbiAgICBMIC0tPiB8U2ltfCBNW0NvbG9jYSBtb2xobyBzb2JyZSBvcyBiaWZmZXNdXG4gICAgTCAtLT4gfE7Do298IE9bQ29sb2NhIHF1ZWlqb11cbiAgICBNIC0tPiBOW1NpcnZhXVxuICAgIE8gLS0-IE4iLCJtZXJtYWlkIjp7InRoZW1lIjoiZGVmYXVsdCJ9LCJ1cGRhdGVFZGl0b3IiOmZhbHNlfQ)

### Variáveis
### Condicionais
### Laços
### O algoritmo de Fibonacci

## Revisar e testar a solução
