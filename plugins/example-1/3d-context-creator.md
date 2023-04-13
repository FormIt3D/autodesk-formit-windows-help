# 3D Context Creator

![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## Che cos'è?

3D Context Creator è un plug-in di facilissimo utilizzo che consente di generare edifici in contesto 3D all'interno di FormIt. 

Questo plug-in consente di visualizzare la planimetria del progetto con il contesto circostante e di prendere decisioni informate nella fase iniziale del processo di progettazione.

Questo plug-in recupera i dati da [OpenStreet Map](https://www.openstreetmap.org/about) per trasformarli in geometrie di FormIt. Il codice sorgente per questo plug-in è disponibile su [Github](https://github.com/matterlab-co/FormIt-Context-Plugin).

## Come utilizzarlo

Per installarlo, è sufficiente attivare il plug-in da Plugin Manager come si farebbe con qualsiasi altro plug-in.

![](../../.gitbook/assets/contextcreator3.png)

Una volta attivato, il plug-in dovrebbe essere visualizzato sul lato destro dell'app ed essere pronto per l'uso.

![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

Se per la planimetria non è già stata configurata una posizione, è possibile fare clic sul collegamento **Set Location...** per impostare una posizione e definire il contorno che verrà utilizzato per la generazione del contesto 3D.

Dopo aver impostato la posizione, 3D Context Creator viene aggiornato con la posizione corrente e il pulsante viene attivato:

![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

3D Context Creator utilizzerà semplicemente le estensioni dell'immagine satellitare per generare il contesto 3D. È sufficiente fare clic su **Generate 3D Context**.

A seconda delle estensioni dell'immagine satellitare e della complessità degli edifici, la generazione potrebbe richiedere alcuni secondi.

Gli edifici in contesto 3D verranno automaticamente posizionati in un'istanza del gruppo e posizionati su un layer denominato Context Buildings. È possibile attivare o disattivare la visibilità del contesto utilizzando questo layer.

![](<../../.gitbook/assets/3D Context Creator_layers.png>)

![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

Se in seguito si decide di modificare la posizione o di regolare l'ambito dell'immagine satellitare, è possibile fare nuovamente clic su **Generate 3D Context** per rigenerare gli edifici. 

_Tenere presente che la rigenerazione del contesto sostituirà l'istanza del gruppo contenente gli edifici con una nuova istanza, pertanto le modifiche apportate agli edifici andranno perse._ Per evitare ciò, è possibile separare il contenitore del contesto e quindi raggrupparlo.

## **Alcuni esempi**

Provare a indovinare quali città iconiche sono rappresentate nei seguenti contesti:

![](<../../.gitbook/assets/image (2) (1).png>)

![](<../../.gitbook/assets/image (34).png>)

![](<../../.gitbook/assets/image (13) (1) (1).png>)

![](<../../.gitbook/assets/image (59).png>)
