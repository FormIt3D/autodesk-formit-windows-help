# Einführung in Plugins

![](../.gitbook/assets/gg4.gif)

Plugins sind benutzerdefinierte Software-Erweiterungen, die die Kernfunktionalität von FormIt erweitern. Plugins können Ihre Arbeitsabläufe bei der 3D-Modellierung in FormIt verbessern, optimieren und vereinfachen.&#x20;

Plugins können verwendet werden, um Objekte zu generieren, Änderungen an vorhandenen Objekten vorzunehmen oder Informationen über ein Objekt zu extrahieren. Plugins können auch über funktionsreiche Webschnittstellen Daten anzeigen und Steuerelemente und Eingaben direkt in der Anwendung bereitstellen.&#x20;

## Zugriff auf Plugins

Plugins stehen im [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) in der Desktop- und Web-Version von FormIt zur Verfügung, sofern Sie mit dem Internet verbunden sind. Plugins bestehen aus einer Reihe von Dateien und Ordnern, die auf GitHub bzw. auf einem lokalen Server gehostet werden, wenn Sie Ihr eigenes Plugin erstellen.&#x20;

![](../.gitbook/assets/c17.PNG)

### Plugins benötigen einen Internetzugang

Externe Plugins (nicht lokal gehostete Plugins) erfordern eine Internetverbindung, um erstmalig geladen zu werden, was bedeutet:

* Externe Plugins werden nicht geladen, wenn beim Starten von FormIt keine Internetverbindung erkannt wird. Nach dem Laden können einige externe Plugins für diese Sitzung im Offline-Modus arbeiten, andere können jedoch unterbrochen werden, bis die Verbindung wiederhergestellt ist.&#x20;
* Externe Plugins laden bei jeder Ausführung den neuesten Code auf dem Server, sodass ihre Funktionalität aktualisiert wird, sobald der Autor eine Änderung vornimmt. Plugins werden asynchron geladen, was bedeutet, dass sich die Reihenfolge der Plugins in der FormIt-Benutzeroberfläche mit jeder neuen Sitzung ändern kann.

## Quelle öffnen

Plugins sind Open-Source-Produkte, sodass Sie die Plugins im [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) kostenlos verwenden können. Sie können Ihre Plugins einfach publizieren und freigeben und andere Plugins auf GitHub finden, um zu verstehen, wie sie erstellt wurden.&#x20;

Wenn Sie Entwickler sind und weitere Informationen zum Publizieren Ihrer Plugins benötigen, finden Sie weitere Informationen unter [Hosting eines Plugins auf GitHub](how-to-develop-plugins/advanced-development/hosting-a-plugin-on-github.md).&#x20;

Wenn Sie ein Plugin für den privaten Gebrauch erstellen möchten, können Sie es mithilfe eines lokalen Dienstes entwickeln und hosten. Weitere Informationen finden Sie unter [Verwenden einer IDE. ](how-to-develop-plugins/advanced-development/using-an-ide.md)

![](../.gitbook/assets/c18.PNG)



## Kontakt

Wenn Sie Hilfe zu FormIt-Plugins benötigen, schreiben Sie uns im [FormIt-Forum](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=de).

![](../.gitbook/assets/c19.PNG)

&#x20;

&#x20;
