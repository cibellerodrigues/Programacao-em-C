# Funções

Uma função é um grupo de instruções que juntas executam uma tarefa e fornece um mecanismo geral que nos permite reutilizar o código.

Todo programa em C tem pelo menos uma função, a main(). Essa é a função principal do programa e através dela chamaremos todas as outras funções que criaremos para serem executadas. 

## Definindo funções

Para definir uma função, empregamos a seguinte forma básica: 

    tipo nome(parametros){
      escopo da função
    }

Sendo que: 
* **tipo** refere-se ao tipo de resposta que a função devolve e deve ser *void(vazio)* se a função não tem valor de resposta;

* **nome** é o identificador da função no resto do programa;

* **parâmetros** é uma lista de variáveis que representam valores de entrada para a função e deve ser *void* caso não haja valores de entrada;

* dentro do escopo da função, a primeira seção é destinada à **declaração** das variáveis e a segunda, aos **comandos**.

Podemos modelar nossas funções de acordo com nossos problemas. Os parâmetros de uma função e seu tipo podem ser *void* e, assim, não retornam e/ou não recebem valores. 

## Funções void

Em C, podemos ter funções que não retornam nada e funções sem parâmetros. Observe os exemplos abaixo.

1. Função sem retorno e sem parâmetros

        void mensagem(void){
          printf("Olá. Seja bem vindo!");
        }

2. Função sem retorno e com parâmetros

        void imc(float altura, float peso){
          printf("Olá! Você tem um IMC de %.2f", peso/pow(altura, 2));
        }

Para que uma função seja reconhecida durante a compilação devemos declarará-la ou defini-la antes de qualquer referência que é feita a ela no resto do programa. Observe abaixo.

    #include <stdio.h>
    #include <math.h>
    void mensagem(void); /* Declaração da função */
    void imc(float altura, float peso);
  
    int main(int argc, const char *argv[ ]){
      mensagem();
      imc(1.69, 51.0);
    }

Para não utilizar as declarações das funções, podemos criar nossas funções acima da main().

## Funções com retorno

Se uma função não é do tipo *void*, então ela deve, necessariamente, ter retorno. Para isso, a função deve empregar o comando *return*. Observe os exemplos abaixo.

    float hipotenusa(float a, float b){
      float h;
    
      h = sqrt (pow(a, 2) + pow(b, 2));
    
      return h;
    }

A função acima recebe as medidas dos catetos de um triângulo retângulo e seu retorno é a medida da sua hipotenusa.

Um comando return pode aparecer em diversos pontos dentro de uma função, mas apenas uma dessas ocorrências pode ser executada. 

    int max(int a, int b){
      if(a > b) return a;
      return b;
    }

No exemplo acima, se a condição for verdadeira, a função retornará o valor contido em a. Caso contrário, o valor contido em b.
