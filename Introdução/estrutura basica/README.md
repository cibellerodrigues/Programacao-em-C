#A maneira que C trabalha

C é uma linguagem para criar programas rápidos. É com ela que todos sistemas básicos são construı́dos. Abaixo estão listados os passos básicos para a construção de um programa.

1. Criar código fonte

        #include <stdlib.h>
        #include <stdio.h>
       
	   int main(int argc, char const *argv[]){
        	puts("Hello World!");
        	return EXIT_SUCESS;
        }
2. Compilar

 	**$ gcc nome_do_arquivo.c -o nome_do_executavel** 

3. Executar

	**$ ./nome_do_executavel**

## Estrutura de um programa em C

1. Comentário serve para descrever o propósito do código.
```c
/* Para comentar
	diversas
	linhas
*/

// Para comentar uma única linha
```

2.  Inclusão de bibliotecas para reutilizar código.

	`#include <biblioteca>` torna disponível as funções implementadas na biblioteca da linguagem. 
	
	`#include "biblioteca"` torna disponível as funções implementadas na biblioteca do usuário. 

3. Função main(). Função que é chamada no inı́cio da execução do programa.

	Pode receber valores durante a execução. Veremos exemplos depois.

	Deve retornar um inteiro

	Deve ter seu código envolto entre chaves
