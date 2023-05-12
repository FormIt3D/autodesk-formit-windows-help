# Hosting di un plug-in su un server locale

Prima di poter visualizzare l'anteprima di un plug-in clonato in FormIt, è necessario ospitarlo su un server locale.

### **Visualizzazione del terminale in IDE**

È possibile avviare il server all'interno di Visual Studio Code, anziché in una finestra di terminale separata.**** Prima di aprire un terminale, assicurarsi che in Visual Studio Code sia aperta la cartella corretta.

Vista > Terminale (o tasto di scelta rapida CTRL+')

![](<../../../.gitbook/assets/image (11) (1).png>)

### Impostazione di un server HTTP

Un server HTTP che funziona correttamente è [http-server](https://www.npmjs.com/package/http-server) di npm.

Innanzitutto, è necessario scaricare e installare [NodeJS](https://nodejs.org/en/), se non è già installato.

Se si verificano errori nei seguenti passaggi, provare a riavviare il computer per completare l'installazione di NodeJS.

Alla riga di comando, immettere quanto segue per installare globalmente _http-server_ di npm (un'unica installazione).

* `npm install http-server -g`

![](<../../../.gitbook/assets/image (47).png>)

### Avvio del server delle licenze

Al termine dell'installazione, eseguire il seguente comando nel terminale per avviare http-server di npm:

* `http-server`

![](<../../../.gitbook/assets/image (84).png>)

Suggerimento 1 In caso di eventuali problemi con l'esecuzione di http-server (installato globalmente o localmente), potrebbe essere utile eseguirlo direttamente tramite npx:

* `npx http-server`

Suggerimento 2 Per gli utenti di Windows 10/11, se si verifica un errore durante l'esecuzione di uno script nel nuovo computer, ciò potrebbe essere dovuto al fatto che le impostazioni siano disattivate. Per risolvere questo problema:

* Avviare lo script PowerShell come amministratore.
* Immettere: `Set-ExecutionPolicy RemoteSigned`

### Sviluppo di FormIt Web

Per sviluppare per FormIt Web, è sufficiente eseguire il seguente comando:

* `http-server --cors`

![](<../../../.gitbook/assets/image (10) (1).png>)

### Verifica del server

È possibile verificare il server accedendo al seguente indirizzo nel browser Web:

* http://localhost:8080

I file delle cartelle di progetto dovrebbero essere visualizzati nella finestra del browser.

**Se si utilizza un server Web diverso da npm, l'indirizzo/la porta di default potrebbe essere differente.

![](<../../../.gitbook/assets/image (41).png>)
