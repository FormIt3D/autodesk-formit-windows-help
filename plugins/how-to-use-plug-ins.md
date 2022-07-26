# Como usar plug-ins

![](<../.gitbook/assets/g3 (1).gif>)

## Gerenciador de plug-ins

O Gerenciador de plug-ins do FormIt é o seu local para descobrir e gerenciar plug-ins.

O Gerenciador de plug-ins é carregado automaticamente quando o FormIt é iniciado, desde que o FormIt tenha acesso à Internet.

Acesse-o clicando no ícone da guia ![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PluginManagerTab.PNG) no lado direito do aplicativo:

![](../.gitbook/assets/c1.PNG)

## Categorias de plug-ins

O Gerenciador de plug-ins organiza os plug-ins em categorias para ajudar a encontrar os plug-ins nos quais você está mais interessado.

![](../.gitbook/assets/d16.png)

**Plug-ins instalados:** plug-ins já instalados pelo usuário.&#x20;

**Plug-ins recomendados:** plug-ins recomendados pela equipe do FormIt para expandir a funcionalidade principal do FormIt e revelar novos fluxos de trabalho. Os plug-ins desenvolvidos pela comunidade serão exibidos aqui após serem aprovados pela equipe do FormIt.\Identificador do GitHub: _formit-plugin-recommended_

**Plug-ins públicos:** plug-ins criados pela comunidade. Os plug-ins nessa categoria não foram revisados ou aprovados pela equipe do FormIt. \Identificador do GitHub: _formit-plugin_

**Plug-ins para desenvolvedores**: plug-ins criados pela comunidade para permitir a criação de novos plug-ins do FormIt. \Identificador do GitHub: _formit-plugin-developers_

## Adicionar o plug-in local ou privado

Se você estiver [desenvolvendo seu próprio plug-in](how-to-develop-plugins/), poderá adicionar a URL privada ao campo na parte inferior e clicar em (+):

![](../.gitbook/assets/d4.PNG)

Para obter mais informações sobre como adicionar o plug-in privado ou local, consulte [Visualizar um plug-in no Gerenciador de plug-ins. ](how-to-develop-plugins/advanced-development/previewing-a-plugin-in-the-plugin-manager.md)

## Redefinir o Gerenciador de plug-ins

O Gerenciador de plug-ins usa chaves de registro no Windows para armazenar os repositórios e plug-ins instalados. Se for necessário redefinir o Gerenciador de plug-ins para seus padrões, exclua a seguinte chave do registro:

`Computer\HKEY_CURRENT_USER\Software\Autodesk\FormIt 360\Plugins`

⚠️ Observação: Isso desinstalará todos os repositórios e plug-ins adicionados pelo usuário, redefinindo o Gerenciador de plug-ins para incluir somente os repositórios e plug-ins internos.

## Instalar plug-ins

O [Gerenciador de plug-ins](how-to-use-plug-ins.md#plugin-manager) inclui vários plug-ins, organizados em diferentes categorias. Cada plug-in tem um nome, uma descrição, um link do GitHub e alternância de instalação.&#x20;

![](../.gitbook/assets/d5.PNG)

Para instalar um plug-in, basta ativar a alternância ao lado do nome do plug-in.&#x20;

![](../.gitbook/assets/d6.png)

O ícone do plug-in selecionado será exibido no painel direito. Clique para exibir a interface do usuário do plug-in.

![](../.gitbook/assets/d7.PNG)

## Usar plug-ins

Cada plug-in tem uma interface do usuário exclusiva definida por seu desenvolvedor. Um plug-in normalmente tem um conjunto de instruções sobre como usá-lo, um conjunto de parâmetros (caixas de texto, controles deslizantes, caixas de seleção etc.) e um ou mais botões para executá-lo.

Usaremos um dos exemplos mais simples no Gerenciador de plug-ins: Cantos de arredondamento 2D. Primeiro carregamos o plug-in da seção Recomendados do Gerenciador de plug-ins. Em seguida, seguindo as instruções fornecidas pelo desenvolvedor, definimos o raio de arredondamento, selecionamos um grupo de faces para o arredondamento e clicamos no botão Cantos de arredondamento.

![](../.gitbook/assets/g4.gif)

##

