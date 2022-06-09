# So verwenden Sie Plugins

![](<../.gitbook/assets/g3 (1).gif>)

## Plugin Manager

Der FormIt Plugin Manager ist Ihre zentrale Anlaufstelle für die Suche und Verwaltung von Plugins.

Der Plugin Manager wird beim Starten von FormIt automatisch geladen, sofern FormIt über Internetzugriff verfügt.

Sie können darauf zugreifen, indem Sie auf das Registerkartensymbol![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PluginManagerTab.PNG) auf der rechten Seite der App klicken:

![](../.gitbook/assets/c1.PNG)

## Plugin-Kategorien

Der Plugin Manager ordnet Plugins in Kategorien an, damit Sie die Plugins finden, die Sie am meisten interessieren.

![](../.gitbook/assets/d16.png)

**Installierte Plugins:** Bereits vom Benutzer installierte Plugins.&#x20;

**Empfohlene Plugins:** Plugins, die das FormIt-Team zur Erweiterung der Kernfunktionen von FormIt und zur Nutzung neuer Arbeitsabläufe empfiehlt. Von der Community entwickelte Plugins werden hier angezeigt, nachdem sie vom FormIt-Team geprüft wurden.\
GitHub-Tag: _formit-plugin-recommended_

**Öffentliche Plugins:** Von der Community erstellte Plugins. Plugins in dieser Kategorie wurden vom FormIt-Team nicht überprüft oder genehmigt. \
GitHub-Tag: _formit-plugin_

**Plugins für Entwickler**: Plugins, die von der Community erstellt wurden, um die Erstellung neuer FormIt-Plugins zu ermöglichen. \
GitHub-Tag: _formit-plugin-developers_

## Hinzufügen Ihres privaten oder lokalen Plugins

Wenn Sie [Ihr eigenes Plugin entwickeln](how-to-develop-plugins/), können Sie die private URL in das Feld unten in der Gruppe einfügen und auf (+) klicken:

![](../.gitbook/assets/d4.PNG)

Weitere Informationen zum Hinzufügen Ihres privaten oder lokalen Plugins finden Sie unter [Vorschau eines Plugins im Plugin Manager ](how-to-develop-plugins/advanced-development/previewing-a-plugin-in-the-plugin-manager.md)

## Zurücksetzen des Plugin Manager

Der Plugin Manager verwendet Registrierungsschlüssel unter Windows, um die installierten Repositorys und Plugins zu speichern. Wenn Sie den Plugin Manager auf die Vorgaben zurücksetzen müssen, löschen Sie den folgenden Registrierungsschlüssel:

`Computer\HKEY_CURRENT_USER\Software\Autodesk\FormIt 360\Plugins`

⚠️ Anmerkung: Dadurch werden alle vom Benutzer hinzugefügten Repositorys und Plugins deinstalliert, und der Plugin Manager wird zurückgesetzt, sodass nur die integrierten Repositorys und Plugins enthalten sind.

## Installieren von Plugins

Der [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) enthält eine Reihe von Plugins, die in verschiedenen Kategorien angeordnet sind. Jedes Plugin verfügt über einen Namen, eine Beschreibung, einen GitHub-Link und einen Installationsschalter.&#x20;

![](../.gitbook/assets/d5.PNG)

Um ein Plugin zu installieren, aktivieren Sie einfach den Schalter neben dem Namen des Plugins.&#x20;

![](../.gitbook/assets/d6.png)

Das Symbol des ausgewählten Plugins wird im rechten Bereich angezeigt. Klicken Sie darauf, um die Benutzeroberfläche des Plugins anzuzeigen.

![](../.gitbook/assets/d7.PNG)

## Verwenden von Plugins

Jedes Plugin verfügt über eine eigene, von seinem Entwickler definierte Benutzeroberfläche. Ein Plugin enthält in der Regel eine Reihe von Anweisungen zur Verwendung, eine Reihe von Parametern (Textfelder, Schieberegler, Kontrollkästchen usw.) sowie eine oder mehrere Schaltflächen zur Ausführung des Plugins.

Wir verwenden eines der einfacheren Beispiele im Plugin Manager: Fillet 2D Corners. Zunächst laden wir das Plugin aus dem Abschnitt der empfohlenen Plugins im Plugin Manager. Anschließend legen wir gemäß den Anweisungen des Entwicklers den Abrundungsradius fest, wählen eine Gruppe von Flächen zum Abrunden aus und klicken auf die Schaltfläche Fillet Corners.

![](../.gitbook/assets/g4.gif)

##

