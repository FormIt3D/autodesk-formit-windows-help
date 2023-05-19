# Impostazione generale di plug-in nel file manifesto 

I plug-in di FormIt sono costituiti da un componente principale chiave denominato file _manifest.json_.

Il file manifesto è un [oggetto JSON](http://www.json.org) che indica all'infrastruttura di FormIt quali file recuperare e quale tipo di plug-in creare.

### Struttura e proprietà di manifest.json

Un file manifest.json presenta la seguente struttura. Contiene proprietà aggiuntive a seconda che si tratti di un [plug-in basato sulla barra degli strumenti](../additional-development-options/creating-a-toolbar-based-plugin.md) o un [plug-in basato sul pannello HTML](../additional-development-options/creating-an-html-panel-plugin.md).

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

Un plug-in tipico include le seguenti proprietà JSON:

* "PluginName" rappresenta il nome del plug-in per uso interno e la maggior parte degli scopi di visualizzazione, tra cui per [Plugin Manager.](../../how-to-use-plug-ins.md#plugin-manager)
* "PluginType" rappresenta il tipo di plug-in consentendo agli utenti di sapere, nella descrizione di [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager), cosa cercare quando installano il plug-in.
* "PluginDescription" viene visualizzato in [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) per comunicare le funzionalità del plug-in.
* "Script" elenca gli script esterni necessari associati al plug-in che verranno caricati nell'applicazione FormIt e che possono essere eseguiti quando viene richiamata una funzionalità del plug-in.

![](<../../../.gitbook/assets/image (5) (1).png>)

Avviare lo sviluppo di plug-in creando un file manifest.json nella cartella dei plug-in. Successivamente, sarà necessario decidere se si sta creando un plug-in basato sulla barra degli strumenti o uno basato sul pannello.

![](<../../../.gitbook/assets/image (36).png>)

**Nota** L'utilizzo di PLUGINLOCATION nel file manifest.json indicato sopra è essenziale e fa distinzione tra maiuscole e minuscole. FormIt sostituirà PLUGINLOCATION con la posizione del server per il plug-in.
