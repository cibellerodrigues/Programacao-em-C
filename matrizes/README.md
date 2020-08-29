# Matrizes

Uma matriz é conhecida como um vetor de vetores ou um vetor 2D cujo os elementos são homogêneos e distribuídos em linhas e colunas. 

Se A é uma matriz mxn então suas linhas são indexadas de 0 a m-1 e suas colunas de 0 a n-1. Observe o exemplo.

[![Matrix](https://cdn.programiz.com/sites/tutorial2program/files/java-2d-array.jpg "Matrix")](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.programiz.com%2Fjava-programming%2Fmultidimensional-array&psig=AOvVaw0pC1M5WfTlNPueiysx-Ige&ust=1596392869318000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCKjI55_R-uoCFQAAAAAdAAAAABAD "Matrix")

## Inicialização de uma matriz

Tecnicamente, matrizes não são suportadas diretamente em C e, para criar uma matriz, devemos declarar um vetor cujos elementos são vetores.

		int A[3][4];

Essa declaração cria um vetor A cujos elementos A[0], ..., A[3] são vetores contendo cada um deles 4 elementos do tipo int.

1. Declarações válidas 

		int abc[2][2] = {1, 2, 3, 4};
		int abc[ ][2] = {1, 2, 3, 4};

2. Declarações inválidas

		int abc[][] = {1, 2, 3 ,4 };
		int abc[2][] = {1, 2, 3 ,4 };

	> Essas declarações são inválidas pois é necessário especificar a segunda dimensão.

## Armazenamento de dados em matrizes

Para processar uma matriz, utilizamos laços for encadeados: um para variar o índice das linhas e outro para o índice das colunas. Portanto, podemos armazenar elementos em uma matriz das seguintes maneiras:

1. 

		A[2][3];
		A[1][2] = 10;

2. 

		#include<stdio.h>
		int main(){
			int abc[5][4];
			int i, j;
			for(i=0; i<5; i++) {
				for(j=0;j<4;j++) {
					printf("Insira um valor para abc[%d][%d]:", i, j);
					scanf("%d", &abc[i][j]);
				}
			}
			return 0;
		}


## Passando Matrizes a Funções

Assim como em vetores, o nome de uma matriz representa o endereço que ela ocupa na memória. Então, quando passamos uma matriz como argumento, a função tem acesso direto aos valores armazenados nessa matriz. 

			#include <stdio.h>

			void imprimir(int matriz[2][2]){
				int i, j;

				for(i = 0; i<2; i++){
					for(j=0; j<2; j++){
						printf("%d", matriz[i][j]);
					}
					printf('\n');
				}
		}
