# Criar um plug-in de painel HTML

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

Um plug-in baseado em painel que exibe uma página HTML tem um arquivo _manifest.json_ com a seguinte estrutura:

```
{
    "PluginName": "Hello Block!",
    "PluginType": "Panel",
    "PluginDescription": "Creates a panel with an HTML form that allows dimensional input for a 3D block which will get generated at the world origin.",
    "Scripts": [
        "PLUGINLOCATION/block.js"
    ],
    "Panel": "PLUGINLOCATION/hello_block.html",
    "PanelIcon": "PLUGINLOCATION/hello_block.png"
}               
```

Além das [propriedades JSON padrão](../advanced-development/general-plugin-setup-in-the-manifest.md), um plug-in baseado em painel inclui as seguintes propriedades JSON especiais:

* “Panel” informa ao FormIt que esse plug-in é um painel e apresenta um link para a localização do arquivo HTML que deve ser carregado no painel.
* O arquivo HTML precisará de links no cabeçalho para os arquivos JavaScript apropriados, bem como para um arquivo CSS para estilização.
* O arquivo HTML será renderizado no painel do FormIt como seria em um navegador.
* É possível ver exemplos de interfaces HTML avançadas em nossa [organização FormIt3D](https://github.com/FormIt3D/).
* “PanelIcon” define um ícone para que esse plug-in seja exibido na guia no lado direito do aplicativo. Se indefinido, o FormIt cria um ícone automático usando as iniciais do nome do plug-in.

Depois que os arquivos HTML, CSS e JavaScript estão configurados, você pode começar a testar o plug-in do painel HTML [carregando-o ou instalando-o](../advanced-development/setting-up-formit-for-development.md#load-vs.-install).
