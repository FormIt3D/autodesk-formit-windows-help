---
description: Computational Design in FormIt
---

# FormIt + Dynamo

![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

In FormIt per Windows è incorporato Dynamo per incredibili workflow di progettazione computazionale.

## Novità di FormIt + Dynamo

### **Grafici dati, invio di livelli ad Excel e controllo delle sfaccettature**

[FormIt 2023](https://formit.autodesk.com/blog/post/introducing-formit-2023/) consente di eseguire i grafici di Dynamo[ senza un nodo SendToFormIt](formit-+-dynamo.md#graph-types), aggiunge la possibilità di [inviare i livelli di FormIt ad Excel](formit-+-dynamo.md#send-formit-levels-to-excel) e aggiunge il controllo della [sfaccettatura di curve e superfici tramite i nuovi nodi FormItGroupOptions](../tool-library/curve-+-surface-faceting.md).

### **Input di quote e accesso all'API JS anticipato**

[FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1) consente di utilizzare le [note quote di FormIt come input](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes), introduce [le opzioni a livello di oggetto](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes) e offre un'anteprima anticipata dell'[accesso all'API JavaScript](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes). È possibile scaricarlo [qui](https://formit.autodesk.com/page/download).

### **Più nodi SendToFormIt**

[FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3) consente di utilizzare [più nodi SendToFormIt e grafici di Dynamo nidificati](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

### **Nodo SelectFromFormIt**

[FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) aggiunge il nodo [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) e consente sessioni sempre connesse, modifiche multi-istanza e altro ancora.

## Manuale introduttivo

Sono fornite informazioni sull'interfaccia e sul collegamento delle directory di Dynamo a FormIt.

### **Prima impostazione**

È la prima volta che si utilizza FormIt + Dynamo? Potrebbe essere necessario prima [configurare il sistema](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes) per visualizzare l'area di disegno 3D in Dynamo.

### **Pannello di Dynamo**

Utilizzare il pannello di Dynamo per avviare Dynamo, posizionare i gruppi di Dynamo e modificare i grafici di Dynamo:

![Dynamo panel](<../.gitbook/assets/dynamo\_dynamopanel (1).png>)

### **Aggiunta e gestione delle directory di Dynamo locali**

* Il pannello di Dynamo funziona come la [Libreria di contenuti](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library), consentendo di collegare e gestire le directory locali contenenti i file di Dynamo.
* Fare clic sul pulsante di collegamento della directory nel pannello di Dynamo, quindi fare di nuovo clic su (+) nella finestra di dialogo Preferenze per selezionare una directory da collegare a FormIt: <img src="../.gitbook/assets/dynamo_selectdirectory.png" alt="" data-size="line">
* Passare da una directory collegata all'altra utilizzando l'elenco a discesa:

![](../.gitbook/assets/dynamo\_dropdown.png)

* Sarà possibile visualizzare solo i file .dyn e le sottocartelle tramite il pannello di Dynamo.
* Utilizzare la barra Filtra per filtrare i file e le sottocartelle di Dynamo in modo da poter trovare facilmente ciò di cui si ha bisogno:

![](../.gitbook/assets/dynamo\_filter.png)

## Diversi modalità disponibili in Dynamo

È possibile creare e modificare grafici in Dynamo o adattare parametri in FormIt senza mai visualizzare il grafico. O entrambe le operazioni contemporaneamente.

### **Tipi di grafico**

FormIt supporta tre tipi di grafici di Dynamo:

* Grafico dati: i grafici dati non presentano nodi _SendToFormIt_ e vengono utilizzati per presentare o trasferire dati tramite FormIt. Ad esempio, è possibile utilizzare i grafici dati per inviare dati ad Excel o calcolare dati non geometrici e visualizzarli in un nodo Watch.
* Grafico della geometria: questi grafici producono immediatamente la geometria e devono essere posizionati nell'area di disegno per visualizzarne i parametri. Dopo aver fatto clic sulla miniatura, la geometria verrà visualizzata sul cursore per il posizionamento nella scena 3D. Questo grafico richiede la presenza e la ricezione di almeno un nodo _SendToFormIt_ alla fine del grafico.
* Grafico di selezione: questi grafici richiedono selezioni di FormIt prima dell'esecuzione. Nell'angolo superiore sinistro di FormIt viene visualizzato un messaggio di richiesta per indicare gli elementi da selezionare. Dopo aver fornito la selezione, il grafico verrà eseguito e genererà la geometria rispetto alla selezione. Questo grafico richiede la presenza e la ricezione di almeno un nodo _SendToFormIt_ alla fine del grafico.

![](../.gitbook/assets/dynamo-graph-types.png)

### **Grafico della geometria: Posizionamento di un gruppo di Dynamo in FormIt**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* Nel pannello di Dynamo, fare clic sulla miniatura del grafico di Dynamo che si desidera eseguire.
   * È possibile utilizzare gli esempi incorporati o [collegare una libreria](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) dei file di Dynamo.
* Se si inserisce la geometria in FormIt, nel file di FormIt verrà incorporata una copia del grafico di Dynamo.
   * Per generare la geometria, è necessario associare un nodo [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) ai nodi della geometria di output nel grafico.
* La geometria del nodo SendToFormIt sarà disponibile sul cursore per il posizionamento.
   * Quando nel grafico sono presenti nodi [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) contrassegnati come È input, in FormIt verrà richiesta innanzitutto la selezione (ogni nodo di selezione in ordine verticale), quindi verrà generata la geometria nella posizione corretta rispetto alla selezione.
* Una copia del file di Dynamo originale viene ora incorporata nel gruppo di FormIt ed è indipendente dal grafico di origine.
* Al momento del posizionamento, il pannello Proprietà verrà attivato automaticamente per visualizzare i parametri disponibili.

### **Grafico della geometria: Modifica dei parametri**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* Dopo aver posizionato un gruppo di Dynamo, selezionarlo e passare al pannello Proprietà oppure è sufficiente fare doppio clic sul gruppo per passare automaticamente a Proprietà.
   * Eventuali nodi di input contrassegnati come È input in Dynamo verranno elencati qui.
   * I nodi di input [**SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) verranno mostrati come pulsanti nella parte superiore e possono essere utilizzati per aggiornare la selezione utilizzata per controllare il grafico.
   * FormIt supporta i seguenti nodi di input: Number Slider, Integer Slider, Boolean Toggle e i campi Number/String.
* Apportare modifiche agli input in FormIt, quindi fare clic su Esegui. Il pulsante Esegui diventa blu per indicare che i parametri sono stati modificati e che è necessario eseguire il grafico.
   * Dynamo verrà eseguito in background per elaborare le modifiche e restituire la geometria aggiornata in FormIt.
   * In FormIt 2022 e versioni successive, alla prima esecuzione dal pannello Proprietà viene messa in funzione un'istanza di Dynamo dedicata, rendendo le modifiche successive molto più veloci.
   * È possibile continuare ad utilizzare FormIt mentre Dynamo è in esecuzione.&#x20;
* Notare che tutta la geometria all'interno di ciascun gruppo SendToFormIt verrà eliminata e sostituita all'esecuzione del grafico di Dynamo.

### Grafico dati: Invio di livelli di FormIt ad Excel

In FormIt 2023 e versioni successive, è possibile utilizzare Dynamo per inviare i livelli di FormIt ad Excel:&#x20;

* Scaricare il [grafico di esempio di Dynamo qui](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn).
* Puntare la tavolozza di Dynamo alla directory locale in cui è stato salvato il grafico di Dynamo.
* Fare clic con il pulsante destro del mouse sulla miniatura e scegliere _Modifica grafico incorporato._
* Creare un foglio di calcolo di Excel vuoto in una posizione qualsiasi.
* Modificare il campo Spreadsheet Location per utilizzare il percorso del foglio di calcolo di Excel.
* Modificare eventuali altri campi desiderati, ad esempio Sheet Name.
* Chiudere Dynamo e salvare il grafico.

Ora è sufficiente fare clic sul file di esempio nella tavolozza ed è possibile eseguirlo in FormIt senza la necessità di generare la geometria.&#x20;

Gli input di Dynamo verranno visualizzati nella tavolozza di Dynamo e si aprirà Excel per visualizzare i risultati del grafico.&#x20;

Quando si apportano modifiche al modello, è possibile fare nuovamente clic sulla miniatura del grafico o sul pulsante _Esegui_ per aggiornare il foglio di calcolo con i dati del livello dell'ultima versione del disegno di FormIt.

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### Avvio di una nuova finestra di Dynamo

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* In FormIt 2021 e versioni successive, facendo clic sul pulsante Avvia Dynamo nel pannello di Dynamo verrà avviata automaticamente una sessione connessa con FormIt.
   * In questo modo viene aperto un modello di grafico in Dynamo e viene generata automaticamente la geometria del modello in FormIt.
   * La geometria risultante verrà visualizzata in un nuovo gruppo, all'origine del contesto di modifica del gruppo corrente. È consigliabile trovarsi nel contesto del gruppo desiderato prima di avviare Dynamo.&#x20;
   * Il modello include sia i nodi di FormIt sia la geometria di esempio. La regolazione dei dispositivi di scorrimento consentirà di regolare le dimensioni del cubo in entrambe le applicazioni.
   * Da qui, è possibile aprire grafici di Dynamo diversi o creare qualcosa di nuovo utilizzando questi componenti di base nel modello e utilizzare Salva con nome in Dynamo per il salvataggio in una nuova posizione.

### **Modifica di grafici incorporati + di origine**

I grafici di Dynamo esistenti possono essere modificati in due modi distinti: modificando i grafici incorporati che sono già stati posizionati in FormIt o modificando il grafico di origine salvato nel computer in uso.

### **Grafici incorporati**

Dopo aver posizionato un oggetto di Dynamo in FormIt, il grafico sottostante viene copiato e incorporato nel file di FormIt corrente. La sua modifica in Dynamo avviene tramite il pulsante **Modifica grafico incorporato**.

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* Selezionare il gruppo di Dynamo e passare al pannello Proprietà oppure è sufficiente fare doppio clic sul gruppo per passare automaticamente a Proprietà.
* Fare clic sul pulsante **Modifica grafico incorporato**.
* In Dynamo, si noterà che il nome del file nella parte superiore contiene ora "(FormIt)", il che significa che si sta modificando un grafico incorporato in questo file di FormIt e non si sta modificando il grafico di origine.
* Assicurarsi che uno o più nodi [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) siano connessi alla geometria che si desidera inviare a FormIt.
* In FormIt verranno visualizzati gli aggiornamenti alla geometria in tempo reale durante la regolazione del grafico.
* Se non si salvano le modifiche in Dynamo, in FormIt verrà ripristinata l'ultima versione salvata del grafico di Dynamo.
* Notare che tutta la geometria all'interno di ciascun gruppo SendToFormIt verrà eliminata e sostituita all'esecuzione del grafico di Dynamo.

### **Grafici di origine**

I grafici di origine vengono visualizzati nel pannello di Dynamo dopo il [collegamento di directory locali](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started). Questi grafici vengono memorizzati nel computer in uso e possono essere modificati in Dynamo facendo clic sul pulsante Modifica grafico di origine.

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* [Collegare una directory](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) contenente i file di Dynamo al pannello di Dynamo, quindi individuare la posizione desiderata nel pannello.&#x20;
* Fare clic con il pulsante destro del mouse sulla miniatura del grafico di Dynamo che si desidera modificare (o fare clic sulla freccia) e selezionare il pulsante **Modifica grafico di origine**.
* Dynamo verrà avviato con il grafico richiesto aperto e in FormIt verrà visualizzata la geometria dell'output finale del grafico.
   * Per i grafici che utilizzano uno o più nodi [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) come input, è possibile che la geometria risultante non venga visualizzata fino a quando i nodi SelectFromFormIt non vengono compilati con delle selezioni.
* La geometria risultante verrà visualizzata in un nuovo gruppo, all'origine del contesto di modifica del gruppo corrente.
   * È consigliabile trovarsi nel contesto del gruppo desiderato prima di fare clic su Modifica grafico di origine.
* Al termine della modifica, salvare e chiudere Dynamo. In FormIt, il grafico di origine è stato copiato e incorporato nel file di FormIt.
   * Se è necessario apportare ulteriori modifiche al **grafico di origine**, eliminare la copia incorporata e seguire di nuovo questi passaggi.

### **Controllo della sfaccettatura di curve e superfici**

*   A partire da FormIt 2023, è possibile controllare la sfaccettatura di curve e superfici associate ai nodi SendToFormIt utilizzando i nodi FormItGroupOptions: SetCurveFacetingCount e SetSurfaceFacetingCount.

    <img src="../.gitbook/assets/dynamo-formitgroupoptions-faceting-nodes.png" alt="" data-size="original">
* Questi nodi sostituiranno le impostazioni globali di sfaccettatura di curve e superfici, definite in Modifica -> Preferenze -> Unità + precisione.
* Ciò è molto utile se il grafico di Dynamo deve generare oggetti curvi utilizzando valori di sfaccettatura specifici, riducendo la necessità di modificare l'impostazione globale per ogni grafico di Dynamo eseguito nella sessione corrente.

![](../.gitbook/assets/dynamo-formitgroupoptions-faceting.gif)

* È inoltre possibile impostare globalmente le impostazioni di sfaccettatura in Modifica -> Preferenze -> Unità + precisione.
* Dopo aver regolato la qualità della sfaccettatura in Preferenze, eseguire nuovamente il grafico per utilizzare le nuove impostazioni di sfaccettatura globali.

![](../.gitbook/assets/dynamo\_controlcurve.gif)

[Sono fornite ulteriori informazioni sulle impostazioni di sfaccettatura di curve e superfici in FormIt.](https://windows.help.formit.autodesk.com/v/italian/tool-library/curve-+-surface-faceting)

## Utilizzo dei gruppi di FormIt con Dynamo

Sfruttando i potenti gruppi di FormIt si ottengono workflow incredibili e una migliore organizzazione della geometria di Dynamo.

### **Gruppi e il nodo SelectFromFormIt**

* Quando si seleziona la geometria per un nodo [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes), è utile memorizzare la geometria in un gruppo di FormIt e selezionare il gruppo.
   * In questo modo si ottiene la flessibilità necessaria per modificare il contenuto del gruppo di FormIt selezionato, quindi è sufficiente eseguire nuovamente il grafico che fa riferimento al gruppo per visualizzare il risultato aggiornato.
* Se si seleziona una geometria non raggruppata, una volta apportate le modifiche a tale geometria potrebbe essere visualizzato in FormIt il messaggio in cui è richiesto di selezionare nuovamente la geometria alla successiva esecuzione del grafico.

### **Generazione della geometria nei gruppi**

* Quando un grafico di Dynamo viene eseguito in FormIt, i risultati geometrici sono contenuti in un gruppo di FormIt.
* Ogni nodo [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) nel grafico crea un sottogruppo che contiene la geometria della porta di input del nodo.
* Dopo la generazione di un oggetto di Dynamo in FormIt, l'intero grafico e i relativi parametri vengono incorporati come copia nel file di FormIt.
* Quando il grafico viene eseguito, la geometria all'interno di ciascun sottogruppo viene eliminata e rigenerata.
   * Prestare attenzione quando si modifica la geometria o si dipingono superfici all'interno di sottogruppi, poiché tali modifiche andranno perse alla successiva esecuzione del grafico di Dynamo.
   * Tuttavia, se si disegnano sottogruppi (non la geometria al loro interno) con i materiali di FormIt, tali materiali verranno mantenuti tra un'esecuzione e l'altra. Vedere le immagini sottostanti.

### **Utilizzo di gruppi e materiali**

* Quando si utilizzano più nodi **SendToFormIt**, è possibile organizzarli in base al materiale, in modo da poter dipingere sottogruppi di FormIt differenti con materiali diversi.
* In questo esempio, un intero edificio viene generato da piani semplici in FormIt. Ogni componente di costruzione che richiede materiali univoci ottiene il nodo **SendToFormIt**:

![](<../.gitbook/assets/dynamo\_sendtoformit (1).png>)

* Dopo l'applicazione di materiali a ciascuno dei sottogruppi, i materiali vengono mantenuti tra le varie esecuzioni di Dynamo:

![](../.gitbook/assets/dynamo\_materialsgif.gif)

### **Nidificazione dei gruppi di Dynamo**

* È possibile utilizzare il nodo **SelectFromFormIt** per selezionare i risultati del sottogruppo da un grafico di Dynamo in modo da controllare i risultati di un altro grafico.&#x20;
* Continuando con l'esempio riportato sopra, l'output della vetrata del grafico di generazione edifici viene utilizzato come geometria di selezione per l'esempio incorporato Storefront Curtainwall:

![](../.gitbook/assets/dynamo\_storefront\_curtainwallgif.gif)

* Quando la forma dell'edificio cambia, è sufficiente selezionare il gruppo del sistema di montanti verticali e fare clic su Esegui nel pannello Proprietà.
   * Sebbene il contenuto del gruppo della vetrata sia cambiato, non è stato cambiato il gruppo stesso, pertanto non è necessario selezionare nuovamente la vetrata quando si riesegue il grafico.
* Il modello precedente è disponibile in FormIt 2022 e versioni successive come "Roof Planes Building" nella sottocartella **Building Masses** di **Dynamo Samples**.
* Combinato con le ampie funzionalità di FormIt, è possibile utilizzare Dynamo per creare e adattare un progetto interamente parametrico, completo di materiali e logica nidificata, nel contesto ricco di un potente modellatore concettuale:

![](../.gitbook/assets/dynamo\_parametricdesigngif.gif)

### **Comportamento del gruppo di FormIt standard ancora valido**

* A parte quanto descritto sopra, i gruppi di Dynamo in FormIt funzionano in base alle stesse regole di altri gruppi:
   * Il posizionamento di un nuovo oggetto di Dynamo dal pannello di Dynamo crea un gruppo univoco e non avrà effetto sulle istanze dello stesso oggetto già posizionate nel disegno.
   * L'operazione di copia e incolla dei gruppi di Dynamo mantiene identiche le istanze. Eventuali modifiche apportate al grafico di Dynamo di una copia aggiornerà anche la geometria nelle sue istanze identiche, a meno che quest'ultime non vengano rese univoche.
   * È possibile rendere univoci i gruppi di Dynamo con il tasto di scelta rapida RU o tramite il menu contestuale:

![](<../.gitbook/assets/dynamo\_makeunique (1).png>)

## Nodi di FormIt essenziali

Sono i nodi più potenti per l'invio di dati tra FormIt e Dynamo.

### **Nodo SendToFormIt**

* Per generare oggetti di Dynamo in FormIt, associare gli output desiderati del nodo geometrico all'input _geometry_ di almeno un nodo SendToFormIt:

![](<../.gitbook/assets/dynamo\_sendtoformitnode (1).png>)

* FormItGroupOptions è una nuova porta (facoltativa) in FormIt 2022 ed è descritta in dettaglio nella sezione **Nodi FormItGroupOptions** riportata di seguito.
* In FormIt 2021.3 e versioni successive, è possibile utilizzare più nodi SendToFormIt per organizzare i risultati di Dynamo in gruppi e sottogruppi di FormIt ordinati.
* [Scoprire come funziona Dynamo con i gruppi di FormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

![](<../.gitbook/assets/dynamo\_sendtoformitnodes (1).png>)

* Il nodo SendToFormIt rispetta il flag È output, che è selezionato per default. È possibile fare clic con il pulsante destro del mouse sul nodo per verificare:

![](<../.gitbook/assets/dynamo\_isoutput (1).png>)

* Se il flag è selezionato, la geometria associata a questo nodo SendToFormIt verrà visualizzata in FormIt, all'interno di un sottogruppo.
* Se il flag è deselezionato, non verrà inviata alcuna geometria a FormIt e il sottogruppo corrispondente (se presente) verrà eliminato.

### **Nodo SelectFromFormIt**

* FormIt 2021 e versioni successive offrono la possibilità di selezionare la geometria da FormIt per l'utilizzo come input nei grafici di Dynamo:

![](<../.gitbook/assets/dynamo\_selectfromformitnode (1).png>)

* Il nome del nodo SelectFromFormIt verrà utilizzato per i messaggi di richiesta in FormIt, pertanto è necessario assegnargli un nome che descriva il tipo di geometria di FormIt da selezionare:

![](<../.gitbook/assets/dynamo\_selectobjectstoarraynode (1).png>)

* Quando si fa clic sul pulsante Select From FormIt dall'editor grafico di Dynamo o dal pannello Proprietà, in FormIt verrà avviata una modalità di selezione guidata per guidare l'utente nella selezione della geometria:

![](../.gitbook/assets/dynamo\_selectobjectstoarrayUI.png)

* Il nodo SelectFromFormIt rispetta il flag È input, che è selezionato per default. È necessario verificare questo affinché la selezione funzioni in FormIt. Fare clic con il pulsante destro del mouse sul nodo da verificare.

![](<../.gitbook/assets/dynamo\_isinput (1).png>)

* Quando è selezionato il flag È input:
   * La miniatura del pannello di Dynamo del grafico indicherà che è necessaria una selezione:

![](../.gitbook/assets/dynamo\_patharray.png)

* Quando si esegue il grafico, la procedura guidata di selezione di FormIt consentirà di guidare l'utente nella selezione delle impostazioni per ogni nodo SelectFromFormIt, a partire dalla parte superiore del grafico.
* Dopo la prima generazione, viene visualizzato un pulsante per ogni nodo SelectFromFormIt nel pannello Proprietà di FormIt.

![](../.gitbook/assets/dynamo\_selectarraypath.png)

* Facendo clic su queste opzioni si avvia la selezione guidata, in modo da poter modificare la selezione utilizzata per generare la geometria finale. Il grafico verrà rieseguito automaticamente dopo la riselezione.

### **Suggerimenti, trucchi e note**

* Assegnare un nome al nodo SelectFromFormIt per indicare il tipo di geometria previsto. Ad esempio, "Select Site Boundary (Edges)".
   * È possibile selezionare qualsiasi tipo di geometria di FormIt, ma spesso è preferibile contenere la selezione in un gruppo di FormIt e [selezionare tale geometria anziché quella grezza](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).
* Se è necessario spostare i risultati di un grafico di Dynamo basato sulla selezione, è consigliabile spostare prima la geometria di selezione, quindi eseguire nuovamente il grafico, che rileverà la geometria di selezione aggiornata e si riposizionerà in modo appropriato.&#x20;
   * È inoltre possibile raggruppare i risultati di Dynamo **e** la selezione, quindi spostare il gruppo che li contiene.
* Quando la geometria di FormIt viene inviata a Dynamo, eventuali attributi, materiali o gruppi nidificati andranno persi quando la geometria verrà riportata in FormIt.
* Se si modifica un grafico basato sulla selezione in Dynamo e la geometria selezionata in FormIt cambia, sarà necessario riselezionare la geometria facendo clic sul pulsante Select From FormIt nel nodo SelectFromFormIt.&#x20;
* Quando si esegue la selezione in FormIt, viene applicato il [filtro di selezione](https://windows.help.formit.autodesk.com/v/italian/tool-library/select-edge-face-or-object#filtro-di-selezione) attivo. Ad esempio, se si desidera selezionare i vertici di FormIt, è necessario attivarli nel filtro di selezione.

![](../.gitbook/assets/dynamo\_filterselection.png)

## Altri nodi di input

È disponibile un'ampia gamma di opzioni di input per una facile personalizzazione dei grafici di Dynamo in FormIt.

### **Nodo FormItLengthString**

In FormIt 2022.1.0 o versione successiva, è possibile utilizzare il nodo **FormItLengthString** per specificare le quote in qualsiasi tipo di unità di FormIt supportato (piedi-pollici, pollici, m, cm, mm) indipendentemente dall'impostazione dell'unità di FormIt nel disegno attivo.

![](../.gitbook/assets/dynamo\_formitlengthstring.png)

Come con altri nodi di input supportati, _FormItLengthString_ viene mostrato nella tavolozza Proprietà di FormIt quando è contrassegnato come È input e, quando viene rinominato, il nuovo nome viene visualizzato in FormIt:

![](../.gitbook/assets/dynamo\_propertiespalette.png)

Ogni istanza del nodo _FormItLengthString_ può essere utilizzata in qualsiasi tipo di unità, pertanto un singolo grafico di Dynamo potrebbe impiegare una combinazione di unità, come mostrato sopra.

### **Passaggio da numeri grezzi a FormItLengthString**

In FormIt 2022.1.1 e versioni successive, il passaggio per un grafico all'utilizzo dei nodi FormItLengthString (mediante il posizionamento del primo in un grafico) o il passaggio per un grafico all'utilizzo dei soli numeri grezzi (rimuovendo l'ultimo nodo FormItLengthString) determinerà la modifica di determinati comportamenti durante la modifica di un grafico in Dynamo:

* Quando si utilizza il nodo [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) durante la modifica di un grafico, il passaggio tra i numeri grezzi e il nodo _FormItLengthString_ come indicato sopra richiederà la riselezione della geometria per ogni _SelectFromFormItNode_, in modo che i risultati continuino ad essere scalati correttamente in FormIt.
* Dopo il posizionamento del primo nodo FormItLengthString in un grafico, tutti i numeri nel grafico destinati come quote (inclusi gli input di numeri grezzi) faranno riferimento ai metri (l'unità nativa nascosta di Dynamo).
   * Il nodo [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) terrà conto della modifica e garantirà che la geometria generata in FormIt resti nelle dimensioni corrette.
   * Al contrario, la rimozione di tutti i nodi FormItLengthString dal grafico comporta il passaggio per i numeri grezzi al riferimento a qualsiasi impostazione delle unità di FormIt (comportamento precedente).
* Anche l'output numerico dei nodi _FormItLengthString_ sarà espresso in metri, ma non cambierà le dimensioni dei risultati geometrici in FormIt:

![](<../.gitbook/assets/dynamo\_outputinmeters (1).png>)

### **Altri nodi di input supportati**

I nodi di input di Dynamo standard verranno visualizzati nel pannello Proprietà di FormIt quando contrassegnati come È input in Dynamo:

* Number Slider
* Integer Slider
* Number
* String
* Boolean Toggle

È possibile rinominare i nodi di input (operazione consigliata per maggiore chiarezza) e il nuovo nome verrà visualizzato in FormIt:

![](<../.gitbook/assets/dynamo\_cuboidsize (1).png>)

![](../.gitbook/assets/dynamo\_inputs.png)

## Altri nodi di output

Esistono metodi differenti per visualizzare i risultati non geometrici da Dynamo a FormIt.

### **Nodo Watch**

I nodi Watch contrassegnati come È output verranno visualizzati nella sezione OUTPUT NODO WATCH del pannello Proprietà in FormIt 2022 e versioni successive:

![](<../.gitbook/assets/dynamo\_watchnodes (1).png>)

### **Visualizzazione delle notifiche di FormIt**

In FormIt 2022.1 o versione successiva, è possibile mostrare le notifiche lato FormIt da un grafico di Dynamo utilizzando il nodo **UI.ShowNotification**:&#x20;

![](../.gitbook/assets/dynamo\_notifications.png)

### **Registrazione nella console di FormIt**

In FormIt 2022.1 o versione successiva, è possibile registrare dati aggiuntivi direttamente nella console dell'applicazione FormIt (finestra Output script) con il nodo **FormIt.ConsoleLog**:

![](../.gitbook/assets/dynamo\_logtoconsole.png)

## Nodi delle opzioni di FormIt

Controllano il modo in cui i dati vengono inviati a FormIt, a livello di geometria individuale o a livello di gruppo che li contiene.

### **FormItGeometryOptions**

FormIt 2022.1 e versioni successive offrono la possibilità di personalizzare la modalità di invio delle singole geometrie di Dynamo a FormIt con nodi **FormItGeometryOptions**.

* Specificare il layer per le singole geometrie all'interno del gruppo di Dynamo generato.
* Specificare un attributo stringa per le singole geometrie all'interno del gruppo di Dynamo generato.

I nodi _FormItGeometryOptions_ possono essere utilizzati a monte del nodo _SendToFormIt_:

![](<../.gitbook/assets/dynamo\_formitgeometryoptions (1).png>)

### **FormItGroupOptions**

FormIt 2022 e versioni successive offrono la possibilità di personalizzare la modalità di generazione del gruppo di Dynamo del nodo _SendToFormIt_ in FormIt con nodi **FormItGroupOptions**.

* Specificare se il nodo SendToFormIt invia la geometria a FormIt come mesh o oggetto.
* Specificare il layer per il gruppo creato dal nodo SendToFormIt.
* Specificare un attributo stringa per il gruppo creato dal nodo SendToFormIt.

È possibile utilizzare qualsiasi combinazione di nodi FormItGroupOptions in qualsiasi ordine concatenandoli tramite collegamento in cascata:

![](../.gitbook/assets/dynamo\_daisychain.png)

## Nodi delle API JavaScript

FormIt 2022.1 e versioni successive offre l'accesso alle API JavaScript e alle funzioni personalizzate da Dynamo tramite due nuovi nodi:

### **CallJSAPI**

Il nodo **CallJSAPI** consente di richiamare le API JavaScript di FormIt direttamente da Dynamo.

![](<../.gitbook/assets/dynamo\_calljsapi (1).png>)

Per i nomi e i parametri delle funzioni, consultare la documentazione su JavaScript, suddivisa in due parti: [API di FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) e [API di WSM](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (kernel di modellazione).

**CallPluginJS**

Al contrario, il nodo **CallPluginJS** consente di richiamare funzioni personalizzate da un plug-in caricato o da un frammento di script eseguito dalla finestra Editor script.

![](<../.gitbook/assets/dynamo\_callpluginjs (1).png>)

## Note importanti

### **Requisiti di sistema**

* Per utilizzare Dynamo in FormIt, è necessario [FormIt per Windows](https://formit.autodesk.com/page/download) v17.0 o versione successiva.
   * L'integrazione di FormIt + Dynamo riceve regolarmente nuove funzionalità e correzioni, pertanto è sempre consigliabile scaricare l'aggiornamento più recente quando disponibile.
* Sarà inoltre necessario disporre di Windows 10. Per motivi tecnici, le versioni precedenti di Windows non sono più supportate.

**Risoluzione dei problemi**

* Se si dispone di un sistema con una [scheda grafica NVIDIA o AMD](https://www.howtogeek.com/414201/how-to-check-what-graphics-card-gpu-is-in-your-pc/) o più schede, potrebbe essere necessario impostare FormIt e Dynamo per utilizzare la GPU ad alta potenza:
   * _C:/Programmi/Autodesk/FormIt/FormIt.exe_.
   * _C:/Programmi/Autodesk/FormIt/DynamoSandbox/FormItDynamoSandbox.exe_.
   * Se si dispone di una scheda NVIDIA, [verificare che sia installato il pannello di controllo NVIDIA](https://whatsabyte.com/blog/find-nvidia-control-panel/).
   * Utilizzare i pannelli di controllo [NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a\_id/2615/\~/how-do-i-customize-optimus-profiles-and-settings%3F) o [AMD](https://www.amd.com/en/support/kb/faq/dh-017) per impostare le seguenti applicazioni in modo che utilizzino la scheda grafica dedicata:
* Se si utilizza una lingua diversa dall'inglese, potrebbe essere necessario definire le impostazioni regionali di Windows 10 in inglese per evitare problemi con determinati nodi di Dynamo:
   * Cercare in Start lingua e scegliere Impostazioni di lingua.
   * Nella parte superiore destra della finestra di dialogo Lingua, fare clic su Impostazioni amministrative della lingua.
   * Fare clic sul pulsante Cambia impostazioni locali del sistema.
   * Scegliere Inglese (Stati Uniti d'America).
* Se i grafici non generano risultati in FormIt quando si lavora con geometria o numeri piccoli, provare a modificare l'impostazione di ridimensionamento di Dynamo su Piccolo:
   * Menu Dynamo > Preferenze > Generale > Scala della geometria > Piccolo

![](../.gitbook/assets/dynamo\_geometryscaling.png)

### **Ottenere supporto**

Serve assistenza con FormIt + Dynamo? [Comunicarlo nei forum](https://forums.autodesk.com/t5/formit-forum/bd-p/142).
