# Test di un plug-in della barra degli strumenti e di un plug-in del pannello HTML combinati

È possibile verificare facilmente i plug-in in corso utilizzando l'[Editor script](../advanced-development/setting-up-formit-for-development.md) incorporato in FormIt per Windows.

Si consiglia di utilizzare `FormIt.LoadPlugin("URL");` durante il test, che carica temporaneamente i plug-in per questa sessione (scompariranno al riavvio di FormIt).&#x20;

Una volta completato il test, è possibile mantenere il plug-in tra le sessioni utilizzando `FormIt.InstallPlugin("URL");`.

**FormIt per Windows v17 e versioni successive**

****

### **Plug-in sulla barra degli strumenti**

Caricare il plug-in in FormIt per visualizzare l'interfaccia utente più recente e testare le ultime funzionalità:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Apportare alcune modifiche, quindi caricare nuovamente il plug-in utilizzando il comando precedente.

È possibile caricare molte istanze dello stesso plug-in nella sessione corrente durante il test, ognuna con la sua interfaccia utente.

Assicurarsi di utilizzare l'ultima istanza dell'interfaccia utente per testare le modifiche più recenti.



### **Plug-in del pannello HTML**

Caricare il plug-in in FormIt per visualizzare l'interfaccia utente più recente e testare le ultime funzionalità:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Apportare alcune modifiche, quindi fare clic con il pulsante destro del mouse sul pannello e selezionare Ricaricamento forzato per ricaricare il pannello con il codice HTML, CSS e gli script più recenti.

****

### **Anteprima del plug-in con Plugin Manager**

Una volta caricato il plug-in, consultare il [capitolo precedente](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md) di questa guida.

****

### **Forzatura della cancellazione della cache Web per i file .JSON**

Se si modifica il titolo o la descrizione all'interno del file manifest.json per un plug-in o un repository, potrebbe essere necessario cancellare la cache in FormIt per Windows per vedere che tali modifiche avranno effetto al successivo ricaricamento di Plugin Manager.

FormIt per Windows memorizza la cache Web in questa posizione. Sarà necessario attivare gli elementi nascosti in Esplora risorse per visualizzare la cartella AppData.

* C:\Users\user\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

Per eliminare la cache Web, è sufficiente eliminare la cartella Default riportata sopra, quindi ricaricare Plugin Manager per visualizzare i titoli e le descrizioni aggiornati.
