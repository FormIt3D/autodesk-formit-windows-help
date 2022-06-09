# Versionierung

Während Sie Ihr Plugin entwickeln und aktualisieren, müssen Sie möglicherweise irgendwann den Code versionieren.

Die FormIt-APIs können sich beispielsweise zwischen verschiedenen Versionen ändern. Sie möchten vielleicht, dass die neue Version Ihres Plugins neue FormIt- oder WSM-APIs verwendet, wollen das Plugin jedoch auch in älteren Clients nutzen können.

Ab FormIt **v18.0** können Sie die Versionierung für Ihr Plugin in drei einfachen Schritten implementieren:

* Fügen Sie eine _versions.json_-Datei zum Stammverzeichnis des Plugin-Verzeichnisses hinzu.
* Geben Sie jede kompatible FormIt-Version und das Verzeichnis mit den Plugin-Dateien in _versions.json_ an.
* Verwenden Sie die interne Versionierungsnummer von FormIt oder die Buildnummer in FormIt unter Info > Info.



### So organisieren Sie die Versionierung für Ihr Plugin

Organisieren Sie Ihre Plugin-Dateien und -Verzeichnisse so, dass sie _versions.json_ entsprechen.

Ihre _versions.json_-Datei sollte so aussehen:

```
        [
            {
                "version":{
                    "major":18,
                    "minor":0
                },
                "path":"v18_0"
            },
            {
                "version":{
                    "major":19,
                    "minor":1
                },
                "path":"v19_0"
            }
        ]

```

Die oben genannten Pfade _v18\_0_ und _v19\_0_ müssen gültige Unterpfade aus dem Stammverzeichnis Ihres Verzeichnisses/Repositorys sein.

![](../../../.gitbook/assets/i1.png)

![](../../../.gitbook/assets/i2.png)

![](../../../.gitbook/assets/i3.png)

Eine gute Möglichkeit, dies zu handhaben, besteht darin, Ihren Plugin-Code in Unterverzeichnisse zu verschieben. Mit der obigen Datei _versions.json_ würde eine Verzeichnisstruktur wie folgt aussehen:

* **versions.json** (Datei)
* **v18\_0** (Verzeichnis)

   * **manifest.json** (Datei)
   * **plugin.html** (Datei)
   * **plugin.js** (Datei)


* **v19\_0** (Verzeichnis)
   * **manifest.json** (Datei)
   * **plugin.html** (Datei)
   * **plugin.js** (Datei)

Optionale Eigenschaften für Versionen sind exactVersion und lastVersion. exactVersion gibt an, dass die Version genau mit der Version von FormIt übereinstimmen muss. lastVersion gibt die letzte Version an, die in FormIt ausgeführt werden darf.\


```
[
    {
      "version":{
        "major":18,
        "minor":0,
        "exactVersion":true
        },
        "path":"v18_0"
    },
    {
        "version":{
            "major":19,
            "minor":1,
            "lastVersion":true
       },
        "path":"v19_0"
    }
 ]
```

Es ist auch möglich, Git-Verzweigungen/-Tags/-Festschreibungen für Ihre Pfade zu verwenden.

Wenn Sie mit einer Vorabversion oder einem Beta-Build von FormIt arbeiten und Änderungen an einem Plugin testen möchten, das nur mit der Vorabversion funktioniert:

* Führen Sie die oben beschriebenen Schritte aus, außer wenn Sie den Dateinamen _versions\_prerelease.json_ verwenden.
* Wenn Sie _versions\_prerelease_ in Ihrem Repository festschreiben, sollten Sie es entfernen, wenn diese Vorabversion von FormIt veröffentlicht wird.
   * Andernfalls laden zukünftige Vorversionen von FormIt das Plugin von einem Speicherort, der möglicherweise veraltet oder für eine ältere Version bestimmt ist.
