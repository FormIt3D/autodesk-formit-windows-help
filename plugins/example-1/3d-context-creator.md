# Criador de contexto 3D

\![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## O que é?

O Criador de contexto 3D é um plug-in fácil de usar que gerará construções de contexto 3D dentro do FormIt. 

Esse plug-in pode ajudá-lo a visualizar o local do projeto com seu contexto circundante e tomar decisões informadas no estágio inicial do processo de projeto.

Esse plug-in recupera dados do [Open Street Map](https://www.openstreetmap.org/about) para ajudar a transformá-los em geometrias do FormIt. O código fonte para esse plugin está disponível em [Github](https://github.com/matterlab-co/FormIt-Context-Plugin).

## Como usá-lo?

Para instalá-lo, basta ativar a alternância do plug-in no Gerenciador de plug-ins, como faria com qualquer outro plug-in.

![](../../.gitbook/assets/contextcreator3.png)

Depois de ativado, o plug-in deve ser exibido no lado direito do aplicativo e estar pronto para uso.

\![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

Se o terreno ainda não tiver uma localização, será possível clicar no link **Definir localização...** para definir uma localização e definir o limite que será usado para gerar o contexto 3D.

Uma vez definida a localização, o Criador de contexto 3D será atualizado com a localização atual e o botão será ativado:

\![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

O Criador de contexto 3D simplesmente usará as extensões da imagem de satélite para gerar o Contexto 3D. Tudo o que você precisa fazer é clicar em **Gerar contexto 3D**.

Dependendo das extensões da imagem de satélite e da complexidade dos prédios, isso poderá levar alguns segundos para ser gerado.

As construções de contexto 3D serão automaticamente posicionadas em uma instância de grupo e posicionadas em uma camada denominada “Construções de contexto”. É possível alternar a visibilidade do contexto usando essa camada.

\![](<../../.gitbook/assets/3D Context Creator_layers.png>)

\![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

Se posteriormente você decidir alterar a localização ou ajustar o escopo da imagem de satélite, será possível clicar em **Gerar contexto 3D** novamente para regenerar as construções. 

_Observe que a regeneração do contexto substituirá a instância do grupo que contém as construções por uma nova instância, portanto, quaisquer alterações feitas nas construções serão perdidas._ Para evitar isso, é possível desagrupar o container de contexto e, em seguida, reagrupá-lo.

## **Alguns exemplos**

Tente adivinhar quais cidades icônicas são representadas nos seguintes contextos:

\![](<../../.gitbook/assets/image (2) (1).png>)

\![](<../../.gitbook/assets/image (34).png>)

\![](<../../.gitbook/assets/image (13) (1) (1).png>)

\![](<../../.gitbook/assets/image (59).png>)
