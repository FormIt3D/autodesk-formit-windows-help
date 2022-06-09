# Creazione di un plug-in basato sulla barra degli strumenti

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### Struttura di un file manifest.json del plug-in basato sulla barra degli strumenti

Un plug-in basato sulla barra degli strumenti presenta un file _manifest.json_ con la seguente struttura:

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

Oltre alle [proprietà JSON standard](../advanced-development/general-plugin-setup-in-the-manifest.md), un plug-in basato sulla barra degli strumenti include questa speciale proprietà JSON:

* "ToolbarURL" indica a FormIt che questo plug-in è una barra degli strumenti e si collega alla posizione di un altro file JSON che descrive le funzionalità della barra degli strumenti.

### Configurazione del formato della barra degli strumenti con JSON

Dopo la creazione di un file manifesto come quello descritto sopra, sarà necessario creare il file toolbar.json, che definisce i pulsanti della barra degli strumenti, i loro nomi, il testo, le icone e la funzione onclick assegnata a ciascun pulsante. Il file JSON della barra degli strumenti avrà il seguente formato:

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

Il file toolbar.json include le seguenti proprietà JSON:

* "name" rappresenta il nome della barra degli strumenti generale e viene utilizzato internamente per associare tutti i pulsanti al singolo menu della barra degli strumenti.
* "buttons" rappresenta i singoli pulsanti aggiunti all'interno della barra degli strumenti. Una barra degli strumenti può avere un numero qualsiasi di pulsanti.
* "name" definisce il nome interno del pulsante, utilizzato per associare il pulsante alla barra degli strumenti e alla funzione onclick del pulsante.
* "command" definisce la funzione del pulsante, che può presentarsi in una delle due seguenti forme: una funzione JavaScript (che può essere definita in uno script contenuto nel campo "Scripts" di manifest.json) o un comando di FormIt, ad esempio "Disegna: Cerchio". È possibile ottenere un elenco di comandi di FormIt eseguendo il plug-in Messagges.
* "iconText" imposta la descrizione comando e il testo descrittivo nel pulsante. Se non viene fornito l'URL di un'icona, il testo creerà un'icona generata automaticamente di testo formattato.
* "iconURL" può essere impostato per definire un'icona personalizzata per il pulsante.

Dopo aver definito tutti i pulsanti nel file toolbar.json, il plug-in è pronto per essere attivato.&#x20;

Se sono presenti funzioni JavaScript aggiuntive che si desidera definire, aggiungerle alla stessa cartella del file manifest.json. Assicurarsi di aggiungere tale riferimento anche al campo "Script" del file manifesto in modo che FormIt possa trovare i file.
