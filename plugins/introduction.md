# Introduzione ai plug-in

![](../.gitbook/assets/gg4.gif)

I plug-in sono aggiunte software personalizzate che ampliano le funzionalità principali di FormIt. I plug-in consentono di migliorare, potenziare e semplificare i workflow di modellazione 3D in FormIt.&#x20;

I plug-in possono essere utilizzati per generare oggetti, apportare modifiche agli oggetti esistenti o estrarre informazioni su un oggetto. I plug-in possono inoltre utilizzare interfacce Web complete per visualizzare i dati e fornire controlli e input direttamente nell'applicazione.&#x20;

## Accesso ai plug-in

I plug-in sono disponibili in [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) nelle versioni di FormIt desktop e per il Web, purché sia presenta una connessione ad Internet. I plug-in sono costituiti da una serie di file e cartelle ospitati su GitHub o su un server locale nel caso della creazione di plug-in personalizzati.&#x20;

![](../.gitbook/assets/c17.PNG)

### Accesso ad Internet richiesto per i plug-in

I plug-in esterni (i plug-in non ospitati localmente) richiedono una connessione ad Internet per il caricamento iniziale, il che significa che:

* I plug-in esterni non vengono caricati se, all'avvio di FormIt, non viene rilevata alcuna connessione ad Internet. Una volta caricati, alcuni plug-in esterni possono continuare a lavorare in modalità offline per tale sessione, ma altri potrebbero interrompersi fino al ripristino della connettività.&#x20;
* I plug-in esterni caricano il codice più recente sul server ad ogni esecuzione, in modo che le loro funzionalità vengano aggiornate ogni volta che l'autore esegue il push di una modifica. I plug-in vengono caricati in modo asincrono, ovvero l'ordine dei plug-in nell'interfaccia di FormIt può cambiare con ogni nuova sessione.

## Apri origine

I plug-in sono open source. Ciò significa che è possibile utilizzare gratuitamente i plug-in in [Plugin Manager](how-to-use-plug-ins.md#plugin-manager), pubblicarli e condividerli facilmente e trovarne altri su GitHub per capire come sono stati creati.&#x20;

Per gli sviluppatori e se si desidera ulteriori informazioni su come pubblicare i plug-in, vedere [Hosting di un plug-in su GitHub](how-to-develop-plugins/advanced-development/hosting-a-plugin-on-github.md).&#x20;

Se si desidera creare un plug-in per uso privato, è possibile svilupparlo e ospitarlo utilizzando un servizio locale. Per ulteriori informazioni, vedere [Utilizzo di un IDE. ](how-to-develop-plugins/advanced-development/using-an-ide.md)

![](../.gitbook/assets/c18.PNG)



## Contattateci

Se è necessaria assistenza per i plug-in di FormIt, farne richiesta sul [forum di FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142).

![](../.gitbook/assets/c19.PNG)

&#x20;

&#x20;
