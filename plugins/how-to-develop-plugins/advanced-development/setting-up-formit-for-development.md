# Impostazione di FormIt per lo sviluppo

Per testare e creare plug-in nell'app desktop di FormIt, è necessario utilizzare FormIt per Windows v17.0 o versioni successive.

### **Visualizzazione dell'Editor script e di Output script**

Nel menu superiore di FormIt, passare a **Finestra** e selezionare le caselle **Editor script** e **Output script**.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

I pannelli Editor script e Output script verranno visualizzati nella parte inferiore della finestra di FormIt.

Passare dall'Editor script ad Output script e viceversa utilizzando i pulsanti nella parte inferiore.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

È inoltre possibile disporre entrambi i pannelli affiancati. Fare clic sul pulsante accanto alla "x" nell'angolo superiore destro per staccare uno dei pannelli, quindi trascinare e rilasciare i pannelli l'uno accanto all'altro:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **Editor di script**

L'Editor script fornisce un ambiente di sviluppo semplice in cui è possibile scrivere e testare il codice.

L'Editor script memorizza il codice scritto all'interno di un file scratch.js nella directory in cui si trova il file FormIt.exe.

Nella parte superiore sono disponibili due pulsanti:

**Esegui** ![] (<../../.gitbook/assets/image (8).png>): esegue tutto il codice scritto nella finestra.

**Esegui selezione**![] (<../../.gitbook/assets/image (52).png>): esegue solo le righe di codice selezionate/evidenziate.

### **Output script**

Nella finestra Output script vengono visualizzati eventuali messaggi stampati sulla console dai plug-in.

È possibile cancellare l'output eseguendo `console.clear();` nell'Editor script.

## Utilizzo di plug-in di esempio

Dopo la [clonazione di un repository](cloning-a-sample-plugin.md) e l'[impostazione di un server Web](hosting-a-plugin-on-a-local-server.md), è ora possibile mostrare i plug-in locali in FormIt.

È possibile caricare o installare uno qualsiasi dei plug-in, ma ai fini di questo esercizio, si installeranno sia un plug-in basato sul pannello che un plug-in basato sulla barra degli strumenti. Si presume che http-server di npm sia in esecuzione sulla porta 8080 che ospita entrambi i repository di esempio.

### **Load o Install**

`FormIt.LoadPlugin();` carica il plug-in solo per la sessione corrente. Il plug-in verrà scaricato automaticamente quando l'app viene chiusa e riavviata.

Questa è un'ottima opzione per caricare temporaneamente il file manifesto di un plug-in per il test solo nella sessione corrente.

`FormIt.InstallPlugin();` consente di mantenere il plug-in utilizzando una chiave del Registro di sistema. Questa opzione è particolarmente utile per i plug-in che si utilizzeranno di frequente da una sessione all'altra.

In Windows, per mantenere i plug-in vengono utilizzate le seguenti chiavi del Registro di sistema:

* Plugins: Computer\HKEY\_CURRENT\_USER\Software\Autodesk\FormIt 360\Plugins\InstalledPlugins

Utilizzare `FormIt.UninstallPlugin();` per eseguire la disinstallazione.

Negli esempi seguenti, se non diversamente indicato, è possibile utilizzare _Install_ o _Load_, a seconda che si desideri che i risultati dell'esercizio siano persistenti o meno.

### **Esempio di plug-in della barra degli strumenti: Flip Along**

Nell'Editor script, eseguire quanto segue:

Se si esegue un server locale:

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

Se si esegue il caricamento dal [repository GitHub di FormIt](https://github.com/FormIt3D/) (richiede una connessione ad Internet):

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

Dovrebbe essere visualizzata la barra degli strumenti di Flip Along nella parte superiore della finestra dell'applicazione:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **Esempio di plug-in del pannello HTML: Properties Plus**

Nell'Editor script, eseguire quanto segue:

Se si esegue un server locale:

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

Se si esegue il caricamento dal [repository GitHub di FormIt](https://github.com/FormIt3D/) (richiede una connessione ad Internet):

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

Dovrebbe essere visualizzato il pannello di Properties Plus sul lato destro della finestra dell'applicazione:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **Esempio di plug-in della finestra di dialogo modale e non modale**

I plug-in della finestra dialogo sono univoci: possono essere caricati e non installati.

Nell'Editor script, eseguire quanto segue:

Se si esegue un server locale:

* Modale: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* Non modale: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

Se si esegue il caricamento dal [repository GitHub di FormIt](https://github.com/FormIt3D/) (richiede una connessione ad Internet):

* Modale: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* Modale: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

Dovrebbe essere visualizzato sullo schermo il pannello di Hello Block! nell'esempio del pannello HTML come finestra di dialogo modale o non modale.
