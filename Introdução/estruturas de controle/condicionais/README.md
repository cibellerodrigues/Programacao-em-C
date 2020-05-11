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