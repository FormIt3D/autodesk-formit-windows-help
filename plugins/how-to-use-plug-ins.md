# Come utilizzare i plug-in

![](<../.gitbook/assets/g3 (1).gif>)

## Plugin Manager

Plugin Manager di FormIt è il negozio online unico per individuare e gestire plug-in.

Gestione plugin viene caricato automaticamente all'avvio di FormIt, purché FormIt disponga dell'accesso ad Internet.

Per accedervi, fare clic sull'icona della spina ![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PluginManagerTab.PNG) a destra dell'app:

![](../.gitbook/assets/c1.PNG)

## Categorie di plug-in

Plugin Manager organizza i plug-in in categorie per aiutare a individuare i plug-in più interessanti.

![](../.gitbook/assets/d16.png)

**Plug-in installati:** plug-in già installati dall'utente.&#x20;

**Plug-in consigliati:** plug-in consigliati dal team di FormIt per espandere le funzionalità principali di FormIt e sbloccare nuovi workflow. I plug-in sviluppati dalla community vengono visualizzati qui dopo l'approvazione da parte del team di FormIt.\
Tag GitHub: _formit-plugin-recommended_

**Plug-in pubblici:** plug-in creati dalla community. I plug-in di questa categoria non sono stati rivisti o approvati dal team di FormIt. \
Tag GitHub: _formit-plugin_

**Plug-in per sviluppatori**: plug-in creati dalla community per consentire la creazione di nuovi plug-in di FormIt. \
Tag GitHub: _formit-plugin-developers_

## Aggiunta del plug-in privato o locale

Se si sta [sviluppando un plug-in personalizzato](how-to-develop-plugins/), è possibile aggiungere il relativo URL privato nel campo in basso e premere (+):

![](../.gitbook/assets/d4.PNG)

Per ulteriori informazioni sull'aggiunta di plug-in privati o locali, vedere [Anteprima di un plug-in in Plugin Manager. ](how-to-develop-plugins/advanced-development/previewing-a-plugin-in-the-plugin-manager.md)

## Reimpostazione di Plugin Manager

Gestione plugin utilizza le chiavi del Registro di sistema in Windows per memorizzare i repository e i plug-in installati. Se è necessario ripristinare le impostazioni di default di Gestione plugin, eliminare la seguente chiave del Registro di sistema:

`Computer\HKEY_CURRENT_USER\Software\Autodesk\FormIt 360\Plugins`

⚠️ Nota Questa operazione disinstallerà tutti i repository e i plug-in aggiunti dall'utente, reimpostando Plugin Manager in modo da includere solo quelli incorporati.

## Installazione dei plug-in

[Plugin Manager](how-to-use-plug-ins.md#plugin-manager) include diversi plug-in, organizzati in categorie differenti. Ogni plug-in ha un nome, una descrizione, un collegamento GitHub e un pulsante di commutazione per l'installazione.&#x20;

![](../.gitbook/assets/d5.PNG)

Per installare un plug-in, è sufficiente attivare il pulsante di commutazione accanto al suo nome.&#x20;

![](../.gitbook/assets/d6.png)

L'icona del plug-in selezionato comparirà nel pannello di destra. Fare clic per visualizzare l'interfaccia utente del plug-in.

![](../.gitbook/assets/d7.PNG)

## Utilizzo dei plug-in

Ogni plug-in dispone di un'interfaccia utente univoca definita dal suo sviluppatore. Un plug-in in genere include una serie di istruzioni su come utilizzarlo, un insieme di parametri (caselle di testo, dispositivi di scorrimento, caselle di controllo e così via) e uno o più pulsanti per eseguirlo.

Ad esempio, utilizzeremo uno degli esempi più semplici in Plugin Manager: Fillet 2D Corners. Innanzitutto, carichiamo il plug-in dalla sezione Recommended di Plugin Manager. Quindi, seguendo le istruzioni fornite dallo sviluppatore, impostiamo il raggio di raccordo, selezioniamo un gruppo di superfici da raccordare e facciamo clic sul pulsante Fillet Corners.

![](../.gitbook/assets/g4.gif)

##

