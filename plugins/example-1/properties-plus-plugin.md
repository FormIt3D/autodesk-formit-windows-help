# Plug-in Properties Plus

_Questo plug-in è una versione più completa della_ _**tavolozza Proprietà** standard. Se si selezionano più gruppi e/o tipi di geometria, questo plug-in fornirà una suddivisione degli elementi selezionati, oltre a consentire la ridenominazione di massa di gruppi e istanze di gruppi._

1 **-** Esamineremo innanzitutto le proprietà di un gruppo di porte del nostro modello principale. Riaprire **Encode Campus Sample Model.axm** e tornare alla scena **Eye Level – Long Alley**. Per iniziare ad utilizzare il plug-in **Properties Plus**:

1. Aprire la **tavolozza Properties Plus** facendo clic sulla proprietà con un'icona a forma del simbolo "più".
2. Assicurarsi che l'opzione **Update on Selection Change** sia selezionata.
3. Selezionare uno dei gruppi di porte vetrate a due pannelli, denominato **Door**, sul lato destro del vialetto.
4. Nell'area **Selection Count**, **Total Objects** indica che è stato selezionato un (**1**) oggetto.
5. Qui sotto sono disponibili ulteriori informazioni sui tipi di oggetti selezionati. In questo caso, è stato selezionato un (**1**) gruppo, ma tale gruppo presenta quattro (**4**) istanze da qualche parte nel modello.

![](<../../.gitbook/assets/10 (2) (1).png>)

_**Nota**_ _La verifica del numero di istanze del gruppo selezionato può risultare molto utile per evitare la modifica accidentale di più elementi quando si desidera effettivamente cambiare solo l'elemento selezionato, ma prima si è dimenticato di renderlo univoco._

2 - Questo plug-in consente di modificare il nome di un gruppo o di un'istanza di gruppo senza dover passare alla modalità di modifica del gruppo e rinominare più istanze contemporaneamente. Come abbiamo appreso in precedenza, ogni gruppo ha un nome, ma ogni istanza di quel gruppo può anche avere un nome di "istanza" univoco. Poiché probabilmente in questo modello vi saranno molti tipi di porte, desideriamo assegnare a questo gruppo, e ad alcune delle sue istanze, nomi più specifici.

1. Con il primo gruppo **Door** di vetro ancora selezionato, aggiungere un altro gruppo **Door** alla selezione corrente tenendo premuto **MAIUSC** o **CTRL** e facendo clic una sola volta sull'altro gruppo **Door** a due pannelli di vetri vicino al primo.
2. Notare che ora nella **tavolozza Properties Plus** è stata aggiornata l'opzione **Selection Count** per mostrare che sono selezionate due (**2**) istanze, ma che è ancora selezionata una sola (**1**) **famiglia** univoca (nota anche come gruppo). Anche se questo plug-in utilizza il termine **famiglia**, che gli utenti di Revit dovrebbero conoscere, in questo contesto ha lo stesso significato di un gruppo di FormIt.
3. Nell'area **Group Family**, aggiornare il campo **Name** in **Doors – Double Glass Storefront**. In questo modo il nome del gruppo verrà aggiornato per tutte le istanze, indipendentemente dal luogo in cui si trovano o dal fatto che siano attualmente selezionate o meno, senza dover fare doppio clic e modificare il gruppo.
4. Poiché queste due istanze sono entrambe porte nell'area Groove Coffee, rinominiamo solo queste due istanze immettendo **Groove Coffee Door** nel campo **Name** nell'area **Multiple Group Instances**.

**Nota** Nella **tavolozza Proprietà** standard, non è possibile rinominare più istanze di un gruppo contemporaneamente. Ciò può risultare estremamente utile quando si desidera assegnare a decine o centinaia di istanze lo stesso nome contemporaneamente.

![](<../../.gitbook/assets/11 (6) (1).png>)

_**Nota**_ _Se si sposta il mouse dalla tavolozza, non sarà più possibile modificare la casella di testo selezionata. Ciò vale per tutte le tavolozze, pertanto è necessario mantenere il cursore all'interno del contorno della tavolozza durante la modifica di qualsiasi elemento di una tavolozza._

3 - Ora, se si seleziona una porta in vetro di Groove Coffee o una porta in vetro diversa e si osservano le relative proprietà nella normale **tavolozza Proprietà**, si noterà che il nome di **Gruppo** è stato aggiornato per ogni istanza, ma solo per le porte di Groove Coffee la proprietà **Nome** è stata aggiornata rispetto al valore di default.

![](<../../.gitbook/assets/12 (3) (1).png>)

4 - Infine, vediamo come questo plug-in consente di ordinare diversi tipi di elementi:

1. Disegnare rapidamente una **Linea (L)**, un **Rettangolo (R)** e un **Cubo (ALT+B)** in qualsiasi punto del modello. Questi elementi saranno temporanei, pertanto la loro posizione precisa non è importante.
2. Riaprire la **tavolozza Properties Plus**, se è stata chiusa, quindi premere **CTRL+A** per selezionare tutti gli elementi visibili nel modello.
3. Esaminare l'area **Selection Count** e notare che gli elementi selezionati sono separati in **Edges** (linee), **Faces**, **Bodies**, (forme 3D di composte da superfici e bordi, come il cubo)**,** **Groups** e così via.

![](<../../.gitbook/assets/13 (3) (1).png>)

_**Nota**_ _Questo plug-in rileva anche i_ _**vertici**, che possono essere creati utilizzando un altro plug-in denominato_ _**Generate Vertex**. Se si desidera sperimentarne l'utilizzo, installare il_ _**plug-in Generate Vertex**_ _e ripetere i passaggi precedenti._
