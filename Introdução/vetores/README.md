# Vetores

Um vetor é uma coleção de variáveis homogêneas que ocupam posições consecutivas de memória. Cada uma dessas variáveis é denominada *elemento* e é identificada por um *índice*. 

[![](https://media.geeksforgeeks.org/wp-content/uploads/C-Arrays.jpg)](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.geeksforgeeks.org%2Fc-sharp-arrays%2F&psig=AOvVaw3VlI1NAp4-8E3Nroxc-GMv&ust=1593520105658000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCODm86ODp-oCFQAAAAAdAAAAABAD)

Em C os vetores são sempre indexados a partir do zero e, portanto, o último elemento de um vetor de tamanho n ocupa a posição n-1 do vetor.

## Utilização de vetores em C

Para criar um vetor em C, basta declarar uma variável com sufixo [n], sendo n uma constante indicando o número de elementos a serem alocados no vetor. 

		int main(int argc, const char *argv[ ]){
			int v[10];
			
			return 0;
		}

No exemplo acima, temos a palavra reservada *int* que indica que o vetor *v* é um grupo de variáveis inteiras e o sufixo [10] especifica que esse grupo possui 10 elementos. 

[![](https://docs.oracle.com/javase/tutorial/figures/java/objects-tenElementArray.gif)](https://www.google.com/url?sa=i&url=https%3A%2F%2Fdocs.oracle.com%2Fjavase%2Ftutorial%2Fjava%2Fnutsandbolts%2Farrays.html&psig=AOvVaw1oSVkebpLQ8KbJJVys5khS&ust=1593524572711000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCODanuSTp-oCFQAAAAAdAAAAABAD)

Em geral, um vetor *v* pode ser indexado com qualquer expressão cujo valor seja do tipo integral. Essa expressão pode ser uma simples constante, uma variável ou então uma expressão propriamente dita, contendo operadores, constantes e variáveis. 

		int main(int argc, const char *argv[ ]){
			int i = 3;
			int v[10];
			
			v[i%3] = 10;
			v['B' - 'A'] = 20;
			v[i - 1] = 30;
			v[i] = 40;
			v[i + 1] = 50;
		
			return 0;
		}

[![](https://secureservercdn.net/160.153.138.219/b79.d22.myftpupload.com/wp-content/uploads/2015/07/array-and-array-index-representation.png)](https://www.google.com/url?sa=i&url=https%3A%2F%2Fcodeforwin.org%2F2015%2F07%2Fc-program-to-read-and-print-elements-in-array.html&psig=AOvVaw1oSVkebpLQ8KbJJVys5khS&ust=1593524572711000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCODanuSTp-oCFQAAAAAdAAAAABAJ)

Como visto acima, podemos inicializar nossos vetores em C. Vetores estáticos e dinamicos são inicializados automaticamente com 0 pelo compilador. 

		int main(int argc, int argv[ ]){
			static float moeda[5] = {1.00, 0.50, 0.25}
			
			return 0;
		}

Os valores são armazenados a partir da posição 0 do vetor, na ordem em que são fornecidos. 

Se a lista de valores iniciais tem mais elementos que a capacidade do vetor, ocorre um erro de compilação. Entretanto, se tem menos que o reservado, as posições excedentes do vetor permanecem zeradas.

Podemos também declarar vetores com tamanho ímplicito. Observe abaixo.

		int main(int argc, const char *argv[ ]){
			char v[] = {'a', 'b', 'c', 'd'};
			
			return 0;
		}

Como o tamanho é omitido, o compilador cria o vetor *v* com quatro posições. 

### Parâmetros do tipo vetor

Para acessar o endereço de memória de um vetor, ao invés de escrever-mos &vetor[0], utilizamos o nome atribuido a ele. Por exemplo, dado um vetor *v[10]*, para acessar seu endereço basta utilizar *v*.

		int main(int argc, const char *argv[ ]){
			int x[3];
			printf("%p", x);
			return 0;
		}

O formato %p é usado em C para a exibição de endereços.

Quando passamos um vetor como argumento a uma função estamos na verdade passando seu endereço. E, ao contrário do que ocorre com outros tipos, a passagem de vetores é feita por referência. 

	void imprimir(int vetor[], int len){ 
		for(int i = 0; i < len; i++)
		printf("%d ", vetor[i]);
	}
		
	int main(int argc, const char *argv[]) {
		int vetor[5] = {1, 2, 3, 4, 5};
		
		imprimir(vetor, 5);
		
		return 0;
	}