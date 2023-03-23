# Hosten eines Plugins auf einem lokalen Server

Bevor Sie die Vorschau eines geklonten Plugins in FormIt anzeigen können, müssen Sie es auf einem lokalen Server hosten.

### **Anzeigen des Terminals in einer IDE**

Sie haben die Möglichkeit, den Server in Visual Studio Code zu starten, anstatt ein separates Terminal-Fenster zu verwenden. **** Stellen Sie vor dem Öffnen eines Terminals sicher, dass der richtige Ordner in Visual Studio Code geöffnet ist.

Ansicht > Terminal (oder Tastenkombination STRG + \`)

\![](<../../../.gitbook/assets/image (11) (1).png>)

### Einrichten eines HTTP-Servers

Ein gut geeigneter HTTP-Server ist der [http-server](https://www.npmjs.com/package/http-server) von npm.

Zuerst müssen Sie [NodeJS](https://nodejs.org/en/) herunterladen und installieren, falls noch nicht geschehen.

Wenn in den folgenden Schritten Fehler auftreten, starten Sie den Computer neu, um die NodeJS-Installation abzuschließen.

Geben Sie in der Befehlszeile Folgendes ein, um den _http-server_ von npm global (einmalige Einrichtung) zu installieren.

* `npm install http-server -g`

\![](<../../../.gitbook/assets/image (47).png>)

### Starten des lokalen Servers

Wenn die Einrichtung abgeschlossen ist, führen Sie den folgenden Befehl im Terminal aus, um den http-server von npm zu starten:

* `http-server`

\![](<../../../.gitbook/assets/image (84).png>)

Tipp 1: Bei Problemen mit der Ausführung des http-server (global oder lokal installiert) kann es hilfreich sein, ihn direkt über npx auszuführen:

* `npx http-server`

Tipp 2: Wenn bei Windows 10-/11-Benutzern beim Ausführen eines Skripts auf dem neuen Computer ein Fehler auftritt, kann dies daran liegen, dass die Einstellungen deaktiviert sind. Fehlerbehebung:

* Starten Sie das PowerShell-Skript als Administrator.
* Geben Sie Folgendes ein: `Set-ExecutionPolicy RemoteSigned`

### Entwickeln für FormIt Web

Um für FormIt Web zu entwickeln, führen Sie stattdessen einfach den folgenden Befehl aus:

* `http-server --cors`

\![](<../../../.gitbook/assets/image (10) (1).png>)

### Überprüfen Ihres Servers

Sie können Ihren Server überprüfen, indem Sie in Ihrem Webbrowser zu folgender Adresse navigieren:

* http://localhost:8080

Ihre Projektordnerdateien sollten nun im Browserfenster angezeigt werden.

**Wenn Sie einen anderen Webserver als npm verwenden, weicht die Vorgabeadresse/der Vorgabeanschluss möglicherweise von der hier angegebenen Adresse ab.

\![](<../../../.gitbook/assets/image (41).png>)
