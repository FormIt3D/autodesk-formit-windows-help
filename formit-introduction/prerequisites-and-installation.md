# Prerequisiti e installazione

## Download e installazione

* Scaricare la versione più recente di [FormIt per Windows](https://formit.autodesk.com/page/download).
* Utilizzare Autodesk Account per accedere o [creare un Autodesk Account gratuito qui](https://accounts.autodesk.com).
* Il modulo aggiuntivo FormIt per Revit è incluso in Revit 2017 e versioni successive. È inoltre possibile scaricare e installare manualmente il modulo aggiuntivo [dal sito Web Autodesk](https://formit.autodesk.com/page/formit-revit).

Le impostazioni a livello di applicazione per FormIt si trovano in Computer\HKEY\_CURRENT\_USER\SOFTWARE\Autodesk\FormIt 360\\.

## Configurazione di sistema consigliata

| Requisito | Dettagli |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sistema operativo** | <p>Microsoft® Windows® 8, 8.1, 10 o 11.</p><p><em>Nota Parallels Desktop non è supportato ufficialmente a causa di problemi di grafica e prestazioni ridotte nei driver OpenGL.</em></p> |
| **CPU** | <p>Processore Intel® Pentium®, Xeon® o serie i o processore AMD® equivalente con tecnologia SSE2.</p><p>CPU con la massima velocità di esecuzione.</p> |
| **Memoria** | Almeno 4 GB di RAM, consigliati almeno 8 GB. |
| **Scheda video (GPU)** | <p>È necessaria una scheda video NVIDIA o AMD dedicata che supporti OpenGL 3.3. È consigliato il supporto OpenGL 4.2.</p><p>Per i sistemi con schede video commutabili, seguire le istruzioni del produttore per assicurarsi che FormIt utilizzi sempre la GPU dedicata per le migliori prestazioni. Consultare le istruzioni per <a href="https://www.amd.com/en/support/kb/faq/dh-017">AMD </a>e <a href="http://nvidia.custhelp.com/app/answers/detail/a_id/2615/kw/manage%203d%20settings/related/1">NVIDIA</a>.</p><p>Per prestazioni e affidabilità ottimali, verificare che i driver della scheda video in uso siano aggiornati dal sito Web del produttore o da Windows Update.</p><p>In FormIt viene mostrato un messaggio all'avvio se non è possibile utilizzare la scheda video a causa di driver non aggiornati o altri problemi. Se FormIt non si avvia dopo l'aggiornamento dei driver, <a href="https://forums.autodesk.com/t5/formit-forum/bd-p/142">consultare i forum</a>.</p> |
| **Spazio su disco** | 1 GB di spazio libero su disco. |
| **Connettività e licenze** | <p>Quando si avvia FormIt per la prima volta, è necessaria una connessione ad Internet per accedere a Autodesk Account.</p><p>È inoltre necessaria una connessione ad Internet per caricare i plug-in all'avvio di FormIt. Se all'avvio non viene rilevata una connessione ad Internet, l'applicazione verrà avviata senza plug-in.</p><p>Per eseguire FormIt Pro in Windows, è necessario un Autodesk Account con un abbonamento cloud a FormIt Pro. FormIt Pro è disponibile come parte di <a href="https://www.autodesk.com/collections/architecture-engineering-construction/overview"><strong>Autodesk AEC Collection</strong></a>.</p> |

## Accesso offline

Quando si esegue FormIt per Windows per la prima volta, è necessario essere connessi ad Internet per poter convalidare la licenza. Dopo il primo accesso, è possibile utilizzare l'app offline per 30 giorni. Trascorso questo periodo, sarà necessario accedere online per convalidare nuovamente la licenza.

Quando si utilizza FormIt per Windows in modalità offline, alcune funzionalità saranno limitate:

* Lo strumento Imposta posizione non funziona, poiché richiede una connessione ad Internet per recuperare i dati satellitari e del terreno da Bing Maps.
   * Tuttavia, eventuali dati satellitari e del terreno esistenti già presenti nel modello derivanti da una sessione online precedente rimarranno.
* Eventuali plug-in, incluso Plugin Manager, non verranno caricati poiché ricevono il codice più recente da GitHub a ogni avvio dell'applicazione.
   * Soluzione: se si caricano tutti i plug-in in modalità online e si mantiene in esecuzione la sessione di FormIt quando si passa alla modalità offline, i plug-in precedentemente caricati rimarranno e funzioneranno normalmente.
* I materiali di esempio non verranno caricati, poiché provengono da un server ospitato nel cloud.
   * Soluzione: accedere alle cartelle delle categorie di materiali di esempio mentre si è connessi ad Internet. Le cartelle vengono scaricate e memorizzate nel computer in uso e possono essere utilizzate in un secondo momento quando si è offline.
* Non sarà possibile eseguire il salvataggio o l'apertura da Autodesk Docs, neanche dalla Libreria del contenuto.

## Impostazioni DPI di Windows consigliate

FormIt per Windows funziona meglio quando lo schermo di visualizzazione è impostato su una scala DPI inferiore o pari al 125% in Windows.

È possibile modificare questa impostazione in Windows 10 effettuando le seguenti operazioni:

* Cercare Schermo nel menu Start e scegliere Cambia le impostazioni dello schermo.
* Selezionare il rettangolo che rappresenta il monitor che verrà utilizzato con FormIt.
* Nella sezione Ridimensionamento e layout, aprire l'elenco a discesa Modifica la dimensione di testo, app e altri elementi e selezionare un valore pari o inferiore al 125%.

## Risoluzione dei problemi

### Errore di sistema di Windows 10 Pro N

Se si esegue FormIt in Windows 10 Pro N versione 1909 o successiva, è possibile che venga visualizzato il seguente messaggio di errore:

![FormIt.exe System Error on Windows 10](<../.gitbook/assets/windows 10 error message.png>)

Ciò è dovuto ad un problema noto relativo a determinate versioni di Windows 10 Pro N. Per evitare questo errore, scaricare il Feature Pack multimediale per la versione di Windows 10 in uso qui: [Elenco dei Feature Pack multimediali per Windows edizioni N](https://support.microsoft.com/it-it/topic/elenco-dei-feature-pack-multimediali-per-windows-edizioni-n-c1c6fffa-d052-8338-7a79-a4bb980a700a).

### Impossibile eseguire l'accesso

Quando si tenta di accedere al proprio account in FormIt, la finestra di dialogo di accesso potrebbe bloccarsi, impedendo di procedere. In tal caso, potrebbe essere necessario sbloccare \*.autodesk.com nel firewall di rete. Contattare il reparto IT per richiedere assistenza.
