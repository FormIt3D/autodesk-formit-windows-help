# Plugin Properties Plus

_Dieses Plugin ist eine Version mit mehr Funktionen als in der Standard-_ _**Eigenschaftenpalette**. Wenn Sie mehrere Gruppen und/oder Geometrietypen auswählen, bietet Ihnen dieses Plugin eine Aufschlüsselung der ausgewählten Elemente und ermöglicht die gebündelte Umbenennung von Gruppen und Gruppenexemplaren._

1 **–** Zunächst betrachten Sie die Eigenschaften einer Türgruppe aus der Basisvorlage. Öffnen Sie die Datei **Encode Campus Sample Model.axm** erneut, und kehren Sie zur Szene **Eye Level – Long Alley** zurück. So verwenden Sie das Plugin **Properties Plus**

1. Öffnen Sie die **Properties Plus-Palette**, indem Sie auf die Eigenschaft mit dem Pluszeichen klicken.
2. Stellen Sie sicher, dass **Bei Auswahländerung aktualisieren** aktiviert ist.
3. Wählen Sie eine der Doppelglas-Türgruppen mit dem Namen **Door** auf der rechten Seite der Gasse aus.
4. Im Bereich **Auswahlzähler** wird unter **Objekte gesamt** angegeben, dass ein (**1**) Objekt ausgewählt wurde.
5. Direkt darunter finden Sie weitere Informationen zu den ausgewählten Objekttypen. In diesem Fall ist eine (**1**) Gruppe ausgewählt, aber diese Gruppe hat vier (**4**) Exemplare im Modell.

![](<../../.gitbook/assets/10 (2) (1).png>)

_**Anmerkung:**_ _Die Überprüfung der Anzahl der Exemplare der ausgewählten Gruppe kann sehr praktisch sein, um zu verhindern, dass versehentlich mehrere Elemente geändert werden, obwohl Sie eigentlich nur das ausgewählte Element ändern wollten, aber vergessen haben, es zuerst eindeutig zu machen._

2 – Dieses Plugin ermöglicht es Ihnen, den Namen einer Gruppe oder eines Gruppenexemplars zu ändern, ohne in den Gruppenbearbeitungsmodus wechseln zu müssen, und mehrere Exemplare gleichzeitig umzubenennen. Wie Sie bereits erfahren haben, hat jede Gruppe einen Namen, aber jedes Exemplar dieser Gruppe kann auch einen eindeutigen Exemplarnamen haben. Da dieses Modell wahrscheinlich viele Türtypen enthält, sollten Sie dieser Gruppe und einigen ihrer Exemplare spezifischere Namen geben.

1. Fügen Sie bei ausgewählter erster **Glastürgruppe** der aktuellen Auswahl eine weitere **Türgruppe** hinzu, indem Sie die **UMSCHALTTASTE** oder **STRG-Taste** gedrückt halten und auf die andere Doppelglas-**Türgruppe** in der Nähe der ersten Gruppe klicken.
2. Beachten Sie, dass in der **Properties Plus-Palette** der **Auswahlzähler** aktualisiert wurde, um anzuzeigen, dass zwei (**2**) Exemplare ausgewählt sind, aber immer noch nur eine (**1**) eindeutige **Familie** (d. h. Gruppe) ausgewählt ist. (Obwohl für dieses Plugin der Begriff **Familie** verwendet wird, der Revit-Benutzern vertraut sein sollte, handelt es sich in diesem Zusammenhang um eine FormIt-Gruppe.)
3. Ändern Sie im Bereich **Gruppenfamilie** das Feld **Name** in **Doors – Double Glass Storefront**. Dadurch wird der Name der Gruppe für alle Exemplare aktualisiert, unabhängig davon, wo sie sich befinden bzw. ob sie derzeit ausgewählt sind oder nicht, ohne dass Sie auf die Gruppe doppelklicken und sie bearbeiten müssen.
4. Da diese beiden Exemplare Türen zum „Groove Coffee“-Bereich darstellen, sollten Sie diese beiden Exemplare umbenennen, indem Sie **Groove Coffee Door** in das Feld **Name** im Bereich **Mehrere Gruppenexemplare** eingeben.

**Anmerkung:** In der Standard-**Eigenschaftenpalette** gibt es keine Möglichkeit, mehrere Exemplare einer Gruppe gleichzeitig umzubenennen. Dies kann sehr praktisch sein, wenn Sie Dutzende oder Hunderte von Exemplaren mit demselben Namen gleichzeitig umbenennen möchten.

![](<../../.gitbook/assets/11 (6) (1).png>)

_**Anmerkung:**_ _Wenn Sie den Mauszeiger von der Palette weg bewegen, können Sie das ausgewählte Textfeld nicht mehr bearbeiten. Dies gilt für alle Paletten. Achten Sie daher darauf, dass sich der Cursor innerhalb der Palettenbegrenzung befindet, während Sie Elemente innerhalb einer Palette bearbeiten._

3 – Wenn Sie jetzt eine „Groove Coffee“-Glastür oder eine andere Glastür auswählen und deren Eigenschaften in der regulären **Eigenschaftenpalette** anzeigen, sehen Sie, dass der Name der **Gruppe** für jedes Exemplar aktualisiert wurde. Nur bei den „Groove Coffee“-Türen wurde jedoch der Vorgabewert für die Eigenschaft des **Exemplarnamens** aktualisiert.

![](<../../.gitbook/assets/12 (3) (1).png>)

4 – Sehen Sie sich nun an, wie dieses Plugin verschiedene Elementtypen sortiert:

1. Zeichnen Sie an einer beliebigen Stelle im Modell schnell eine **Linie (L)**, ein **Rechteck (R)** und einen **Würfel (ALT+B)**. Diese sind temporär, sodass ihre genaue Position nicht von Bedeutung ist.
2. Öffnen Sie die **Properties Plus-Palette** erneut, falls sie geschlossen war, und drücken Sie dann **STRG+A**, um alle sichtbaren Elemente im Modell auszuwählen.
3. Sehen Sie sich den Bereich **Auswahlzähler** an. Beachten Sie, dass die ausgewählten Elemente in **Kanten** (Linien), **Flächen**, **Körper**, (3D-Formen aus Flächen und Kanten, wie der Würfel)**,** **Gruppen** und vieles mehr unterteilt sind.

![](<../../.gitbook/assets/13 (3) (1).png>)

_**Anmerkung:**_ _Dieses Plugin erkennt auch_ _**Scheitelpunkte**, die mit einem anderen Plugin namens_ _**Generate Vertex** erstellt werden können. Wenn Sie experimentieren möchten, installieren Sie das_ _**Plugin Generate Vertex**__, und wiederholen Sie die oben genannten Schritte._
