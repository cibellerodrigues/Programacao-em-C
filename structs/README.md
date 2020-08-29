# Structs

Uma struct é uma coleção arbitrária de variáveis logicamente relacionadas. 
Como nos [vetores](https://github.com/cibellerodrigues/Programacao-em-C/tree/master/Introdu%C3%A7%C3%A3o/vetores "vetores") essas variáveis compartilham o mesmo nome e ocupam posições consecutivas na memória. Contudo, diferentemente de vetores, structs são estruturas heterogêneas. Dessa forma, podemos utilizar um tipo de dados que pode ser usado para agrupar itens de tipos possivelmente diferentes em um único tipo.

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/structs/1.png)

## Definindo uma struct

	struct [structure tag] {
		member definition;
		member definition;
		...
		member definition;
	} [one or more structure variables]; 

A *structure tag* é opcional e cada definição de membro é uma definição de variável com os tipos que já vimos anteriormente. No final da definição da struct você pode especificar uma ou mais variáveis, mas é opcional.

## Criando uma struct 

	struct Adress{
		char name[50];
		char street[100];
		char state[20];
		int pin;
	};

---
	struct {
		int dia;
		int mes;       //struct anônima
		int ano;
	}hoje;

---

	struct Ponto{
		int x, y;
	}p1;

## Acessando membros de uma struct

	struct {
		int dia;
		int mes;
		int ano;
	}hoje;
	
	int main(){
		hoje.dia = 8;
		hoje.mes = 08;
		hoje.ano = 2020;
		
		return 0;
	}

---

	struct Adress{
		char name[50];
		char street[100];
	};
	
	int main(){
		struct Adress a1;
		a1.name = "Maria";
		a1.street = "João Maciel";
		
		return 0;
	}

---

	struct Ponto{
		int x, y;
	}p1;
	
	int main(){
		
		p1.x = 10;
		p1.y = 20;
		
		struct Ponto p2;
		p2.x = 5;
		p2.y = 6;
		
		return 0;
	}

## Criando structs com typedef

	typedef struct data{
		int dia;
		int mes;
		int ano;
	};

Esse fragmento de código cria um tipo de struct, cuja tag é data, através da qual podemos declarar variáveis da seguinte maneira:

> struct data hoje;
> struct data ontem, amanha;

Para não ser necessário utilizar a palavra reservada "struct" podemos declarar uma struct com tag e nome.

	typedef struct data{
		int dia;
		int mes;
		int ano;
	}DATA;

Teremos:

> DATA hoje;
> DATA amanha;

Por fim, também podemos omitir a tag e declarar apenas seu nome.

	typedef struct {
		int dia;
		int mes;
		int ano;
	}DATA;

### Acessando os membros da struct

	typedef struct {
		int dia;
		int mes;
		int ano;
	}DATA;
	
	int main(){
		DATA d1;
		d1.dia = 8;
		d1.mes = 08;
		d1.ano = 2020;
		
		return 0;
	}
