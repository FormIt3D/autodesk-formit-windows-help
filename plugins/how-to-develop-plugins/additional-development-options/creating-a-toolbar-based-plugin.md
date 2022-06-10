# Criar um plug-in com base na barra de ferramentas

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### Estrutura de um plug-in manifest.json com base na barra de ferramentas

Um plug-in baseado em barra de ferramentas tem um arquivo _manifest.json_ com a seguinte estrutura:

```
{
    "PluginName": "Flip Along",
    "PluginType": "Toolbar",
    "PluginDescription": "Creates a toolbar with X, Y, and Z buttons to quickly flip selected geometry in the direction of the selected axis.",
    "ToolbarURL": "PLUGINLOCATION/toolbar.json",
    "Scripts": [
        "PLUGINLOCATION/flipalong.js"
    ]
}               
```

Além das [propriedades JSON padrão](../advanced-development/general-plugin-setup-in-the-manifest.md), um plug-in baseado em barra de ferramentas inclui esta propriedade JSON especial:

* “ToolbarURL” informa ao FormIt que esse plug-in é uma barra de ferramentas e apresenta um link para a localização de outro arquivo JSON que descreve a funcionalidade da barra de ferramentas.

### Configurar o formato da barra de ferramentas com JSON

Após criar um arquivo de manifesto como o descrito acima, você precisará criar o arquivo toolbar.json, que define os botões da barra de ferramentas, seus nomes, texto, ícones e a função onClick atribuída a cada botão. O arquivo JSON da barra de ferramentas terá o seguinte formato:

```
{
    "name": "Flip Along Toolbar",
    "buttons": [
        {
            "name": "Flip Along X",
            "command": "FlipAlongPlugin.ButtonX",
            "iconText": "X",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Y",
            "command": "FlipAlongPlugin.ButtonY",
            "iconText": "Y",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Z",
            "command": "FlipAlongPlugin.ButtonZ",
            "iconText": "Z",
            "iconURL": "[Icon URL]"
        }
    ]
}               
```

O arquivo toolbar.json inclui as seguintes propriedades JSON:

* “name” representa o nome da barra de ferramentas geral, e é usado internamente para associar todos os botões ao menu de barra de ferramentas único.
* “buttons” representa os botões individuais adicionados dentro da barra de ferramentas. Uma barra de ferramentas pode ter qualquer quantidade de botões.
* “name” define o nome interno do botão, que é usado para associar o botão à barra de ferramentas, bem como à função onClick do botão.
* “command” define a função do botão, que pode vir em uma de duas formas: uma função JavaScript (que pode ser definida em um script contido no campo manifest.json “Scripts”) ou um comando do FormIt, por exemplo, “Desenhar: Círculo”. É possível obter uma lista de comandos do FormIt executando o plug-in de mensagens.
* “iconText” define a dica de ferramenta e o texto de descrição no botão. Se um URL de ícone não for fornecido, o texto criará um ícone gerado automaticamente do texto formatado.
* “iconURL” pode ser configurado para definir um ícone personalizado para o botão.

Após todos os botões terem sido definidos no arquivo toolbar.json, o plug-in estará pronto para ser usado.&#x20;

Se houver outras funções JavaScript que você deseja definir, adicione-as à mesma pasta que o arquivo manifest.json. Certifique-se de adicionar a referência de arquivo ao campo “Scripts” do arquivo de manifesto, para que o FormIt possa localizar os arquivos.
