# Generate String Lights

_In questo capitolo, illustreremo alcuni dei plug-in forniti con FormIt per apportare alcuni miglioramenti al file_ _**Encode Campus Sample Model.axm**. Se non è già stato fatto, è possibile scaricare il file dal_ [_set di dati della Parte II della Guida introduttiva di FormIt_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip).

_Questo nuovo plug-in consente di aggiungere rapidamente al modello luci sospese in base ad una linea o una curva._

1 - Prima di aggiungere eventuali nuove luci, controlliamo il risultato desiderato utilizzando una scena predefinita nel modello.

1. Per passare alla scena contenente luci stringa esistenti, aprire la **tavolozza Scene** e fare doppio clic sulla scena denominata **Eye Level – Short Alley**.
2. Notare le luci stringa fornite con questo modello: è quello che ricreeremo, ma aggiungendo qualche altro elemento.
3. Nella **tavolozza Layer**, attivare il layer **Helper Geometry** in modo da visualizzare le linee originali utilizzate per generare queste luci stringa.

![](<../../.gitbook/assets/3 (10).png>)

2 - Ora passiamo all'altro vialetto e aggiungiamo alcune luci. Nella **tavolozza Scene**, aprire la scena **Eye Level – Long Alley**. Notare che in questo vialetto non sono ancora presenti eventuali luci stringa.

3 - Per creare una nuova stringa di luci:

1. Aprire la **tavolozza Generate String Lights** appena installata facendo clic sull'icona della luce stringa. Per default, le icone per i nuovi plug-in vengono visualizzate nella parte inferiore.
2. Modificare l'opzione **Number of Fixtures** in **10**.
3. Fare doppio clic su una delle linee guida per modificare il gruppo **String Lights – Long Alley** pre-creato. Quindi fare clic una sola volta su una delle linee guida pre-disegnate per selezionarlo.
4. Fare clic sul pulsante **Generate String Lights** all'interno della tavolozza del plug-in. Dovrebbe essere visualizzata una nuova stringa di luci. Si noti che ogni stringa di luci viene creata come gruppo univoco.

![](<../../.gitbook/assets/4 (6) (1).png>)

_**Nota**_ _È possibile che alcune linee passino attraverso l'insegna "Groove Coffee", poiché il plug-in della luce stringa crea una curva catenaria che va a sparire in maniera realistica sotto l'insegna stessa._

4 - Provare a creare più luci stringa utilizzando le altre linee guida predefinite e/o creando alcune linee guida personalizzate. Utilizzare le impostazioni del plug-in per ottenere risultati diversi.

5 - Per mantenere ordinato il modello, al termine consigliamo di raggruppare tutte le linee guida e posizionare tale gruppo sul layer **Helper Geometry**, nonché assegnare tutti i gruppi di luci stringa al layer **Context – Exterior Lighting**. Ciò impedirà la visualizzazione delle linee guida in una qualsiasi delle scene "Eye Level" dove non desideriamo vederle. Al termine, i risultati dovrebbero essere simili alla schermata successiva.

![](<../../.gitbook/assets/5 (3) (1).png>)

_**Nota**_ _A differenza della geometria creata da uno script di Dynamo, che può essere aggiornata e rigenerata mediante la_ _**tavolozza Proprietà**, gli oggetti creati da un plug-in sono (per la maggior parte) solo la normale geometria di FormIt. Una volta creati, possono essere modificati solo utilizzando gli strumenti di modellazione incorporati di FormIt._
