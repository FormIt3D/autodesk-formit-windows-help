# Fehlerbehebung

Die Fehlerbehebung für ein FormIt-Plugin erfordert verschiedene Verfahren, je nach Engine, für die die Fehlerbehebung durchgeführt wird. (Weitere Informationen zu Engines finden Sie im [vorherigen Abschnitt](client-side-vs-web-side-engines.md).)

### **Fehlerbehebung auf der Client-Seite (FormIt)**

Um im FormIt-Seiten-Code, der sowohl für werkzeugkasten- als auch gruppenbasierte Plugins gilt, eine Fehlerbehebung durchzuführen, können Sie eine Codezeile hinzufügen, um den integrierten JS-Debugger der Desktopanwendung anzuzeigen:

`debugger`

![](../../../.gitbook/assets/debugger.gif)

### **Fehlerbehebung auf der Web-Seite (HTML)**

Die gruppenbasierten FormIt-Plugins bieten HTML-basierte Benutzeroberflächen-Fehlerbehebung, da es sich bei den Gruppen im Wesentlichen um HTML-Websites mit Stilen und Skripten handelt.

So führen Sie die Fehlerbehebung für HTML-Seiten-Code für Plugins aus, die in einer Gruppe integriert sind, einschließlich Skripten und Stilen:

* **FormIt for Windows 2021.1 und neuer**
   * Klicken Sie mit der rechten Maustaste auf die HTML-Seite des Plugins, und klicken Sie auf Debug, um den integrierten HTML-Debugger der Anwendung anzuzeigen.

![](../../../.gitbook/assets/debugpanelplugin.gif)

* **FormIt for Web**
   * Verwenden Sie die Tastenkombination F12 oder STRG + UMSCHALT + I, um den HTML-Debugger des Browsers aufzurufen.

![](../../../.gitbook/assets/debugonweb.gif)

