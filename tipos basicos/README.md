# Tipos básicos

Um programa em C pode ser definido como um conjunto de **comandos** e **dados**.

* Comandos: operações disponíveis no computador. 

* Dados: valores a serem manipulados pelas operações.

	* Variáveis: valores que podem sofrer alterações.

	* Constantes: valores imutáveis.

## Tipos de dados básicos do C

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/tipos%20basicos/1.png)

* **char** é para armazenar caracteres. Mas, por exemplo, o caractere 'A' não é armazenado assim. Armazena-se um inteiro pequeno que corresponde a ele, no caso 65. Isso ocorre devido a uma limitação do computador, que só sabe trabalhar com números. Assim, qualquer coisa que não seja número tem que ser convertida para um. A primeira conversão de caracteres em números pode ser vista na tabela ASCII.

* **int** é para armazenar números inteiros maiores que a capacidade de armazenamento de um char. 

* **float** é para armazenar números fracionários ou reais. 

* **double** é também para números reais , mas com uma precisão muito maior que o float. Ou seja, suporta bem mais casas decimais.

* **void** serve para dizer que há ausência de valor. Entende-se melhor quando for utilizá-lo. 

## Definição de variáveis

Pode-se definir uma variável da forma seguinte: 

		tipo_de_dado nome_variavel;

Exemplos: 

		 char tecla;
		 char opcao;
		 int x, y, z;
		 float comissao, desconto, salario;

Definir uma variável é útil para informar ao compilador que um dado tem um tipo e nome determinado, mesmo que não tenha um valor. Porém, é possível atribuir valor durante a definição, com o operador =.

Exemplos: 

		int d = 3, f = 5;
		float f = 9.53;
		byte z = 22;
		char x = 'x';

## Modificadores de tipos 

Modificam as propriedades básicas dos tipos int e char. 

* **unsigned**: só números positivos, 0 e maiores que ele. 

* **short**: diminui a capacidade de armazenamento, limita a dois bytes. 

* **long** e **long long**: aumenta a capacidade de armazenamento.

	* long no linux é 64 bits e no windows é 32 bits.

	* long long no linux é 64 bits e no windows é 64 bits.

Mas quero que meu código fique independente de sistema operacional. Inclua inttypes.h, ela disponibilizará os tipos abaixo.

<img src="https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/tipos%20basicos/2.png" width="300"/>

Exemplos de variáveis modificadas: 

		unsigned char contador;
		unsigned int a, b, c;
		long int tam_arquivo;

## Entrada e saída formatada de dados 

A função *printf* exibe informações formatadas na tela. Ela tem a seguinte organização: *printf("formatação", arg1, arg2, ..., argn );*. Formatação é uma mensagem que será exibida, podendo ter partes substituídas pelos valores contidos nos argumentos *(arg1, arg2, ..., argn)*.

Exemplo: 

		printf("Hello world!");

Imprimirá: Hello world!

		printf("%i é par.", 2);

Imprimirá: 2 é par.

É possível imprimir valores de uma variável.

Exemplo: 

		int a = 65;
		char b = 65;
		float c = 65.0;
		printf("int: %i char: %c float: %f.\n", a, b, c);

Imprimirá: *int: 65 char: A float: 65.0;*

Cada tipo tem um especificador para formatação. 

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/tipos%20basicos/3.png)

Já a função *scanf* serve para entrada formatada de dados. Ela tem a organização seguinte: *scanf("formatação", arg1, arg2, ..., argn);*. Dada uma *string* que foi informada no sistema, se ela segue o formato da formatação, ela terá valores extraídos e colocados nos argumentos *(arg1, arg2, ..., argn)*. Exemplo: 

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/tipos%20basicos/4.png)

Não se esqueça de usar *&* antes do argumento, caso seja uma variável dos tipos que vimos até agora. No futuro, com ponteiros, isso é desnecessário. 

> %d é para inteiros, assim como %i. 

## Operações aritméticas básicas

C oferece operadores para a realização de operações aritméticas. As básicas são mostradas abaixo. Assuma que a variável A tem valor 10 e a B valor 20. 

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/tipos%20basicos/5.png)
