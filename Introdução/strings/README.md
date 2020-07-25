# Strings 

Em C, uma string é um vetor de caracteres terminadas com '\0'. Em que, '\0' pode ser lido como um caractere nulo. Observe o exemplo abaixo que apresenta como uma string pode ser declarada e como, internamente, essa string é armazenada.

		int main(int argc, const char *argv[ ]){
			
			char c[ ] = "hello";
			
			return 0;
		}

[![](https://www.tutorialspoint.com/cprogramming/images/string_representation.jpg)](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.tutorialspoint.com%2Fcprogramming%2Fc_strings.htm&psig=AOvVaw1grWjDOFTncwRhwW1TU86c&ust=1595784002563000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCLjmvuv06OoCFQAAAAAdAAAAABAD)

É importante notar que, devido à necessidade do '\0', os vetores que armazenam strings devem ter sempre uma posição a mais do que o número de caracteres a serem armazenados. 

Porém, quando a string é uma constante, o espaço adicional para o caracter '\0' é alocado automaticamente pelo compilador. 

## Leitura de Strings

Você pode utilizar a função *scanf()* para ler uma string. Mas existem outras funções que também realizam essa tarefa. Observe os exemplos.

		int main(int argc, const char *argv[ ]){
			
			char nome[20];
			printf("Informe seu nome: ");
			scanf("%s", nome);
			printf("Seu nome é: %s", nome);
			
			return 0;
		}

A saída do programa será:
>Informe seu nome: Maria Eduarda
>Seu nome é: Maria

Note que, apenas "Maria" foi armazenado na memória na variável *nome*. Isso acontece porque há um espaço depois de "Maria". 

Lembre-se que, a função *scanf()* lê uma sequência de caracteres até encontrar um espaço em branco(espaço, linha nova, tab, etc.).

#### Como ler uma linha de texto?

Podemos utilizar duas funções: *fgets()* e *puts*. Observe abaixo os exemplos.

		int main(int argc, const char *argv[ ]){
			
			char nome[20];
			printf("Informe seu nome: ");
			fgets(nome, sizeof(nome), stdin);
			printf("Nome: ");
			puts(nome);
			
			return 0;
		}

A saída do programa será:
>Informe seu nome: Maria Eduarda
>Nome: Maria Eduarda

>Nota: 
> A função sizeof(nome) irá retornar 20. Portanto, podemos utilizar no máximo 30 caracteres como entrada, que é o tamanho da string nome.

## Manipulação de Strings

Como a string não é um tipo de dado básico da linguagem C, operações simples como atribuição e comparação não podem ser feitas diretamente com os operadores disponíveis. 

		int main(int argc, const char *argv[ ]){
			
			char nome[20];
			nome = "Maria Eduarda"; //Erro! Tipo array não é atribuível.
			
			return 0;
		}

No exemplo abaixo, apesar de x e y terem o mesmo valor e, portanto, serem iguais, a saída será: um == um resulta em falso. Isso acontece porque na expressão x==y não estamos comparando o conteúdo dos vetores x e y, mas sim seus endereços que, obviamente, devem ser diferentes. 

		int main(int argc, const char *argv[ ]){
			char x[ ] = "um";
			char y[ ] = "um";
			
			printf("%s == %s resulta em %s", x, y, x==y ? "verdade" : "falso");
			
			return 0;
		}

Para fazermos a atribuição e comparação de strings, podemos utilizar funções da biblioteca "string.h" ou utilizar a indexação para isso. Observe exemplos:

1. Utilizando indexação

		int main(int argc, const char *argv[ ]){
			char x[5];
			char y[5] = "dois";
			
			for(int i=0; i<5; i++) x[i]=y[i];
			
			puts(x);
			
			return 0;
		}

2. Utlizando a função strcpy() para copiar o conteudo de uma string para outra string.

		#include <stdio.h>
		#include <string.h>
		int main(int argc, const char *argv[ ]){
			char x[5];
			char y[5] = "dois";
			
			strcpy(x, y);
			
			puts(x);
			
			return 0;
		}

