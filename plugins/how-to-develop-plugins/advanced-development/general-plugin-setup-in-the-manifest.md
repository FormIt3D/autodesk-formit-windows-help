# Configuração de plug-in geral no manifesto

Os plug-ins do FormIt são compostos de um componente base chave denominado arquivo _manifest.json_.

O arquivo de manifesto é um [objeto JSON](http://www.json.org) que informa a infraestrutura do FormIt quais arquivos buscar e que tipo de plug-in criar.

### Estrutura e propriedades do Manifest.json

Um arquivo manifest.json tem a seguinte estrutura. Possui propriedades adicionais dependendo se é um [plug-in baseado em barra de ferramentas](../additional-development-options/creating-a-toolbar-based-plugin.md) ou [baseado em painel HTML](../additional-development-options/creating-an-html-panel-plugin.md).

```
{
    "PluginName": "[PluginName]",
    "PluginType": "[PluginType]"
    "PluginDescription": "[PluginDescription]",
    "Scripts": [
        "PLUGINLOCATION/[script1].js",
        "PLUGINLOCATION/[script2].js",
        ...
        "PLUGINLOCATION/[scriptn].js"
    ]
}               
```

Um plug-in típico inclui as seguintes propriedades JSON:

* “PluginName” representa o nome do plug-in para fins internos e para a maior parte dos fins de exibição, incluindo para o [Gerenciador de plug-ins.](../../how-to-use-plug-ins.md#plugin-manager)
* “PluginType” representa o tipo de plug-in, permitindo que os usuários saibam na descrição do [Gerenciador de plug-ins](../../how-to-use-plug-ins.md#plugin-manager) o que procurar durante a instalação do plug-in.
* “PluginDescription” é exibido no [Gerenciador de plug-ins](../../how-to-use-plug-ins.md#plugin-manager) para comunicar os recursos do plug-in.
* “Scripts” lista os scripts externos necessários associados ao plug-in que serão carregados no aplicativo FormIt e podem ser executados quando a funcionalidade de plug-in é chamada.

![](<../../../.gitbook/assets/image (5) (1).png>)

Inicie o desenvolvimento do plug-in criando um arquivo manifest.json na pasta do plug-in. Em seguida, você precisará decidir se está criando um plug-in baseado em barra de ferramentas ou painel.

![](<../../../.gitbook/assets/image (36).png>)

**Observação:** O uso de PLUGINLOCATION em todo o arquivo manifest.json acima é essencial e diferencia maiúsculas de minúsculas. O FormIt substituirá PLUGINLOCATION pela localização do servidor do plug-in.
