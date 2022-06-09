# Voraussetzungen und Installation

## Download und Installation

* Laden Sie die neueste Version von [FormIt for Windows](https://formit.autodesk.com/page/download) herunter.
* Melden Sie sich mit Ihrem Konto bei Autodesk Account an, oder [erstellen Sie hier ein kostenloses Konto bei Autodesk Account](https://accounts.autodesk.com).
* Das FormIt-Zusatzmodul für Revit ist in Revit 2017 und höher enthalten. Sie können das Zusatzmodul auch [von unserer Website](https://formit.autodesk.com/page/formit-revit) herunterladen und manuell installieren.

Einstellungen auf Anwendungsebene für FormIt finden Sie unter Computer\HKEY\_CURRENT\_USER\SOFTWARE\Autodesk\FormIt 360\\.

## Empfohlene Systemkonfiguration

| Anforderung | Details |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Betriebssystem** | <p>Microsoft® Windows® 8, 8.1, 10 oder 11</p><p><em>Anmerkung: Parallels Desktop wird aufgrund von Leistungs- und Grafikproblemen bei OpenGL-Treibern offiziell nicht unterstützt.</em></p> |
| **CPU** | <p>Intel® Pentium®-, Xeon®- oder i-Series-Prozessor oder entsprechender AMD®-Prozessor mit SSE2-Technologie.</p><p>Höchstmögliche CPU-Geschwindigkeit wird empfohlen.</p> |
| **Arbeitsspeicher** | Mindestens 4 GB RAM, 8 GB oder mehr empfohlen. |
| **Grafikkarte (GPU)** | <p>Eine eigenständige NVIDIA- oder AMD-Grafikkarte mit Unterstützung für OpenGL 3.3 ist erforderlich. Unterstützung für OpenGL 4.2 wird dringend empfohlen.</p><p>Bei Systemen mit umschaltbaren Grafikkarten befolgen Sie die Anweisungen des Herstellers, um sicherzustellen, dass FormIt immer die dedizierte GPU verwendet und Sie beste Ergebnisse erhalten. Siehe Anweisungen für <a href="https://www.amd.com/en/support/kb/faq/dh-017">AMD</a> und <a href="http://nvidia.custhelp.com/app/answers/detail/a_id/2615/kw/manage%203d%20settings/related/1">NVIDIA</a>.</p><p>Um eine optimale Leistung und Zuverlässigkeit zu erzielen, stellen Sie sicher, dass die Grafikkartentreiber auf dem neuesten Stand sind. Informationen hierzu finden Sie auf der Website des Herstellers oder bei Windows Update.</p><p>FormIt zeigt beim Start eine Meldung an, wenn die Grafikkarte aufgrund von veralteten Treibern oder anderen Problemen nicht verwendet werden kann. Wenn FormIt nach der Aktualisierung der Treiber nicht gestartet werden kann, <a href="https://forums.autodesk.com/t5/formit-forum/bd-p/142">sehen Sie in den Foren nach</a>.</p> |
| **Festplattenspeicherplatz** | 1 GB freier Festplattenspeicherplatz |
| **Konnektivität und Lizenzierung** | <p>Beim erstmaligen Starten von FormIt ist eine Internetverbindung erforderlich, um sich bei Ihrem Konto bei Autodesk Account anzumelden.</p><p>Eine Internetverbindung ist auch erforderlich, um Plugins beim Starten von FormIt zu laden. Wenn beim Start keine Internetverbindung erkannt wird, wird die Anwendung ohne Plugins gestartet.</p><p>Ein Konto bei Autodesk Account mit einem FormIt Pro-Cloud-Abonnement ist erforderlich, um FormIt Pro unter Windows auszuführen. FormIt Pro ist als Teil der <a href="https://www.autodesk.com/collections/architecture-engineering-construction/overview"><strong>Autodesk AEC Collection</strong></a> verfügbar.</p> |

## Offline-Zugriff

Beim ersten Ausführen von FormIt for Windows müssen Sie mit dem Internet verbunden sein, damit Ihre Lizenz überprüft werden kann. Nach der ersten Anmeldung können Sie die App 30 Tage lang offline verwenden. Danach müssen Sie online gehen, um Ihre Lizenz erneut zu validieren.

Bei der Offline-Verwendung von FormIt for Windows sind einige Funktionen eingeschränkt:

* Das Werkzeug Standort festlegen funktioniert nicht, da eine Internetverbindung zum Abrufen von Satelliten- und Geländedaten aus Bing Maps erforderlich ist.
   * Alle vorhandenen Satelliten- und Geländedaten aus einer früheren Online-Sitzung, die sich bereits im Modell befinden, bleiben jedoch erhalten.
* Plugins, einschließlich des Plugin Managers, werden nicht geladen, da sie bei jedem Anwendungsstart den neuesten Code von GitHub erhalten.
   * Schnelle Zwischenlösung: Wenn Sie alle Plugins laden, während Sie online sind, und die FormIt-Sitzung beibehalten, wenn Sie offline gehen, bleiben die zuvor geladenen Plugins erhalten und funktionieren ordnungsgemäß.
* Beispielmaterialien werden nicht geladen, da sie von einem in der Cloud gehosteten Server stammen.
   * Schnelle Zwischenlösung: Navigieren Sie zu den Ordnern der Beispielmaterialkategorie, während Sie mit dem Internet verbunden sind. Die Ordner werden heruntergeladen und auf Ihrem Computer gespeichert. Sie können später offline darauf zugreifen.
* Sie können nicht in Autodesk Docs speichern oder Dateien daraus öffnen, auch nicht aus der Inhaltsbibliothek.

## Empfohlene Windows-DPI-Einstellungen

FormIt for Windows funktioniert am besten, wenn der Bildschirm in Windows auf eine DPI-Skalierung von 125 % oder weniger eingestellt ist.

Sie können dies in Windows 10 wie folgt ändern:

* Suchen Sie im Startmenü nach Anzeige, und wählen Sie Anzeigeeinstellungen ändern.
* Wählen Sie das Rechteck für den Bildschirm aus, den Sie in FormIt verwenden werden.
* Öffnen Sie im Abschnitt Skalierung und Anordnung die Dropdown-Liste Größe von Text, Apps und anderen Elementen ändern, und wählen Sie einen Wert von 125 % oder weniger aus.

## Troubleshooting (Fehlerbehebung)

### Windows 10 Pro N-Systemfehler

Wenn Sie FormIt unter Windows 10 Pro N Version 1909 oder höher ausführen, wird möglicherweise die folgende Fehlermeldung angezeigt:

![FormIt.exe System Error on Windows 10](<../.gitbook/assets/windows 10 error message.png>)

Dies liegt an einem bekannten Problem mit bestimmten Versionen von Windows 10 Pro N. Um diesen Fehler zu vermeiden, laden Sie hier das Media Feature Pack für Ihre Version von Windows 10 herunter: [Liste der Media Feature Packs für Windows N-Editionen](https://support.microsoft.com/de-de/topic/liste-der-media-feature-packs-für-windows-n-editionen-c1c6fffa-d052-8338-7a79-a4bb980a700a).

### Anmelden nicht möglich

Beim Versuch, sich in FormIt bei Ihrem Konto anzumelden, reagiert das Anmeldedialogfeld möglicherweise nicht mehr, sodass Sie nicht fortfahren können. Wenn dies der Fall ist, müssen Sie möglicherweise die Sperrung von \*.autodesk.com in Ihrer Netzwerk-Firewall aufheben. Wenden Sie sich an Ihre IT-Abteilung, um Unterstützung zu erhalten.
