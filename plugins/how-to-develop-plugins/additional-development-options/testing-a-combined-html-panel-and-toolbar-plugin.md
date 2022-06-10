# Testar um painel HTML e um plug-in de barra de ferramentas combinados

É possível testar os plug-ins em andamento facilmente usando o [Editor de script](../advanced-development/setting-up-formit-for-development.md) incorporado no FormIt para Windows

Recomendamos usar `FormIt.LoadPlugin("URL");` ao testar, que carrega plug-ins temporariamente para esta sessão (eles desaparecerão quando o FormIt for reiniciado).&#x20;

Depois que o teste é concluído, é possível manter o plug-in entre as sessões usando `FormIt.InstallPlugin("URL");`.

**FormIt para Windows v17 e versões mais recentes**

****

### **Plug-ins da barra de ferramentas**

Carregue o plug-in no FormIt para ver a interface do usuário mais recente e testar a funcionalidade mais recente:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Faça algumas alterações e carregue o plug-in novamente usando o comando acima.

É possível carregar muitas instâncias do mesmo plug-in na sessão atual à medida que você testa, cada uma com sua própria interface do usuário.

Certifique-se de usar a instância mais recente da interface do usuário para garantir que você esteja testando as alterações mais recentes.



### **Plug-ins de painel HTML**

Carregue o plug-in no FormIt para ver a interface do usuário mais recente e testar a funcionalidade mais recente:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Faça algumas alterações e, em seguida, clique com o botão direito do mouse no painel e selecione “Recarregar rígido” para recarregar o painel com o HTML, CSS e scripts mais recentes.

****

### **Visualizar o plug-in com o Gerenciador de plug-ins**

Depois que o plug-in tenha sido carregado, consulte um [capítulo anterior](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md) deste guia.

****

### **Forçar a limpeza do cache da Web para arquivos .JSON**

Se você modificar o título ou a descrição dentro do arquivo manifest.json de um plug-in ou repositório, talvez seja necessário forçar a limpeza do cache no FormIt para Windows para ver que essas alterações entrarão em vigor na próxima vez que você recarregar o Gerenciador de plug-ins.

O FormIt para Windows armazena seu cache da Web aqui. Você precisará ativar os itens ocultos no Windows Explorer para ver a pasta AppData.

* C:\Users\user\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

Para excluir o cache da Web, basta excluir a pasta “Padrão” acima e, em seguida, recarregar o Gerenciador de plug-ins para ver os títulos e as descrições atualizados.
