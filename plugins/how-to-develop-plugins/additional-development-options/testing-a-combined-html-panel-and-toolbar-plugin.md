# Testen eines kombinierten HTML-Gruppen- und Werkzeugkasten-Plugins

Sie können Ihre in Bearbeitung befindlichen Plugins mithilfe des integrierten [Skript-Editors](../advanced-development/setting-up-formit-for-development.md) in FormIt for Windows ganz einfach testen.

Wir empfehlen, beim Testen `FormIt.LoadPlugin("URL");` zu verwenden, wodurch Plugins vorübergehend für diese Sitzung geladen werden (sie werden beim Neustart von FormIt ausgeblendet).&#x20;

Nach dem Testen können Sie das Plugin zwischen `FormIt.InstallPlugin("URL");`-Sitzungen beibehalten.

**FormIt for Windows v17 und neuer**

****

### **Werkzeugkasten-Plugins**

Laden Sie Ihr Plugin in FormIt, um die neueste Benutzeroberfläche zu sehen und die neuesten Funktionen zu testen:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Nehmen Sie einige Änderungen vor, und laden Sie das Plugin erneut mithilfe des obigen Befehls.

Sie können während des Tests in der aktuellen Sitzung mehrere Instanzen desselben Plugins laden, wobei jede Instanz eine eigene Benutzeroberfläche besitzt.

Verwenden Sie die neueste Benutzeroberflächen-Instanz, um sicherzustellen, dass Sie die neuesten Änderungen testen.



### **HTML-Gruppen-Plugins**

Laden Sie Ihr Plugin in FormIt, um die neueste Benutzeroberfläche zu sehen und die neuesten Funktionen zu testen:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Nehmen Sie einige Änderungen vor. Klicken Sie dann einfach mit der rechten Maustaste auf die Gruppe, und wählen Sie Neuladen erzwingen aus, um die Gruppe mit den neuesten HTML-, CSS- und Skriptversionen neu zu laden.

****

### **Vorschau Ihres Plugins mit dem Plugin Manager**

Sobald das Plugin geladen ist, finden Sie in einem [früheren Kapitel](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md) eine entsprechende Anleitung.

****

### **Erzwingen des Löschens des Web-Cache für JSON-Dateien**

Wenn Sie den Titel oder die Beschreibung in der Datei manifest.json für ein Plugin oder ein Repository ändern, müssen Sie möglicherweise das Löschen des Cache in FormIt for Windows erzwingen, damit diese Änderungen beim nächsten Laden des Plugin Managers wirksam werden.

FormIt for Windows speichert den Web-Cache hier. Sie müssen ausgeblendete Elemente in Windows Explorer aktivieren, um den Ordner AppData anzuzeigen.

* C:\Benutzer\Benutzer\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

Um den Web-Cache zu löschen, löschen Sie einfach den oben genannten Vorgabe-Ordner und laden dann den Plugin Manager neu, um die aktualisierten Titel und Beschreibungen zu sehen.
