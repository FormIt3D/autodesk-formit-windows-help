# Plug-in Manage Cameras

_In questo capitolo, illustreremo alcuni dei plug-in forniti con FormIt per apportare alcuni miglioramenti al file_ _**Encode Campus Sample Model.axm**. Se non è già stato fatto, è possibile scaricare il file dal_ [_set di dati della Parte II della Guida introduttiva di FormIt_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip).

In tutta la Guida introduttiva, abbiamo utilizzato le scene come strumenti preziosi per navigare e controllare la visibilità in tutto il modello. Questo plug-in ci consente di visualizzare e modificare la quota altimetrica della cinepresa attuale, esportare le cineprese per ogni scena come oggetti 3D e copiare queste scene tra modelli.

1 - Innanzitutto, regoleremo la scena **Eye Level – Long Alley** in modo che la cinepresa sia effettivamente a livello della vista:

1. Se non è già presente, tornare alla scena **Eye Level – Long Alley** facendovi doppio clic nella **tavolozza Scene**.
2. Aprire la **tavolozza Manage Cameras** facendo clic sulla cinepresa con un'icona a forma di ingranaggio.
3. Modificare **Height Above Ground** in **5'-8"**.

![](<../../.gitbook/assets/6 (6) (1).png>)

_**Nota**_ _Se il modello contiene livelli, questo plug-in mostrerà anche l'altezza al di sopra del livello più vicino sotto_ _**Main Camera**._

2 - Quindi:

1. Tornare alla **tavolozza Scene**.
2. Assicurarsi che la scena **Eye Level – Long Alley** sia ancora selezionata (altrimenti fare clic una sola volta per selezionarla).
3. Fare clic sul pulsante **Aggiorna scena** per salvare la nuova altezza della cinepresa in questa scena.

![](<../../.gitbook/assets/7 (1) (1).png>)

_**Nota**_ _È inoltre possibile regolare l'angolo e la posizione della cinepresa di una scena attivando/disattivando il pulsante_ _**
Modifica cineprese scena**_ _nella parte superiore della_ _**tavolozza Scene**_ _(tra i pulsanti di aggiornamento e riproduzione)._

3 - Quindi esportare le scene in un nuovo modello. Innanzitutto, dobbiamo creare oggetti cinepresa per tutte le scene utilizzando il plug-in **Manage Cameras**:

1. Aprire nuovamente la **tavolozza Manage Cameras**.
2. Verificare che l'opzione **Copy Cameras to Clipboard** sia selezionata.
3. Fare clic sul pulsante **Export Scenes to Cameras**. Questa operazione potrebbe richiedere alcuni secondi.
4. Se l'intera area di disegno è diventata bianca, è perché la **cinepresa principale** è stata allineata con una delle cineprese della scena. Eseguire **Zoom (Z)** indietro fino a quando non si possono vedere i 3 edifici principali e gli oggetti cinepresa appena creati. Notare che gli oggetti cinepresa vengono automaticamente posizionati in un gruppo di grandi dimensioni denominato **Cameras**. All'interno di tale gruppo, ogni singola cinepresa viene posizionata nel relativo gruppo con lo stesso nome delle scene da cui è stata creata.

![](<../../.gitbook/assets/8 (7) (1).png>)

4 - Copiamo queste scene in un nuovo modello. Poiché i dati della cinepresa sono stati salvati negli Appunti, non è necessario eseguire molte operazioni:

1. Selezionare **Salva** **(CTRL+S)** per salvare il modello corrente e chiuderlo.
2. Avviare un nuovo disegno vuoto selezionando **Nuovo disegno (CTRL+N)** dall'elenco a discesa **File** sulla barra **Menu principale**.
3. Aprire il plug-in **Manage Cameras**, se non è già aperto, e verificare che l'opzione **Look for Cameras on Clipboard** sia selezionata.
4. Fare clic sul pulsante **Import Scenes from Cameras** nella parte inferiore del plug-in e le scene dell'altro modello verranno importate. Per verificare, aprire la **tavolozza Scene** e/o attivare il layer **Camera**. Come si può vedere, tutte le scene e gli oggetti cinepresa 3D sono stati importati in questo modello.

![](<../../.gitbook/assets/9 (7) (1).png>)
