# Configurar o FormIt para desenvolvimento

Para testar e criar plug-ins no aplicativo para desktop do FormIt, será necessário o FormIt para Windows v17.0 ou posterior.

### **Exibir editor de script e saída de script**

No menu superior do FormIt, vá para **Janela** no menu superior e marque as caixas **Editor de script** e **Saída de script**.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

Os painéis Editor de script e Saída de script aparecerão na parte inferior da janela do FormIt.

Alterne entre o Editor de script e a Saída de script usando os botões na parte inferior.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

Também é possível organizar os dois painéis lado a lado. Clique no botão ao lado do “x” no canto superior direito para desanexar um dos painéis e, em seguida, arraste e solte os painéis ao lado um do outro:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **Editor de scripts**

O Editor de script fornece um ambiente de desenvolvimento simples onde é possível escrever e testar o código.

O Editor de script armazena o código criado em um arquivo scratch.js no diretório em que o arquivo FormIt.exe está localizado.

Na parte superior, há dois botões:

**Executar** \![](<../../../.gitbook/assets/image (8)(1).png>): executa todo o código escrito na janela.

**Executar seleção** \![](<../../../.gitbook/assets/image (52).png>): executa somente as linhas de código selecionadas/realçadas.

### **Saída de script**

A janela Saída de script exibe as mensagens impressas no console dos plug-ins.

É possível limpar a saída executando `console.clear();` no Editor de script.

## Trabalhar com plug-ins de amostra

Após [clonar um repositório](cloning-a-sample-plugin.md) e [configurar um servidor da Web](hosting-a-plugin-on-a-local-server.md), agora é possível fazer com que os plug-ins locais sejam exibidos no FormIt.

É possível carregar ou instalar qualquer um dos plug-ins, mas para os fins deste exercício, você instalará um plug-in baseado em painel e um baseado em barra de ferramentas. Vamos supor que o servidor http npm esteja sendo executado na porta 8080 hospedando ambos os repositórios de exemplo.

### **Carga vs. Instalação**

`FormIt.LoadPlugin();` carrega o plug-in somente para a sessão atual. O plug-in será descarregado automaticamente quando o aplicativo for fechado e reiniciado.

Essa é uma ótima opção para manifestar temporariamente um plug-in para teste somente na sessão atual.

`FormIt.InstallPlugin();` faz com que o plug-in persista usando uma chave do registro. Isso é ótimo para plug-ins que você usará com frequência de sessão para sessão.

No Windows, as seguintes chaves de registro são usadas para manter os plug-ins:

* Plug-ins: Computer\\HKEY_CURRENT_USER\\Software\\Autodesk\\FormIt 360\\Plugins\\InstalledPlugins

Use `FormIt.UninstallPlugin();` para desinstalar.

Nos exemplos a seguir, a não ser que indicado de outra forma, sinta-se à vontade para usar _Instalar_ ou _Carregar_, dependendo se você deseja que os resultados do exercício sejam persistentes ou não.

### **Amostra de plug-in de barra de ferramentas: Inverter ao longo**

No Editor de script, execute o seguinte:

Se estiver executando um servidor local:

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

Se estiver carregando do repositório do [FormIt GitHub](https://github.com/FormIt3D/) (requer uma conexão com a Internet):

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

Você deve ver a barra de ferramentas Inverter ao longo exibida na parte superior da janela do aplicativo:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **Amostra de plug-in de painel HTML: Mais propriedades**

No Editor de script, execute o seguinte:

Se estiver executando um servidor local:

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

Se estiver carregando do repositório do [FormIt GitHub](https://github.com/FormIt3D/) (requer uma conexão com a Internet):

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

Você deve ver o painel Mais propriedades ser exibido no lado direito da janela do aplicativo:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **Amostra de plug-in de caixa de diálogo modal e sem janela restrita**

Os plug-ins de caixa de diálogo são exclusivos: só podem ser carregados, não instalados.

No Editor de script, execute o seguinte:

Se estiver executando um servidor local:

* Modal: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* Sem janela restrita: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

Se estiver carregando do repositório do [FormIt GitHub](https://github.com/FormIt3D/) (requer uma conexão com a Internet):

* Modal: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* Modal: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

Você deve ver o painel Hello Block! do exemplo do painel HTML aparecer na tela como uma caixa de diálogo modal ou sem janela restrita.
