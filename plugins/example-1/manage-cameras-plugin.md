# Plugin Manage Cameras

_In diesem Kapitel werden einige der Plugins in FormIt behandelt, um Verbesserungen an der Datei_ _**Encode Campus Sample Model.axm** vorzunehmen. Wenn Sie dies nicht bereits getan haben, können Sie die Datei aus dem_ [_FormIt Primer Part II DataSet_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip)__ herunterladen.

Während der gesamten Einführung haben Sie Szenen als wertvolle Hilfsmittel verwendet, um im gesamten Modell zu navigieren und die Sichtbarkeit zu steuern. Mit diesem Plugin können Sie die Höhe der aktuellen Kamera anzeigen und bearbeiten, Kameras für jede Szene als 3D-Objekte exportieren und diese Szenen zwischen Modellen kopieren.

1 – Zunächst passen Sie die Szene **Eye Level – Long Alley** so an, dass sich die Kamera tatsächlich auf Augenhöhe befindet:

1. Kehren Sie ggf. zur Szene **Eye Level – Long Alley** zurück, indem Sie in der **Szenenpalette** darauf doppelklicken.
2. Öffnen Sie die **Manage Cameras-Palette**, indem Sie auf die Kamera mit dem Zahnradsymbol klicken.
3. Ändern Sie die Einstellung **Überschüttung** in **5'-8"**.

![](<../../.gitbook/assets/6 (6) (1).png>)

_**Anmerkung:**_ _Wenn Ihr Modell Ebenen besitzt, zeigt dieses Plugin auch die Höhe über der nächstgelegenen Ebene unter der_ _**Hauptkamera** an._

2 – Dann:

1. Wechseln Sie zurück zur **Szenenpalette**.
2. Stellen Sie sicher, dass die Szene **Eye Level – Long Alley** noch ausgewählt ist (andernfalls klicken Sie darauf, um sie auszuwählen).
3. Klicken Sie auf die Schaltfläche **Szene aktualisieren**, um die neue Kamerahöhe in dieser Szene zu speichern.

![](<../../.gitbook/assets/7 (1) (1).png>)

_**Anmerkung:**_ _Sie können den Winkel und die Position der Kamera einer Szene auch anpassen, indem Sie die Schaltfläche_ _**Szenenkameras bearbeiten**_ _oben in der_ _**Szenenpalette**_ _(zwischen den Schaltflächen Aktualisieren und Abspielen) aktivieren bzw. deaktivieren._

3 – Als Nächstes exportieren Sie die Szenen in ein neues Modell. Zunächst müssen Sie mithilfe des Plugins **Manage Cameras** Kameraobjekte für alle Szenen erstellen:

1. Öffnen Sie die **Manage Cameras-Palette** erneut.
2. Stellen Sie sicher, dass die Option **Kameras in Zwischenablage kopieren** aktiviert ist.
3. Klicken Sie auf die Schaltfläche **Szenen in Kameras exportieren**. Dies kann ein paar Sekunden dauern.
4. Wenn der gesamte Ansichtsbereich weiß wird, liegt das daran, dass die **Hauptkamera** an einer der Szenenkameras ausgerichtet war. Verwenden Sie **Zoom (Z)**, um die Ansicht zu verkleinern, bis Sie die drei Hauptgebäude und die neu erstellten Kameraobjekte sehen können. Beachten Sie, dass die Kameraobjekte automatisch in einer großen Gruppe mit dem Namen **Cameras** platziert werden. Innerhalb dieser Gruppe wird jede einzelne Kamera in einer eigenen Gruppe platziert, die denselben Namen hat wie die Szenen, aus denen sie erstellt wurde.

![](<../../.gitbook/assets/8 (7) (1).png>)

4 – Kopieren Sie diese Szenen in ein neues Modell. Da die Kameradaten in der Zwischenablage gespeichert wurden, müssen Sie nicht viel tun:

1. **Speichern** **(STRG+S)** Sie das aktuelle Modell, und schließen Sie es.
2. Beginnen Sie eine neue leere Skizze, indem Sie **Neue Skizze (STRG+N)** aus der Dropdown-Liste **Datei** in der **Hauptmenüleiste** auswählen.
3. Öffnen Sie das Plugin **Manage Cameras**, falls es nicht bereits geöffnet ist, und stellen Sie sicher, dass die Option **In Zwischenablage nach Kameras suchen** aktiviert ist.
4. Klicken Sie auf die Schaltfläche **Szenen aus Kameras importieren** unten im Plugin. Die Szenen aus dem anderen Modell werden importiert. Um dies zu überprüfen, öffnen Sie die **Szenenpalette** und/oder aktivieren den Layer **Camera**. Sie werden sehen, dass alle Szenen und 3D-Kameraobjekte in dieses Modell importiert wurden.

![](<../../.gitbook/assets/9 (7) (1).png>)
