# Configurando um ambiente de desenvolvimento no Windows
VsCode e Mingw-w64 para criar programas em C

## Pré-requisitos
Para montar o ambiente corretamente você tem que seguir os passos a seguir: 

1. Instalar o Visual Studio Code;

a. Download do instalador para Windows: [link](https://go.microsoft.com/fwlink/LinkID=534107)

b. Finalizando o download, execute o instalador(VSCodeUserSetup-{versão}.exe).

>1. Escolha a língua que será usada no instalador.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/1.png)

	>2. Aceite a licença.
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/2.png)
	>3. Por padrão, o vs code é instalado na pasta
	C:\users\{username}\AppData\Local\Programs\Microsoft VS Code.
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/3.png)
	
	>4. Defina um nome para pasta no menu.
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/4.png)
	
	>5. Configurações adicionais (ícone e editor padrão).
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/5.png)
	
	>6. Só terminar a instalação clicando em install.
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/6.png)
	
	>7. Instalação.
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/7.png)
	
	>8. Completar iniciando o vscode.
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/8.png)
	
	c. Agora você deveria ter o VS code executando.
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/9.png)
2. Instalando a extensão C/C++ para o VS Code.
	a. Primeira coisa que fará é abrir a aba de extensões do VS Code com (Ctrl + Shift+ X). Você pode encontrar a extensão digitando c na busca por extensões.
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/10.png)

	b. Após escolhida a extensão, a primeira da lista, basta clicar em install. O estado da tela abaixo indica a finalização da instalação da extensão.
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/11.png)
3. Instalação mingw-w64.
a. Realize o download do mingw-w64 via site do sourceforge: [link](http://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/mingw-w64-install.exe/download)
b. Abra o instalador e inicie a instalação.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/12.png)
c. Configure de acordo com os parâmetros abaixo.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/13.png)
d. Não instale em um caminho no sistema de arquivos que tenha espaço, por
exemplo “C:\Program Files”. Assumo que você instalará em C:. Veja como
ficou a minha configuração.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/14.png)
e. A instalação começa.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/15.png)
f. Finalização da instalação.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/16.png)
g. Caso dê o erro a seguir, a instalação será manual.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/17.png)

	>1. Acesse este [link](https://sourceforge.net/projects/mingw-w64/files/mingw-w64/) para obter o arquivo comprimido.
	>2. Selecione o arquivo com a configuração anteriormente feita.
	**MinGW-W64 GCC-8.1.0**
	x86_64-posix-sjlj
	>3. Após o download do arquivo extraia seu conteúdo para a pasta C:\mingw-w64.
	>4. Tanto a instalação pelo instalador, quanto a manual, o caminho do programa no sistema de arquivos do seu computador fica igual abaixo (C:\mingw-w64\mingw64).
	![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/18.png)
4. Configuração do Mingw na variável de ambiente do Windows.
a. Na barra de busca do Windows digite configurações. Abrirá as configurações
do Windows.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/19.png)
b. Busque por “Editar as variáveis de ambiente do sistema”. Ao clicar no
resultado da busca, abrirá a janela abaixo.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/20.png)
c. Clique em variáveis do ambiente. Abrirá a tela a seguir.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/21.png)
d. Selecione a variável “Path” e clique em “editar”. Abrirá a tela a seguir.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/22.png)
e. Selecione “Novo” para adicionar o caminho até a pasta “bin” do mingw que
instalou. Se seguiu a minha configuração, o caminho será “C:\mingw-
w64\mingw64\bin”. Clique em OK de todas as telas até sair da configuração.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/23.png)
f. Para verificar se a configuração foi realizada com sucesso abra um prompt de
comando e digite “gcc --version”.
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/24.png)
g. Se a saída foi igual a figura anterior está tudo ok. Senão verifique os seus
passos de instalação e tente descobrir onde errou.

## Criando o primeiro programa no ambiente
É uma boa prática  definir uma pasta no sistema de arquivos que agrupe todos os seus projetos ou ambientes de desenvolvimento. Dessa maneira, onde você quiser, no seu sistema, crie uma pasta “projetos”, dentro dela uma pasta “c” e dentro de “c” crie uma pasta “helloworld”.

Após a criação da estrutura de pastas anterior, aperte “Ctrl+Shit+E” ou no ícone que é duas folhas uma acima da outra. Você verá a figura abaixo e clicará em “abrir pasta” no vs code.

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/25.png)

Selecione a pasta “helloworld” que acabou de criar. Veja que a pasta está aberta no vscode.

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/26.png)

Agora você criará o arquivo helloworld.c. Para isso passe o mouse próximo do nome “helloworld” no vscode para habilitar as opções de criação. Veja o exemplo abaixo.

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/27.png)

Após a criação você deve ter percebido a criação de uma aba onde você editará o código. Digite o exemplo abaixo.

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/28.png)

Quando estiver digitando você perceberá que o vscode tenta adivinhar o que quer escrever, dando opções para escolha no intuito de adiantar a programação. Após terminar a escrita, salve com “Ctrl + S”.

### Compilando o primeiro programa no ambiente

Compilar é o processo de gerar o programa executável. Para isso, você precisará abrir um terminal. No próprio vscode você tem duas opções. A primeira é clicar na aba “Terminal” e ao abrir em “Novo terminal”. A segunda é usar o atalho “Ctrl+Shift+’ ”. O resultado dessa ação está logo abaixo.

![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/29.png)

Perceba que foi aberto um terminal na parte inferior do vscode. É ele que usaremos para gerar o executável. Siga os passos:
1. Para compilar: gcc -o helloworld.exe helloworld.c
2. Para ver o executável: dir
3. Para executar: .\helloworld.exe

Veja o resultado: 
![](https://raw.githubusercontent.com/cibellerodrigues/Programacao-em-C/master/Introdu%C3%A7%C3%A3o/images/ambiente/30.png)

Se conseguiu ver “Hello world!” tudo está funcional.
