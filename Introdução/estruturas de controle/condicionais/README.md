#Comandos de Decisão

Todos os programas apresentados até agora possuem estrutura sequencial: as instruções são executadas uma após a outra na ordem dada. Porém, a maioria dos programas possui uma estrutura mais complicada, na qual instruções podem ou não serem executadas dependendo de certas condições. 

##Expressões lógicas

Para gerar um valor lógico em C, utilizamos operadores relacionais. O resultado da avaliação de um operador relacional é 0 se a comparação é falsa e 1 se é verdadeira.

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/condicionais/1.png)

Além dos operadores relacionais, C também oferece operadores lógicos. 

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/condicionais/2.png)

##Decisão simples

Em C, a estrutura condicional é codificada da seguinte forma: 

			if( condição ) comando 1; else comando2; 

Como obtemos o maior valor entre dois números? Antes de pensar no código em C, observe o fluxograma abaixo. 

[![](https://mermaid.ink/img/eyJjb2RlIjoiZ3JhcGggVERcblx0QVtYID0gMTBdIC0tPlxuICBCW1kgPSA1XSAtLT5cblx0Q3tYID49IFl9XG5cdEMgLS0-fHZlcmRhZGV8IERbbWFpb3IgPSBYXVxuXHRDIC0tPnxmYWxzb3wgRVttYWlvciA9IFldXG5cdFx0XHRcdFx0IiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)](https://mermaid-js.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiZ3JhcGggVERcblx0QVtYID0gMTBdIC0tPlxuICBCW1kgPSA1XSAtLT5cblx0Q3tYID49IFl9XG5cdEMgLS0-fHZlcmRhZGV8IERbbWFpb3IgPSBYXVxuXHRDIC0tPnxmYWxzb3wgRVttYWlvciA9IFldXG5cdFx0XHRcdFx0IiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)

Agora, temos o código em C: 

			int main(int argc, const char *argv[ ]){
				int x = 10, y = 5, maior;
				
				if( x >= y) maior = x; else maior = y;
				
				return 0;
			}

Passo a passo de execução de um condicional em C: 

* avaliamos a **condição**, que deve ser uma expressão lógica;

* se a **condição** for verdadeira, executa apenas o *comando1;*

* senão, executa apenas o *comando2*.

###Operador condicional

C oferece também um operador que proporciona uma forma mais compacta de se representar uma decisão simples. O operador condicional, cuja sintaxe é

			 condição ? expressão1 : expressão2;

Resolveremos o problema anterior utilizando operador condicional. Observe o script abaixo.

			int main(int argc, const char *argv[ ]){
				int x = 10, y = 5, maior;
				
				maior = x >= y ? x : y;
				
				return 0;
			}

Passo a passo de execução de um operador condicional em C: 

* avalia a condição;

* se ela for verdadeira, o resultado final é o valor da *expressão1*;

* senão, o resultado final é o valor da *expressão2*.

###Condicionais Aninhados e Encadeados

Como vimos, a estrutura condicional serve para selecionar e executar um entre dois comandos alternativos. É possível que, algumas vezes, um destes comandos alternativos (ou ambos) sejam também condicionais. 

		if( condição ) /*  principal */
			if ... /* aninhado */
		else
			if ... /*encadeado */

Para compreendermos essa estrutura, observe abaixo o script para classificação de um triângulo de acordo com suas medidas. 

		int main(int argc, char const *argv[ ]){
			float a, b, c;
			printf("Informe três valores:\n ");
			scanf("%f %f %f", &a, &b, &c);
			
			if(a < b + c && b < a + c &&  c < a + b){
				printf("É um triângulo ");
				if(a==b && b==c) printf("equilatero\n");
				else if(a == b || a==c || b==c) printf("isosceles\n");
				else printf("escaleno\n");
			}
			
			return 0;
		}

Vale relembrar as seguintes informações: 

* Para que três números representem os lados de um triângulo é necessário que cada um deles seja menor que a soma dos outros dois.

* Um triângulo é equilátero se tem os três lados iguais, isóceles se tem apenas dois lados iguais e escaleno se tem todos os lados distintos. 

##Decisão Múltipla

A estrutura de decisão múltipla é bastante adequada quando precisamos escolher uma entre várias alternativas previamente definidas. A decisão múltipla tem a seguinte sintaxe: 

		switch( expressão ){
			case constante1 : comando1; break;
			case constante2 : comando2; break;
			...
			case constanten : comandon; break
			default : comando;
		}

Funciona da seguinte maneira: 

* Avalia a expressão, que deve ser do tipo char ou int;

* Encontra o case cuja constante é igual ao valor da expressão e executa todos os comandos seguintes até encontrar um comando break;

* Se não existe tal caso, executa todas as instruções associadas ao caso default. 

Se dois casos não são separados por um comando break, dizemos que o controle "vaza" de um caso para o outro, ou seja, quando o primeiro caso é selecionado para execução, não apenas o comando associado a ele é executado, mas também o comando associado ao segundo. 

Para demonstrar o uso da estrutura de decisão múltipla, criaremos um script para uma calculadora simples. Veja abaixo.

		int main(int argc, char const *argv[ ]){
			float x, y;
			char op;
			printf("\n Expressão? ");
			scanf("%f %c %f", &x, &op, &y);
			
			switch(op){
				case '+' : printf("\n valor = %.2f", x+y); break;
				case '-' : printf("\n valor = %.2f", x-y); break;
				case '*' : printf("\n valor = %.2f", x*y); break;
				case '/' : printf("\n valor = %.2f", x/y); break;
				default  : break;
			}
		}
