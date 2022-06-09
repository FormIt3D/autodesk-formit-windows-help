# Generate String Lights

_In diesem Kapitel werden einige der Plugins in FormIt behandelt, um Verbesserungen an der Datei_ _**Encode Campus Sample Model.axm** vorzunehmen. Wenn Sie dies nicht bereits getan haben, können Sie die Datei aus dem_ [_FormIt Primer Part II DataSet_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip)__ herunterladen.

_Mit diesem praktischen Plugin können Sie basierend auf einer Linie oder Kurve schnell Hängeleuchten zu Ihrem Modell hinzufügen._

1 – Bevor Sie neue Leuchten hinzufügen, sehen Sie sich das gewünschte Ergebnis anhand einer vordefinierten Szene im Modell an.

1. Um zu der Szene mit den vorhandenen Lichterketten zu springen, öffnen Sie die **Szenenpalette** und doppelklicken auf die Szene mit dem Namen **Eye Level – Short Alley**.
2. Beachten Sie die in diesem Modell enthaltenen Lichterketten. So in der Art soll Ihr Entwurf auch aussehen, jedoch an anderer Stelle.
3. Aktivieren Sie in der **Layer-Palette** den Layer **Helper Geometry**, sodass Sie die ursprünglichen Linien sehen können, die zum Erstellen dieser Lichterketten verwendet wurden.

![](<../../.gitbook/assets/3 (10).png>)

2 – Navigieren Sie nun zur anderen Gasse und fügen einige Leuchten hinzu. Öffnen Sie in der **Szenenpalette** die Szene **Eye Level – Long Alley**. Beachten Sie, dass diese Gasse noch keine Lichterketten aufweist.

3 – So erstellen Sie eine neue Lichterkette:

1. Öffnen Sie die neu installierte **Generate String Lights-Palette**, indem Sie auf das Lichterketten-Symbol klicken. Vorgabemäßig werden die Symbole für neue Plugins unten angezeigt.
2. Ändern Sie die Option **Anzahl von Installationen** in **10**.
3. Doppelklicken Sie auf eine der Hilfslinien, um die vordefinierte Gruppe **String Lights – Long Alley** zu bearbeiten. Klicken Sie dann auf eine der vorgezeichneten Hilfslinien, um sie auszuwählen.
4. Klicken Sie auf die Schaltfläche **Generate String Lights** in der Palette des Plugins. Eine neue Lichterkette sollte angezeigt werden. Beachten Sie, dass jede Lichterkette als eigene, eindeutige Gruppe erstellt wird.

![](<../../.gitbook/assets/4 (6) (1).png>)

_**Anmerkung:**_ _Es ist nicht schlimm, dass einige der Linien durch das Schild „Groove Coffee“ verlaufen, da mit dem Lichterketten-Plugin eine Kettenlinie erstellt wird, die realitätsgetreu etwas durchhängt und somit unterhalb des Schilds verläuft._

4 – Erstellen Sie weitere Lichterketten, indem Sie die andere vordefinierte Hilfslinie verwenden und/oder eigene Hilfslinien erstellen. Experimentieren Sie mit den Einstellungen des Plugins, um unterschiedliche Ergebnisse zu erhalten.

5 – Um das Modell übersichtlich zu halten, sollten nach Abschluss alle Hilfslinien gruppiert und auf dem Layer **Helper Geometry** platziert werden. Außerdem sollten alle Lichterkettengruppen dem Layer **Context – Exterior Lighting** zugewiesen werden. Dadurch wird verhindert, dass die Hilfslinien in einer der „Eye Level“-Szenen angezeigt werden, in denen sie nicht sichtbar sein sollen. Wenn Sie fertig sind, sollten die Ergebnisse in etwa wie im nächsten Screenshot aussehen.

![](<../../.gitbook/assets/5 (3) (1).png>)

_**Anmerkung:**_ _Im Gegensatz zu Geometrie, die aus einem Dynamo-Skript erstellt wurde und über die_ _**Eigenschaftenpalette** aktualisiert und regeneriert werden kann, stellen die in einem Plugin erstellten Objekte (größtenteils) reguläre FormIt-Geometrie dar. Nach der Erstellung können sie nur mit den integrierten Modellierungswerkzeugen von FormIt bearbeitet werden._
