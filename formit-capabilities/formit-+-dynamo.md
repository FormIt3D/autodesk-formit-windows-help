---
description: Computational Design in FormIt
---

# FormIt und Dynamo

![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

FormIt for Windows verfügt über integrierte Dynamo-Funktionen, sodass Sie von beeindruckenden Arbeitsabläufen für computergestützte Entwürfe profitieren können.

## Neue Funktionen in FormIt und Dynamo

### **Datendiagramme, Senden von Ebenen an Excel und Facettierungssteuerung**

[FormIt 2023](https://formit.autodesk.com/blog/post/introducing-formit-2023/) ermöglicht die Ausführung von Dynamo-Diagrammen [ohne SendToFormIt-Block](formit-+-dynamo.md#graph-types), bietet die Möglichkeit zum [Senden von FormIt-Ebenen an Excel](formit-+-dynamo.md#send-formit-levels-to-excel) und umfasst Steuermöglichkeiten für [Kurven- und Oberflächenfacettierung über neue FormItGroupOptions-Blöcke](../tool-library/curve-+-surface-faceting.md).

### **Bemaßungseingaben und Vorschau der JS-API**

[FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1) bietet die Möglichkeit, [vertraute FormIt-Bemaßungen als Eingaben zu verwenden](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes), führt [Optionen auf Objektebene](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes) ein und bietet eine Vorschau für den Zugriff auf die [JavaScript-API](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes). Sie finden die Anwendung [hier](https://formit.autodesk.com/page/download).

### **Mehrere SendToFormIt-Blöcke**

[FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3) bietet die Möglichkeit, [mehrere SendToFormIt-Blöcke und verschachtelte Dynamo-Diagramme](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups) zu verwenden.

### **SelectFromFormIt-Block**

In [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) wurde der [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes)-Block hinzugefügt, und es werden immer verbundene Sitzungen, die Bearbeitung mehrerer Instanzen und vieles mehr ermöglicht.

## Erste Schritte

Erfahren Sie mehr über die Benutzeroberfläche, und verknüpfen Sie Ihre Dynamo-Verzeichnisse mit FormIt.

### **Erstmaliges Setup**

Verwenden Sie FormIt und Dynamo zum ersten Mal? Möglicherweise müssen Sie zuerst [Ihr System konfigurieren](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes), um den 3D-Ansichtsbereich in Dynamo anzuzeigen.

### **Gruppe Dynamo**

Über die Gruppe Dynamo können Sie Dynamo starten, Dynamo-Gruppen platzieren und Dynamo-Diagramme bearbeiten:

![Dynamo panel](<../.gitbook/assets/dynamo\_dynamopanel (1).png>)

### **Hinzufügen und Verwalten lokaler Dynamo-Verzeichnisse**

* Die Gruppe Dynamo funktioniert wie die [Inhaltsbibliothek](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library), sodass Sie lokale Verzeichnisse, die Dynamo-Dateien enthalten, verknüpfen und verwalten können.
* Klicken Sie in der Gruppe Dynamo auf die Schaltfläche Dynamo-Verzeichnis verknüpfen, und klicken Sie dann im Dialogfeld Voreinstellungen erneut auf (+), um ein Verzeichnis für die Verknüpfung mit FormIt auszuwählen: <img src="../.gitbook/assets/dynamo_selectdirectory.png" alt="" data-size="line">
* Wechseln Sie mithilfe der Dropdown-Liste zwischen verknüpften Verzeichnissen:

![](../.gitbook/assets/dynamo\_dropdown.png)

* Sie können DYN-Dateien und -Unterordner nur über die Gruppe Dynamo anzeigen.
* Verwenden Sie die Filterleiste, um Dynamo-Dateien und -Unterordner herauszufiltern, um schnell die gewünschten Dateien zu finden:

![](../.gitbook/assets/dynamo\_filter.png)

## Verschiedene Möglichkeiten für Dynamo

Erstellen und bearbeiten Sie Diagramme in Dynamo, oder testen Sie Parameter in FormIt, ohne das Diagramm jemals anzuzeigen. Oder führen Sie beide Aktionen gleichzeitig aus!

### **Diagrammarten**

FormIt unterstützt drei Arten von Dynamo-Diagrammen:

* Datendiagramm: Datendiagramme haben keine _SendToFormIt_-Blöcke und werden verwendet, um Daten über FormIt anzuzeigen oder durch FormIt durchzuleiten. Sie können Datendiagramme beispielsweise verwenden, um Daten an Excel zu senden oder nicht geometrische Daten zu berechnen und diese in einem Beobachtungsblock anzuzeigen.
* Geometriediagramm: Diese Diagramme erzeugen Geometrie sofort und müssen im Ansichtsbereich platziert werden, damit die Parameter angezeigt werden können. Nach dem Klicken auf die Miniaturansicht wird die Geometrie am Cursor angezeigt, sodass sie in der 3D-Szene platziert werden kann. Für dieses Diagramm muss mindestens ein _SendToFormIt_-Block am Ende des Diagramms vorhanden sein, der Geometrie erhält.
* Auswahldiagramm: Für diese Diagramme sind vor der Ausführung FormIt-Auswahlen erforderlich. In der oberen linken Ecke von FormIt wird eine Eingabeaufforderung angezeigt, in der Sie angeben können, was ausgewählt werden soll. Nach der Auswahl wird das Diagramm ausgeführt und die Geometrie relativ zur Auswahl generiert. Für dieses Diagramm muss mindestens ein _SendToFormIt_-Block am Ende des Diagramms vorhanden sein, der Geometrie erhält.

![](../.gitbook/assets/dynamo-graph-types.png)

### **Geometriediagramm: Platzieren von Dynamo-Gruppen in FormIt**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* Klicken Sie in der Gruppe Dynamo auf die Miniaturansicht des Dynamo-Diagramms, das Sie ausführen möchten.
   * Sie können die integrierten Beispiele verwenden oder [eine Bibliothek](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) Ihrer eigenen Dynamo-Dateien verknüpfen.
* Durch das Platzieren der Geometrie in FormIt wird eine Kopie des Dynamo-Diagramms in die FormIt-Datei eingebettet.
   * Um Geometrie zu generieren, muss den Ausgabegeometrie-Blöcken im Diagramm ein [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes)-Block zugeordnet werden.
* Die Geometrie aus dem SendToFormIt-Block wird mit dem Cursor verbunden, sodass sie platziert werden kann.
   * Wenn im Diagramm [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes)-Blöcke mit Ist Eingabe markiert sind, fordert FormIt zunächst eine Auswahl (alle Auswahlblöcke in vertikaler Reihenfolge) und generiert dann die Geometrie an der richtigen Position relativ zur Auswahl.
* Eine Kopie der ursprünglichen Dynamo-Datei wird jetzt in die FormIt-Gruppe eingebettet und ist unabhängig vom Quelldiagramm.
* Nach der Platzierung wird die Gruppe Eigenschaften automatisch aktualisiert, sodass die verfügbaren Parameter angezeigt werden.

### **Geometriediagramm: Parameter bearbeiten**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* Nachdem Sie eine Dynamo-Gruppe platziert haben, wählen Sie sie aus und wechseln zur Gruppe Eigenschaften. Sie können auch einfach auf die Gruppe doppelklicken, um automatisch zu den Eigenschaften zu wechseln.
   * Alle Eingabeblöcke, die in Dynamo mit Ist Eingabe gekennzeichnet sind, werden hier aufgeführt.
   * [**SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes)-Eingabeblöcke werden oben als Schaltflächen angezeigt und können verwendet werden, um die Auswahl zu aktualisieren, die zum Steuern des Diagramms verwendet wird.
   * FormIt unterstützt die folgenden Eingabeblöcke: Number Sliders, Integer Sliders, Boolesche Umschalter und Nummern-/Zeichenfolgen-Felder.
* Ändern Sie die Eingaben in FormIt, und klicken Sie dann auf Ausführen. Die Schaltfläche Ausführen wird blau, um anzuzeigen, dass Parameter geändert wurden, und das Diagramm muss ausgeführt werden.
   * Dynamo wird im Hintergrund ausgeführt, um die Änderungen zu verarbeiten und aktualisierte Geometrie in FormIt zurückzugeben.
   * In FormIt 2022 und höher wird durch die erste Ausführung über die Gruppe Eigenschaften eine dedizierte Dynamo-Instanz erstellt, wodurch nachfolgende Bearbeitungen wesentlich schneller erfolgen können.
   * Sie können FormIt weiterhin verwenden, während Dynamo ausgeführt wird.&#x20;
* Beachten Sie, dass die gesamte Geometrie innerhalb der einzelnen SendToFormIt-Gruppen gelöscht und ersetzt wird, wenn das Dynamo-Diagramm ausgeführt wird.

### Datendiagramm: Senden von FormIt-Ebenen an Excel

In FormIt 2023 und höher können Sie mit Dynamo FormIt-Ebenen an Excel senden:&#x20;

* Laden Sie das [Dynamo-Beispieldiagramm hier herunter](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn).
* Verweisen Sie die Dynamo-Palette auf das lokale Verzeichnis, in dem das Dynamo-Diagramm gespeichert wurde.
* Klicken Sie mit der rechten Maustaste auf die Miniaturansicht, und wählen Sie _Eingebettetes Diagramm bearbeiten_
* Erstellen Sie an einer Stelle eine leere Excel-Tabelle.
* Bearbeiten Sie das Feld für den Speicherort der Tabelle, um den Pfad zur Excel-Tabelle zu verwenden.
* Bearbeiten Sie alle anderen gewünschten Felder, z. B. Planname.
* Schließen Sie Dynamo, und speichern Sie das Diagramm.

Jetzt können Sie einfach auf die Beispieldatei in der Palette klicken, und sie wird in FormIt ausgeführt, ohne dass Geometrie erstellt werden muss.&#x20;

Die Dynamo-Eingaben werden in der Dynamo-Palette angezeigt, Excel wird geöffnet, und die Ergebnisse aus dem Diagramm werden angezeigt.&#x20;

Wenn Sie Änderungen am Modell vornehmen, können Sie erneut auf die Miniaturansicht des Diagramms oder auf die Schaltfläche _Ausführen_ klicken, um die Tabelle mit den Ebenendaten aus der neuesten Version der FormIt-Skizze zu aktualisieren.

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### Starten eines neuen Dynamo-Fensters

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* In FormIt 2021 und höher wird durch Klicken auf die Schaltfläche Dynamo starten in der Gruppe Dynamo automatisch eine verbundene Sitzung mit FormIt gestartet.
   * Dadurch wird eine Diagrammvorlage in Dynamo geöffnet, und die Vorlagengeometrie wird automatisch in FormIt generiert.
   * Die resultierende Geometrie wird in einer neuen Gruppe am Ursprung des aktuellen Gruppenbearbeitungskontexts angezeigt. Es ist empfehlenswert, sich im gewünschten Gruppenkontext zu befinden, bevor Sie Dynamo starten.&#x20;
   * Die Vorlage enthält sowohl FormIt-Blöcke als auch einige Beispielgeometrien. Durch Anpassen der Schieberegler wird die Größe des Würfels in beiden Anwendungen angepasst.
   * Hier können Sie verschiedene Dynamo-Diagramme öffnen oder mithilfe dieser grundlegenden Komponenten in der Vorlage neue Elemente erstellen und mit Speichern unter in Dynamo an einem neuen Speicherort speichern.

### **Bearbeiten eingebetteter und Quelldiagramme**

Vorhandene Dynamo-Diagramme können auf zwei verschiedene Arten bearbeitet werden: durch Bearbeiten von eingebetteten Diagrammen, die bereits in FormIt platziert wurden, oder durch Bearbeiten des Quelldiagramms, das auf Ihrem Computer gespeichert ist.

### **Eingebettete Diagramme**

Nach dem Platzieren eines Dynamo-Objekts in FormIt wird das zugrunde liegende Diagramm kopiert und in die aktuelle FormIt-Datei eingebettet. Die Bearbeitung in Dynamo erfolgt über die Schaltfläche **Eingebettetes Diagramm bearbeiten**.

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* Wählen Sie die Dynamo-Gruppe aus, und wechseln Sie zur Gruppe Eigenschaften. Sie können auch einfach auf die Gruppe doppelklicken, um automatisch zu den Eigenschaften zu wechseln.
* Klicken Sie auf die Schaltfläche **Eingebettetes Diagramm bearbeiten**.
* In Dynamo sehen Sie, dass der Dateiname oben jetzt "(FormIt)" enthält. Dies bedeutet, dass Sie ein in diese FormIt-Datei eingebettetes Diagramm bearbeiten, nicht das Quelldiagramm.
* Stellen Sie sicher, dass mindestens ein [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes)-Block mit der Geometrie verbunden ist, die Sie an FormIt senden möchten.
* FormIt zeigt Aktualisierungen der Geometrie in Echtzeit an, während Sie das Diagramm anpassen.
* Wenn Sie die Änderungen nicht in Dynamo speichern, wird FormIt auf die zuletzt gespeicherte Version des Dynamo-Diagramms zurückgesetzt.
* Beachten Sie, dass die gesamte Geometrie innerhalb der einzelnen SendToFormIt-Gruppen gelöscht und ersetzt wird, wenn das Dynamo-Diagramm ausgeführt wird.

### **Quelldiagramme**

Quelldiagramme werden in der Gruppe Dynamo angezeigt, nachdem [lokale Verzeichnisse verknüpft wurden](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started). Diese Diagramme werden auf Ihrem Computer gespeichert und können in Dynamo bearbeitet werden, indem Sie auf die Schaltfläche Quelldiagramm bearbeiten klicken.

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* [Verknüpfen Sie ein Verzeichnis](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) mit Dynamo-Dateien mit der Gruppe Dynamo, und navigieren Sie dann zu diesem Speicherort in der Gruppe.&#x20;
* Klicken Sie mit der rechten Maustaste auf die Miniaturansicht des Dynamo-Diagramms, das Sie bearbeiten möchten (oder klicken Sie auf den Pfeil), und wählen Sie die Schaltfläche **Quelldiagramm bearbeiten**.
* Dynamo wird mit geöffnetem angeforderten Diagramm gestartet, und in FormIt wird die Geometrie der endgültigen Ausgabe des Diagramms angezeigt.
   * Bei Diagrammen, die einen oder mehrere [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes)-Blöcke als Eingabe verwenden, wird die resultierende Geometrie möglicherweise erst angezeigt, wenn die SelectFromFormIt-Blöcke mit Auswahlen gefüllt sind.
* Die resultierende Geometrie wird in einer neuen Gruppe am Ursprung des aktuellen Gruppenbearbeitungskontexts angezeigt.
   * Es ist empfehlenswert, sich im gewünschten Gruppenkontext zu befinden, bevor Sie auf Quelldiagramm bearbeiten klicken.
* Wenn Sie mit der Bearbeitung fertig sind, speichern und schließen Sie Dynamo. In FormIt wurde das Quelldiagramm kopiert und in die FormIt-Datei eingebettet.
   * Wenn Sie weitere Änderungen am **Quelldiagramm** vornehmen müssen, löschen Sie die eingebettete Kopie und führen die folgenden Schritte erneut durch.

### **Steuern der Kurven- und Oberflächenfacettierung**

*   Ab FormIt 2023 können Sie das Facettieren von Kurven und Flächen, die SendToFormIt-Blöcken zugeordnet sind, mithilfe der FormItGroupOptions-Blöcke SetCurveFacetingCount und SetSurfaceFacetingCount steuern.

    <img src="../.gitbook/assets/dynamo-formitgroupoptions-faceting-nodes.png" alt="" data-size="original">
* Diese Blöcke überschreiben die globalen Einstellungen für die Kurven- und Oberflächenfacettierung, die unter Bearbeiten -> Voreinstellungen -> Einheiten und Genauigkeit definiert sind.
* Dies ist sehr nützlich, wenn Ihr Dynamo-Diagramm gekrümmte Objekte mit bestimmten Facettierungswerten erstellen muss, wodurch die Notwendigkeit, die globale Einstellung für jedes in der aktuellen Sitzung ausgeführte Dynamo-Diagramm zu ändern, verringert wird.

![](../.gitbook/assets/dynamo-formitgroupoptions-faceting.gif)

* Sie können Facettierungseinstellungen auch global unter Bearbeiten -> Voreinstellungen -> Einheiten und Genauigkeit festlegen.
* Nachdem Sie die Facettierungsqualität in den Voreinstellungen angepasst haben, führen Sie das Diagramm erneut aus, um die neuen globalen Facettierungseinstellungen zu verwenden.

![](../.gitbook/assets/dynamo\_controlcurve.gif)

[Erfahren Sie mehr über die Einstellungen für Kurven- und Oberflächenfacettierung in FormIt.](https://windows.help.formit.autodesk.com/v/german/tool-library/curve-+-surface-faceting)

## Verwenden von FormIt-Gruppen mit Dynamo

Nutzen Sie die leistungsstarken FormIt-Gruppen für eine bessere Organisation der Dynamo-Geometrie und beeindruckende Arbeitsabläufe.

### **Gruppen und der SelectFromFormIt-Block**

* Wenn Sie Geometrie für einen [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes)-Block auswählen, ist es hilfreich, die Geometrie in einer FormIt-Gruppe zu speichern und stattdessen die Gruppe auszuwählen.
   * Dadurch haben Sie die Möglichkeit, den Inhalt der ausgewählten FormIt-Gruppe zu ändern und das Diagramm, das die Gruppe referenziert, einfach erneut auszuführen, um das aktualisierte Ergebnis anzuzeigen.
* Wenn Sie nicht gruppierte Geometrie auswählen, kann es bei Änderungen an dieser Geometrie vorkommen, dass FormIt Sie auffordert, die Geometrie bei der nächsten Ausführung des Diagramms erneut auszuwählen.

### **Erstellen von Geometrie in Gruppen**

* Wenn ein Dynamo-Diagramm in FormIt ausgeführt wird, sind die geometrischen Ergebnisse in einer FormIt-Gruppe enthalten.
* Jeder [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes)-Block im Diagramm erstellt eine Untergruppe, die die Geometrie aus dem Block-Eingabeanschluss enthält.
* Nach dem Erstellen eines Dynamo-Objekts in FormIt werden das gesamte Diagramm und seine Parameter als Kopie in die FormIt-Datei eingebettet.
* Wenn das Diagramm ausgeführt wird, wird die Geometrie in jeder Untergruppe gelöscht und neu generiert.
   * Gehen Sie beim Ändern von Geometrie oder beim Malen von Flächen in Untergruppen vorsichtig vor, da diese Änderungen beim nächsten Ausführen des Dynamo-Diagramms verloren gehen.
   * Wenn Sie jedoch mit FormIt-Materialien Untergruppen (keine enthaltene Geometrie) malen, bleiben diese Materialien zwischen den Durchläufen erhalten. Siehe unten.

### **Arbeiten mit Gruppen und Materialien**

* Wenn Sie mehrere **SendToFormIt**-Blöcke verwenden, können Sie die Blöcke nach Material organisieren, sodass Sie verschiedene FormIt-Untergruppen mit unterschiedlichen Materialien malen können.
* In diesem Beispiel wird ein ganzes Gebäude aus einfachen Ebenen in FormIt generiert. Jede Gebäudekomponente, die eindeutige Materialien erfordert, erhält ihren eigenen **SendToFormIt**-Block:

![](<../.gitbook/assets/dynamo\_sendtoformit (1).png>)

* Nach dem Anwenden von Materialien auf die einzelnen Untergruppen bleiben die Materialien zwischen Dynamo-Ausführungen erhalten:

![](../.gitbook/assets/dynamo\_materialsgif.gif)

### **Verschachteln von Dynamo-Gruppen**

* Sie können den **SelectFromFormIt**-Block verwenden, um die Ergebnisse der Untergruppe aus einem Dynamo-Diagramm auszuwählen und die Ergebnisse eines anderen Diagramms zu steuern.&#x20;
* Basierend auf dem obigen Beispiel wird die Verglasungsausgabe des Gebäude-Generator-Diagramms als Auswahlgeometrie für das integrierte Beispiel Storefront Curtainwall verwendet:

![](../.gitbook/assets/dynamo\_storefront\_curtainwallgif.gif)

* Wenn sich die Form des Gebäudes ändert, können Sie einfach die Pfostensystemgruppe auswählen und in der Gruppe Eigenschaften auf Ausführen klicken.
   * Obwohl sich der Inhalt der Verglasungsgruppe geändert hat, wurde die Gruppe selbst nicht geändert, sodass Sie die Verglasung nicht erneut auswählen müssen, wenn Sie das Diagramm erneut ausführen.
* Das oben genannte Modell steht in FormIt 2022 und höher als Roof Planes Building im Unterordner **Building Masses** unter **Dynamo Samples** zur Verfügung.
* In Kombination mit den umfangreichen Funktionen von FormIt können Sie mit Dynamo einen vollständig parametrischen Entwurf – komplett mit Materialien und verschachtelter Logik – im umfangreichen Kontext eines leistungsstarken Konzeptmodellierers erstellen und testen:

![](../.gitbook/assets/dynamo\_parametricdesigngif.gif)

### **Standardmäßiges Gruppenverhalten in FormIt gilt weiterhin**

* Abgesehen von den oben beschriebenen Vorgehensweisen gelten für Dynamo-Gruppen in FormIt dieselben Regeln wie für andere Gruppen:
   * Durch das Platzieren eines neuen Dynamo-Objekts aus der Gruppe Dynamo wird eine eindeutige Gruppe erstellt. Dies wirkt sich nicht auf bereits in der Skizze platzierte Instanzen desselben Objekts aus.
   * Durch Kopieren und Einfügen von Dynamo-Gruppen bleiben diese identisch. Änderungen, die Sie am Dynamo-Diagramm einer Kopie vornehmen, aktualisieren auch die Geometrie in den identischen Instanzen, sofern sie nicht als eindeutig definiert werden.
   * Sie können Dynamo-Gruppen mithilfe des Tastaturkurzbefehls MU oder über das Kontextmenü eindeutig machen:

![](<../.gitbook/assets/dynamo\_makeunique (1).png>)

## Grundlegende FormIt-Blöcke

Die leistungsfähigsten Blöcke zum Senden von Daten zwischen FormIt und Dynamo.

### **SendToFormIt-Block**

* Um Dynamo-Objekte in FormIt zu generieren, ordnen Sie die Ausgaben des gewünschten geometrischen Blocks der _Geometrie_-Eingabe von mindestens einem SendToFormIt-Block zu:

![](<../.gitbook/assets/dynamo\_sendtoformitnode (1).png>)

* FormItGroupOptions ist ein neuer (optionaler) Anschluss in FormIt 2022, der im Abschnitt **FormItGroupOptions-Blöcke** weiter unten beschrieben wird.
* In FormIt 2021.3 und höher können Sie mehrere SendToFormIt-Blöcke verwenden, um Ihre Dynamo-Ergebnisse in aufgeräumten FormIt-Gruppen und -Untergruppen zu organisieren.
* [Erfahren Sie, wie Dynamo mit FormIt-Gruppen verwendet werden kann](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

![](<../.gitbook/assets/dynamo\_sendtoformitnodes (1).png>)

* Der SendToFormIt-Block berücksichtigt das Flag Ist Ausgabe, das vorgabemäßig aktiviert ist. Sie können mit der rechten Maustaste auf den Block klicken, um Folgendes zu überprüfen:

![](<../.gitbook/assets/dynamo\_isoutput (1).png>)

* Wenn diese Option aktiviert ist, wird die Geometrie, die diesem SendToFormIt-Block zugeordnet ist, in FormIt in einer Untergruppe angezeigt.
* Wenn diese Option deaktiviert ist, wird keine Geometrie an FormIt gesendet, und die entsprechende Untergruppe (falls vorhanden) wird gelöscht.

### **SelectFromFormIt-Block**

* In FormIt 2021 und höher können Sie Geometrie aus FormIt auswählen, um sie als Eingabe in Dynamo-Diagrammen zu verwenden:

![](<../.gitbook/assets/dynamo\_selectfromformitnode (1).png>)

* Der Name des SelectFromFormIt-Blocks wird für Eingabeaufforderungen in FormIt verwendet. Sie sollten diesen daher so benennen, dass er beschreibt, welche Art von FormIt-Geometrie ausgewählt werden soll:

![](<../.gitbook/assets/dynamo\_selectobjectstoarraynode (1).png>)

* Wenn Sie im Dynamo-Diagramm-Editor oder in der Gruppe Eigenschaften auf die Schaltfläche Aus FormIt auswählen klicken, startet FormIt einen Auswahlassistenten, der Sie durch die Auswahl der Geometrie führt:

![](../.gitbook/assets/dynamo\_selectobjectstoarrayUI.png)

* Der SelectFromFormIt-Block berücksichtigt das Flag Ist Eingabe, das vorgabemäßig aktiviert ist. Diese Option muss aktiviert werden, damit die Auswahl in FormIt funktioniert. Klicken Sie mit der rechten Maustaste auf den Block, um ihn zu überprüfen.

![](<../.gitbook/assets/dynamo\_isinput (1).png>)

* Wenn Ist Eingabe aktiviert ist:
   * Die Miniaturansicht der Gruppe Dynamo im Diagramm gibt an, dass eine Auswahl erforderlich ist:

![](../.gitbook/assets/dynamo\_patharray.png)

* Beim Ausführen des Diagramms führt Sie der FormIt-Auswahlassistent durch die Einstellungen für jeden SelectFromFormIt-Block, beginnend am oberen Rand des Diagramms.
* Nach dem erstmaligen Generieren wird in der FormIt-Gruppe Eigenschaften eine Schaltfläche für jeden SelectFromFormIt-Block angezeigt.

![](../.gitbook/assets/dynamo\_selectarraypath.png)

* Wenn Sie auf diese klicken, wird der Auswahlassistent gestartet, sodass Sie die Auswahl ändern können, die zum Erstellen der endgültigen Geometrie verwendet wurde. Das Diagramm wird nach der Neuauswahl automatisch erneut ausgeführt.

### **Tipps, Tricks und Anmerkungen**

* Geben Sie dem SelectFromFormIt-Block einen Namen, um anzugeben, welcher Geometrietyp erwartet wird. Beispiel: Select Site Boundary (Edges)
   * Sie können jeden Typ von FormIt-Geometrie auswählen, es ist jedoch oft am besten, die Auswahl in eine FormIt-Gruppe aufzunehmen und [diese anstelle der unbearbeiteten Geometrie auszuwählen](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).
* Wenn Sie die Ergebnisse eines auswahlbasierten Dynamo-Diagramms verschieben müssen, ist es am besten, zuerst die Auswahlgeometrie zu verschieben und dann das Diagramm erneut auszuführen. Dabei wird die aktualisierte Auswahlgeometrie ausgewählt und die Position entsprechend geändert.&#x20;
   * Sie können die Dynamo-Ergebnisse **und** die Auswahl auch gruppieren und dann die Gruppe verschieben, die sie enthält.
* Beim Senden von FormIt-Geometrie an Dynamo gehen alle Attribute, Materialien oder verschachtelten Gruppen verloren, wenn Sie die Geometrie wieder in FormIt zurückgeben.
* Wenn Sie ein auswahlbasiertes Diagramm in Dynamo bearbeiten und sich die ausgewählte Geometrie in FormIt ändert, müssen Sie die Geometrie erneut auswählen, indem Sie auf dem SelectFromFormIt-Block auf die Schaltfläche Aus FormIt auswählen klicken.&#x20;
* Bei der Auswahl in FormIt wird der aktive [Auswahlfilter](https://windows.help.formit.autodesk.com/v/german/tool-library/select-edge-face-or-object#auswahlfilterung) angewendet. Wenn Sie beispielsweise FormIt-Scheitelpunkte auswählen möchten, müssen Sie diese Option im Auswahlfilter aktivieren.

![](../.gitbook/assets/dynamo\_filterselection.png)

## Andere Eingabeblöcke

Eine Vielzahl von Eingabeoptionen für die einfache Anpassung von Dynamo-Diagrammen in FormIt.

### **FormItLengthString-Block**

In FormIt 2022.1.0 oder höher können Sie den **FormItLengthString**-Block verwenden, um Bemaßungen in jedem unterstützten FormIt-Einheitentyp (Fuß-Zoll, Zoll, m, cm, mm) anzugeben, unabhängig von der Einheiteneinstellung in FormIt in der aktiven Skizze.

![](../.gitbook/assets/dynamo\_formitlengthstring.png)

Wie bei anderen unterstützten Eingabeblöcken wird _FormItLengthString_ bei Markierung mit Ist Eingabe in der Eigenschaftenpalette von FormIt angezeigt, und bei einer Umbenennung wird der neue Name in FormIt angezeigt:

![](../.gitbook/assets/dynamo\_propertiespalette.png)

Jede Instanz des _FormItLengthString_-Blocks kann in einem beliebigen Einheitentyp verwendet werden, sodass ein einzelnes Dynamo-Diagramm eine Kombination von Einheiten verwenden kann, wie oben gezeigt.

### **Wechseln von reinen Zahlen zu FormItLengthString**

Wenn Sie in FormIt 2022.1.1 und höher einstellen, dass ein Diagramm FormItLengthString-Blöcke verwenden soll (indem Sie den ersten in einem Diagramm platzieren), oder dass ein Diagramm nur reine Zahlen verwenden soll (indem Sie die letzte FormItLengthString-Zeichenfolge entfernen), werden bestimmte Verhaltensweisen beim Bearbeiten eines Diagramms in Dynamo geändert:

* Wenn Sie beim Bearbeiten eines Diagramms den [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes)-Block verwenden, müssen Sie beim Wechseln zwischen den reinen Zahlen und dem _FormItLengthString_-Block wie oben erläutert die Geometrie für jeden _SelectFromFormItNode_-Block erneut auswählen, damit die Ergebnisse in FormIt weiterhin korrekt skaliert werden.
* Nach dem Platzieren des ersten FormItLengthString-Blocks in einem Diagramm verweisen alle Zahlen im Diagramm, die als Bemaßungen dienen (einschließlich reiner Zahleneingaben), auf Meter (die programmeigene Einheit von Dynamo).
   * Der [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes)-Block berücksichtigt die Änderung und stellt sicher, dass die generierte Geometrie in FormIt die richtige Größe beibehält.
   * Umgekehrt gilt, dass durch das Entfernen aller FormItLengthString-Blöcke aus dem Diagramm die reinen Zahlen auf die Einheiteneinstellungen von FormIt (altes Verhalten) verweisen.
* Die numerische Ausgabe von _FormItLengthString_-Blöcken erfolgt ebenfalls in Metern, aber dadurch wird die Größe der geometrischen Ergebnisse in FormIt nicht geändert:

![](<../.gitbook/assets/dynamo\_outputinmeters (1).png>)

### **Andere unterstützte Eingabeblöcke**

Standardeingabeblöcke von Dynamo werden in der FormIt-Gruppe Eigenschaften angezeigt, wenn sie in Dynamo mit Ist Eingabe markiert sind:

* Number Slider
* Integer Slider
* Zahl
* String
* Boolescher Umschalter

Sie können die Eingabeblöcke umbenennen (zur eindeutigen Unterscheidung empfohlen). Der neue Name wird dann in FormIt angezeigt:

![](<../.gitbook/assets/dynamo\_cuboidsize (1).png>)

![](../.gitbook/assets/dynamo\_inputs.png)

## Andere Ausgabeblöcke

Verschiedene Methoden zum Anzeigen von nicht geometrischen Ergebnissen aus Dynamo in FormIt.

### **Beobachtungsblock**

Beobachtungsblöcke, die mit Ist Ausgabe markiert sind, werden in FormIt 2022 und höher im Abschnitt zu Beobachtungsblock-Ausgaben der Gruppe Eigenschaften angezeigt:

![](<../.gitbook/assets/dynamo\_watchnodes (1).png>)

### **Anzeigen von FormIt-Benachrichtigungen**

In FormIt 2022.1 oder höher können Sie FormIt-seitige Benachrichtigungen aus einem Dynamo-Diagramm mithilfe des **UI.ShowNotification**-Blocks anzeigen:&#x20;

![](../.gitbook/assets/dynamo\_notifications.png)

### **Anmelden bei der FormIt-Konsole**

In FormIt 2022.1 oder höher können Sie zusätzliche Daten mithilfe des **FormIt.ConsoleLog**-Blocks direkt an der FormIt-Anwendungskonsole (Skriptausgabefenster) protokollieren:

![](../.gitbook/assets/dynamo\_logtoconsole.png)

## FormIt-Optionsblöcke

Steuern Sie, wie Daten an FormIt gesendet werden, entweder auf der Ebene der jeweiligen Geometrie oder auf der Ebene der Gruppe, die sie enthält.

### **FormItGeometryOptions**

FormIt 2022.1 und höher bietet die Möglichkeit, die Art und Weise, wie einzelne Dynamo-Geometrien mit **FormItGeometryOptions**-Blöcken an FormIt gesendet werden, anzupassen.

* Geben Sie den Layer für einzelne Geometrien in der generierten Dynamo-Gruppe an.
* Geben Sie ein Zeichenfolgenattribut für die einzelnen Geometrien in der generierten Dynamo-Gruppe an.

_FormItGeometryOptions_-Blöcke können vor dem _SendToFormIt_-Block verwendet werden:

![](<../.gitbook/assets/dynamo\_formitgeometryoptions (1).png>)

### **FormItGroupOptions**

FormIt 2022 und höher bietet die Möglichkeit, die Art und Weise, wie die Dynamo-Gruppe aus dem _SendToFormIt_-Block in FormIt generiert wird, mithilfe von **FormItGroupOptions**-Blöcken anzupassen.

* Geben Sie an, ob der SendToFormIt-Block Geometrie als Netz oder Objekt an FormIt sendet.
* Geben Sie den Layer für die durch den SendToFormIt-Block erstellte Gruppe an.
* Geben Sie ein Zeichenfolgenattribut für die durch den SendToFormIt-Block erstellte Gruppe an.

Sie können eine beliebige Kombination von FormItGroupOptions-Blöcken in beliebiger Reihenfolge verwenden, indem Sie sie verketten:

![](../.gitbook/assets/dynamo\_daisychain.png)

## JavaScript-API-Blöcke

FormIt 2022.1 und neuer bietet über zwei neue Blöcke Zugriff auf JavaScript-APIs und benutzerdefinierte Funktionen aus Dynamo:

### **CallJSAPI**

Der **CallJSAPI**-Block ermöglicht Ihnen das Aufrufen von FormIt-JavaScript-APIs direkt aus Dynamo.

![](<../.gitbook/assets/dynamo\_calljsapi (1).png>)

Informationen zu Funktionsnamen und Parametern finden Sie in unserer JavaScript-Dokumentation, die in zwei Teile unterteilt ist: [FormIt-API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) und [WSM-API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (Modellierungs-Kernel).

**CallPluginJS**

Umgekehrt können Sie mit dem **CallPluginJS**-Block benutzerdefinierte Funktionen von einem geladenen Plugin oder einem Skript-Snippet aus aufrufen, das im Skript-Editor-Fenster ausgeführt wird.

![](<../.gitbook/assets/dynamo\_callpluginjs (1).png>)

## Wichtige Hinweise

### **Systemanforderungen**

* Um Dynamo in FormIt verwenden zu können, benötigen Sie [FormIt for Windows](https://formit.autodesk.com/page/download) v17.0 oder höher.
   * Die Integration von FormIt und Dynamo erhält regelmäßig neue Funktionen und Lösungsansätze für Probleme. Es ist daher immer ratsam, die neuesten Updates herunterzuladen, sobald diese verfügbar sind.
* Sie benötigen außerdem Windows 10. Aus technischen Gründen werden ältere Versionen von Windows nicht mehr unterstützt.

**Fehlerbeseitigung**

* Wenn Sie ein System mit einer [NVIDIA- oder AMD-Grafikkarte](https://www.howtogeek.com/414201/how-to-check-what-graphics-card-gpu-is-in-your-pc/) oder mehreren Karten nutzen, müssen Sie möglicherweise FormIt und Dynamo so einrichten, dass sie die leistungsstarke GPU verwenden:
   * _C:/Programme/Autodesk/FormIt/FormIt.exe_
   * _C:/Programme/Autodesk/FormIt/DynamoSandbox/FormItDynamoSandbox.exe_
   * Wenn Sie eine NVIDIA-Karte nutzen, [stellen Sie sicher, dass die NVIDIA-Systemsteuerung installiert ist](https://whatsabyte.com/blog/find-nvidia-control-panel/).
   * Verwenden Sie die [NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a\_id/2615/\~/how-do-i-customize-optimus-profiles-and-settings%3F)- oder [AMD](https://www.amd.com/de/support/kb/faq/dh-017)-Systemsteuerung, um die folgenden Anwendungen so einzustellen, dass Ihre eigenständige Grafikkarte verwendet wird:
* Wenn Sie sich in einem nicht englischsprachigen Gebietsschema befinden, müssen Sie möglicherweise die Windows 10-Ländereinstellungen auf Englisch festlegen, um Probleme mit bestimmten Dynamo-Blöcken zu vermeiden:
   * Suchen Sie im Startmenü nach Sprache, und wählen Sie Spracheinstellungen.
   * Klicken Sie oben rechts im Dialogfeld Sprache auf Administrative Sprachoptionen.
   * Klicken Sie auf die Schaltfläche Gebietsschema ändern.
   * Wählen Sie Englisch (USA).
* Wenn bei der Arbeit mit kleinen Geometrien oder Zahlen die Diagramme keine Ergebnisse in FormIt generieren, ändern Sie die Dynamo-Skalierungseinstellung in Klein:
   * Dynamo-Menü > Voreinstellungen > Allgemein > Geometrieskalierung > Klein

![](../.gitbook/assets/dynamo\_geometryscaling.png)

### **Unterstützung erhalten**

Benötigen Sie Hilfe bei FormIt und Dynamo? [In den Foren können Sie uns dies mitteilen](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=de).
