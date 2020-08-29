# Bibliotecas em C 

Todo programa em C, antes de chegar ao compilador é tratado por um módulo adicional denominado preprocessador. 

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/usando%20bibliotecas/1.png)

Antes que o programa seja analisado pelo compilador o preprocessador pode realizar uma série de modificações. Por meio de diretivas de preprocessamento podemos realizar essas modificações. 

## A Diretiva #include

Em C, a diretiva *#include* informa ao preprocessador para inserir o conteúdo de outro arquivo no código fonte a partir do ponto que a diretiva é encontrada. 

A sintaxe para utilizar a diretiva #include pode ser definida de duas maneiras: 

		#include <header_file>

		#include "header_file"

* header_file (arquivo de cabeçalho): consiste em um arquivo em C que termina em ".h" e contém declarações de macros, funções e structs que podem ser compartilhadas.  

* A diferença entre as duas sintaxes é que se um arquivo de cabeçalho estiver incluído em <>, o preprocessador procurará um caminho de diretório predeterminado para localizar o arquivo de cabeçalho. Se estiver entre "", o preprocessador procurará o arquivo de cabeçalho no mesmo diretório do código fonte. 

## Utilizando Bibliotecas

Veremos algumas bibliotecas, a lista de algumas funções desta biblioteca e como utilizá-las.

* Stdio.h

|   função |   utilidade|
| ------------ | ------------ |
| printf   |  Escrita formatada |
| scanf  |   Leitura formatada |
| sprintf | Escrita de string formatada|
| sscanf  | Leitura de string formatada|
|putchar | Escrita de character|
| getchar | Leitura de character |
| gets | Leitura de string |
| perror| Exibir mensagem de erro |

		#include <stdio.h>
		
		int main(int argc, const char *argv[ ]){
			 char buffer[20], nome[10];
			 scanf("%s", nome);
			 sprintf(buffer, "Olá %s!", nome);
			 printf("%s", buffer);
			 
			 putchar('\n');
			 
			 char s [] = "2 alunos acima da media e 3 alunos abaixo da media";
			 char str [10],str2 [10];
			 int i, j;
			 
			 sscanf (s,"%d %*s %s %*s %*s %*s %d %*s %s", &i, str, &j, str2);
			 printf("%d %s %d %s", i, str, j, str2);
			 
			 return 0;
		}

A saída do programa será: 

> Olá, seu_nome!
>
> 2 acima 3 abaixo

* Stdlib.h 

|  função | utilidade  |
| ------------ | ------------ |
|  exit |  Sair do programa |
|  abs |   Valor absoluto de um número inteiro|
| div | Divisão inteira|
| rand| Gerador de números pseudo-aleatorios|
| atoi | Converte string para inteiro|
|calloc | Alocar e limpar um bloco de memória|
|malloc | Alocar bloco de memória|
|realloc | Realocar bloco de memória|

		#include <stdio.h>
		#include <stdlib.h>
		
		int main(int argc, const char *argv[ ]){
			char *ch = (char*)malloc(10 * sizeof(char));
			
			if(ch == NULL) exit(0);
			else{
				ch = "1278";
				int at = atoi(ch);
				printf("%d", at);
			}
			return 0;
		}

A saída do programa será:
 
> 1278

* Math.h

|   função| utilidade  |
| ------------ | ------------ |
|  log |   Logaritmo natural|
| log10 | Logaritmo comum|
| modf| Separa um número natural em duas partes|
|pow | Potência|
|sqrt| Raiz quadrada|
|cos| Cosseno|
|sin| Seno|


		#include <stdio.h>
		#include <math.h>
		
		int main(int argc, const char *argv[ ]){
			int a = pow (10, 2);
			int b = sqrt(25);
			
			printf("%d %d", a, b);
			return 0;
		}

A saída do programa será: 

> 100 5


## Projetando bibliotecas

Para criar uma biblioteca é necessário seguir os passos abaixo:

1.  Crie uma INTERFACE para sua biblioteca: mylib.h

		#define erro "Mensagem de erro"
		int sum(int a, int b){
			return a + b;
		}
		
		void msg_erro(){
			printf("%s\n", erro);
		}

2. Utilize o arquivo .h em outro programa

		#include <stdio.h>
		#include "mylib.h"
		
		int main(int argc, const char *argv[ ]){
			msg_erro();
			result = sum(4, 6);
			
			printf("%d", result);
			
			return 0;
		}

