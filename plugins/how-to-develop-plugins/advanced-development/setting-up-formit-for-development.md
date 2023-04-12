# Einrichten von FormIt für die Entwicklung

Zum Testen und Erstellen von Plugins in der FormIt Desktop-App benötigen Sie FormIt for Windows v17.0 oder höher.

### **Anzeigen des Skript-Editors und der Skriptausgabe**

Wechseln Sie im oberen Menü von FormIt zu **Fenster** oben, und aktivieren Sie die Kontrollkästchen **Skript-Editor** und **Skriptausgabe**.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

Die Gruppen Skript-Editor und Skriptausgabe werden unten im FormIt-Fenster angezeigt.

Wechseln Sie mithilfe der Schaltflächen unten zwischen dem Skript-Editor und der Skriptausgabe.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

Sie können beide Gruppen auch nebeneinander anordnen. Klicken Sie auf die Schaltfläche neben dem x in der oberen rechten Ecke, um eine der Gruppen zu lösen, ziehen Sie dann die Gruppen, und legen Sie sie nebeneinander ab:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **Skript-Editor**

Der Skript-Editor bietet eine einfache Entwicklungsumgebung, in der Sie Code schreiben und testen können.

Der Skript-Editor speichert geschriebenen Code in der Datei scratch.js in dem Verzeichnis, in dem sich die Datei FormIt.exe befindet.

Oben befinden sich zwei Schaltflächen:

**Ausführen** ![](<../../../.gitbook/assets/image (8) (1).png>): Führt den gesamten im Fenster geschriebenen Code aus.

**Auswahl ausführen** ![](<../../../.gitbook/assets/image (52).png>): Nur die ausgewählten/hervorgehobenen Codezeilen werden ausgeführt.

### **Skriptausgabe**

Das Fenster Skriptausgabe zeigt alle Meldungen an, die über Plugins auf die Konsole geschrieben werden.

Sie können die Ausgabe löschen, indem Sie `console.clear();` im Skript-Editor ausführen.

## Arbeiten mit Beispiel-Plugins

Nach dem [Klonen eines Repositorys](cloning-a-sample-plugin.md) und dem [Einrichten eines Webservers](hosting-a-plugin-on-a-local-server.md) können Sie jetzt Ihre lokalen Plugins in FormIt anzeigen lassen.

Sie können jedes beliebige Plugin laden oder installieren. Für diese Übung installieren Sie jedoch sowohl ein gruppenbasiertes als auch ein werkzeugkastenbasiertes Plugin. Es wird davon ausgegangen, dass Ihr http-server von npm an Anschluss 8080 ausgeführt wird, der beide Beispiel-Repositorys hostet.

### **Laden im Vergleich zu Installieren**

`FormIt.LoadPlugin();` lädt das Plugin nur für die aktuelle Sitzung. Das Plugin wird automatisch entfernt, wenn die App geschlossen und neu gestartet wird.

Dies ist eine gute Möglichkeit, ein Plugin vorübergehend nur für Tests in der aktuellen Sitzung zu manifestieren.

`FormIt.InstallPlugin();` bewirkt, dass das Plugin unter Verwendung eines Registrierungsschlüssels dauerhaft beibehalten wird. Dies ist besonders für Plugins geeignet, die Sie über mehrere Sitzungen häufig verwenden.

Unter Windows werden die folgenden Registrierungsschlüssel verwendet, um Plugins dauerhaft beizubehalten:

* Plugins: Computer\\HKEY_CURRENT_USER\\Software\\Autodesk\\FormIt 360\\Plugins\\InstalledPlugins

Verwenden Sie `FormIt.UninstallPlugin();` zum Deinstallieren.

In den folgenden Beispielen können Sie, sofern nicht anders angegeben, entweder _Installieren_ oder _Laden_ verwenden, je nachdem, ob die Ergebnisse der Übung beibehalten werden sollen oder nicht.

### **Beispiel für Werkzeugkasten-Plugin: Flip Along**

Führen Sie im Skript-Editor Folgendes aus:

Wenn Sie einen lokalen Server ausführen:

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

Beim Laden aus dem [FormIt GitHub-Repository](https://github.com/FormIt3D/) (Internetverbindung erforderlich):

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

Der Werkzeugkasten Flip Along sollte nun oben im Anwendungsfenster angezeigt werden:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **Beispiel für HTML-Gruppen-Plugin: Properties Plus**

Führen Sie im Skript-Editor Folgendes aus:

Wenn Sie einen lokalen Server ausführen:

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

Beim Laden aus dem [FormIt GitHub-Repository](https://github.com/FormIt3D/) (Internetverbindung erforderlich):

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

Die Gruppe Properties Plus sollte nun auf der rechten Seite des Anwendungsfensters angezeigt werden:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **Beispiel für ein Dialogfeld-Plugin für Modusabhängig und Modusunabhängig**

Dialogfeld-Plugins sind Unikate: Sie können nur geladen, nicht installiert werden.

Führen Sie im Skript-Editor Folgendes aus:

Wenn Sie einen lokalen Server ausführen:

* Modusabhängig: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* Modusunabhängig: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

Beim Laden aus dem [FormIt GitHub-Repository](https://github.com/FormIt3D/) (Internetverbindung erforderlich):

* Modusabhängig: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* Modusabhängig: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

Nun sollte die Gruppe Hello Block! aus dem HTML-Gruppenbeispiel auf dem Bildschirm entweder als modusabhängiges oder modusunabhängiges Dialogfeld angezeigt werden.
