# Comandos de Repetição

Os comandos de repetição nos permitem executar um mesmo trecho de código por determinadas vezes. Em C, veremos que existem 3 estruturas de repetição. 

## Expressões Compactas

C oferece uma forma compacta para escrever expressões. Observe a tabela abaixo.

|  Expressão               |   Forma Compactada        |
| --------------------------- | ---------------------------------- |
|  x = x + y                   |  x += y                               |
|  x = x - y                    |  x -= y                                |
|  x = x * y                    |  x *= y                               |
|  x = x / y                    |  x/= y                                 |
|  x = x % y                  |  x%= y                               |

### Incremento e decremento

Podemos também compactar expressões que incrementam e decrementam o valor de uma variável. 	Esses operadores são unários e podem ser utilizados tanto na forma pré-fixa quanto pós-fixa. Observe a tabela abaixo.

|   Pré-fixa | Pós-fixa  |
| ------------ | ------------ |
|   ++x       |   x++        |
|   - -x        |   x- -         |

* Na forma pré-fixa, a variável é alterada e, depois, seu valor é usado.

* Na forma pós-fixa, o valor da variável é usado e, depois, ela é alterada. 

## Declarações while

A declaração *while* tem seu funcionamento controlado por uma única expressão, cujo valor deve ser verdadeiro para que o comando seja repetido. Essa estrutura tem a seguinte forma: 

		while( condição ) comando;

Para exemplificar, considere o seguinte problema. 

1. Dado um número natural, exibir os seus digitos. Por exemplo, dado o número 7896 como entrada, o programa deverá exibir como saída 6, 9, 8 e 7 respectivamente. 

		int main( int argc, char const *argv [ ]){
			unsigned a, b;
			scanf("%u", &a);
			
			printf("\n os seus digitos são: ");
			while( a != 0){
				b = a % 10;
				a/= 10;
				printf("%u", b);
			}
			return 0;
		}

## Declarações for

Na estrutura for a sua estrutura é controlada por uma variável que conta a quantidade de vezes que o comando é executado. Essa estrutura tem a seguinte forma: 

		for (inicialização; condição; alteração) comando;

Em suma, temos: 

* **inicialização:** expressão que atribui um valor inicial ao contador;

* **condição:** verifica se a contagem chegou até o fim;

* **alteração:** modifica o valor do contador.

Para exemplificar, considere o seguinte problema: 

1. Exibir, em sequência, os inteiros de 0 a n.

		int main(int argc, char const *argv[ ]){
			int n;
			scanf("%d", &n);
			
			for(int i =0; i<= n; i++){
				printf("%d ", i);
			}
			return 0;
		}

## Declarações do while

A estrutura de repetição do while é bastante semelhante à *while*. A diferença é que no *do while* a condição é verificada somente depois que o comando é executado. Assim, diferente do *while*, o comando é executado pelo menos uma vez. Essa estrutura tem a seguinte forma:

		do{ comando; }while( condição );

Para exemplificar, considere o seguinte problema. 

1. Dado um número natural *n*, calcule o somatório de 1 até n. 

		int main( int argc, char const *argv[ ]){
			unsigned n, somatorio = 0;
			scanf("%u", &n);
			
			do{
				somatorio+=n; 
				n--;
			}while(n > 0);
			
			printf("%u\n", somatorio);
			
			return 0;
		}
