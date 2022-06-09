# Debug

Il debug di un plug-in di FormIt richiede procedure diverse a seconda del motore utilizzato. Per ulteriori informazioni sui motori, consultare la [sezione precedente](client-side-vs-web-side-engines.md).

### **Debug lato client (FormIt)**

Per eseguire il debug del codice lato FormIt, che si applica sia ai plug-in basati sulla barra degli strumenti che a quelli basati sul pannello, è possibile aggiungere una riga nel codice per visualizzare il debugger JS incorporato dell'applicazione desktop:

`debugger`

![](../../../.gitbook/assets/debugger.gif)

### **Debug lato Web (HTML)**

I plug-in di FormIt basati sul pannello offrono il debug dell'interfaccia utente basata su pagine HTML, poiché i pannelli sono fondamentalmente siti Web HTML con stili e script.

Per eseguire il debug del codice lato HTML per i plug-in incorporati in un pannello, inclusi script e stili:

* **FormIt per Windows 2021.1 e versioni successive**
   * Fare clic con il pulsante destro del mouse sulla pagina HTML del plug-in e selezionare Debug per visualizzare il debugger HTML incorporato dell'applicazione.

![](../../../.gitbook/assets/debugpanelplugin.gif)

* **FormIt per il Web**
   * Utilizzare il tasto di scelta rapida F12 o CTRL+MAIUSC+I per visualizzare il debugger HTML del browser.

![](../../../.gitbook/assets/debugonweb.gif)

