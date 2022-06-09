---
description: >-
  Start a BIM workflow by evaluating the performance of elements from the
  beginning of the design process.
---

# Solar- und Energieanalyse

![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## Energieanalyse in FormIt

Analysieren Sie Ihr Gebäudemodell bereits in einem frühen Stadium des Entwurfsprozesses hinsichtlich der Energieeffizienz.

[Insight-Projekte anzeigen](https://gbs.autodesk.com/OneEnergy/Insight)

## Energieanalyse mit Insight

Mit einem **FormIt Pro**-Abonnement im Rahmen der [AEC Collection](https://www.autodesk.de/collections/architecture-engineering-construction/overview) können Sie auf die Energieanalyse in **Insight** zugreifen:

* Analysieren Sie Modelle in frühen Entwurfsstadien mit der Analyse-Engine von Green Building Studio.
* Zeigen Sie eine Dashboard-Ansicht mit Analyseergebnissen an, um die Optionen für Ihren Entwurf zu vergleichen.
* Passen Sie die Widgets für einzelne Faktoren in der Energieanalyse, z. B. Wand-Fenster-Verhältnis, Ausrichtung des Gebäudes und mehr, an.
* Fassen Sie die energetische Auswirkung des Gebäudes zu einem einzelnen, als Endergebnis für die Kosten pro Fläche berechneten Zahlenwert zusammen.
* Speichern Sie die Ergebnisse der Energieanalyse zur späteren Prüfung mit Kunden und anderen Beteiligten.

## Neue Funktionen in FormIt und Insight <a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Verbesserungen bei der Zuverlässigkeit von Insight** <a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) prüft Ihr Modell jetzt auf häufige Modellprobleme, bevor Insight ausgeführt wird, und behebt häufige Insight-Fehler für eine zuverlässigere Benutzererfahrung.
* In FormIt 2021 wurden außerdem generell die Zuverlässigkeit der FormIt- und Insight-Verbindung verbessert, viele bekannte Fehler behoben und die Ausführungserfolgsrate gesteigert.

## Erste Schritte <a href="#insight-getting-started" id="insight-getting-started"></a>

### **Funktionsweise** <a href="#how-it-works" id="how-it-works"></a>

* Die Energieanalyse mit Insight lädt Ihre FormIt-Modelldaten hoch und führt mehrere Hundert Analysen in der Cloud durch, um verschiedene Energiewerte zu bestimmen.
* Die Energieanalyse verwendet Revit zur Analyse Ihres Modells. Wie beim Senden von FormIt-Daten an Revit müssen Sie daher [sicherstellen, dass Ihr FormIt-Modell wasserdicht und bündig ist](https://formit.autodesk.com/blog/post/repairing-solid-models).

### **Vorbereiten Ihres FormIt-Modells** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Insight verwendet jede sichtbare Geometrie in Ihrer FormIt-Skizze.
   * Stellen Sie sicher, dass die Gebäudehülle, die Sie analysieren möchten, die einzige sichtbare Geometrie ist.
   * Legen Sie unterstützende Geometrie wie Umgebung, Möbel und Grundstückselemente auf einem separaten [Layer](../tool-library/layers.md) ab, und deaktivieren Sie den Layer.
* Insight funktioniert am besten mit einem einfachen, massiven Gebäudemodell.
   * Stellen Sie sicher, dass der Gebäudekörper [massiv und wasserdicht](https://formit.autodesk.com/blog/post/repairing-solid-models) ist.
   * Wenn Ihr Gebäudeentwurf bereits Öffnungen für Fenster und Türen aufweist, ist es am besten, einen neuen Körper ohne Öffnungen speziell für die Energieanalyse zu erstellen und die detailliertere Version mithilfe von Layern auszublenden.
* Auf den einfachen Gebäudekörper müssen [Ebenen](../tool-library/levels-and-area.md) angewendet werden.
* Für das FormIt-Modell muss ein [Standort](../tool-library/setting-location.md) festgelegt sein.

![](../.gitbook/assets/insight.png)

### **Starten der Energieanalyse** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* Suchen Sie im Werkzeugkasten nach der Schaltfläche Energieanalyse.

![](../.gitbook/assets/generate\_insight.png)

* Klicken Sie auf Insight generieren, um den Prozess zu starten.
* Dadurch werden die sichtbaren Modelldaten hochgeladen und mehrere Hundert Simulationen in der Cloud ausgeführt.
* Wenn der Vorgang abgeschlossen ist, wird eine Meldung oben auf dem Bildschirm angezeigt, und das Menü wird aktualisiert, um anzugeben, dass ein neuer Insight angezeigt werden kann.
   * Klicken Sie auf Insight anzeigen, um die Analyse in Ihrem Webbrowser anzuzeigen.
   * Sie finden alle Ihre Einblicke auch unter [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight).

## Troubleshooting (Fehlerbehebung) <a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **Häufige Fehler** <a href="#common-errors" id="common-errors"></a>

* Insight-Projekt konnte nicht erstellt werden. Versuchen Sie es später erneut.
   * Melden Sie sich beim [Green Building Studio-Dashboard](https://gbs.autodesk.com/GBS/Project) an, und starten Sie FormIt neu.
      * Wenn Sie sich nicht anmelden können oder Zugriff verweigert angezeigt wird, müssen Sie möglicherweise [ein Abonnement für Green Building Studio erwerben](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/DEU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html).
   * Stellen Sie sicher, dass das Modell [massiv und wasserdicht](https://formit.autodesk.com/blog/post/repairing-solid-models) ist.
   * Prüfen Sie im [Autodesk Health Dashboard](https://health.autodesk.com/), ob Probleme mit den FormIt-Diensten vorliegen.
* Um zu erfahren, ob Green Building Studio die Energieanalyse-Durchläufe für dieses Projekt erfolgreich ausgeführt hat, sehen Sie im [Green Building Studio-Dashboard](https://gbs.autodesk.com/GBS/Project) nach.
   * Das neueste Projekt sollte oben in der Liste angezeigt werden und 248 Durchläufe umfassen.
   * Wenn 0 Durchläufe angezeigt werden, [informieren Sie uns über die FormIt-Foren](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=de). Wir können Ihnen dann weitere Unterstützung bei der Fehlerbehebung bieten.

### **Detaillierte Protokolle** <a href="#detailed-logs" id="detailed-logs"></a>

* FormIt Web bietet zusätzliche Informationen, wenn die Energieanalyse fehlschlägt:
   * Wechseln Sie zu [FormIt Web](https://formit.autodesk.com/app).
   * Öffnen Sie das Modell, bei dem Probleme bei der Energieanalyse aufgetreten sind.
   * Führen Sie die Energieanalyse aus.
   * Öffnen Sie die Entwicklerwerkzeuge (drücken Sie F12 in Google Chrome oder Firefox).
   * Prüfen Sie die Registerkarte Konsole.
   * Kopieren Sie die Fehler, oder erstellen Sie einen Screenshot, und [melden Sie sie über die FormIt-Foren](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=de).

## Sonnenstudie

Mit einem **FormIt Pro**-Abonnement im Rahmen der [AEC Collection](https://www.autodesk.de/collections/architecture-engineering-construction/overview) können Sie die Einwirkung der Sonne auf das Gebäude visuell darstellen:

* Geben Sie die Flächen an, die im Hinblick auf die Sonneneinwirkung analysiert werden sollen.
* Die Ergebnisse werden innerhalb von Sekunden im Arbeitsbereich der App angezeigt.
* Setzen Sie den Cursor auf einen Eingabepunkt, um die berechneten Werte für die Sonneneinwirkung an diesem Punkt anzuzeigen.
* Sie können wählen, ob die Ergebnisse als Monatswerte in einer Studie für die Verglasung oder als Jahreswerte für Machbarkeitsstudien zu Solarzellen angezeigt werden sollen.

Erfahren Sie mehr über [Solaranalysen](../tool-library/solar-analysis.md) in FormIt Pro.
