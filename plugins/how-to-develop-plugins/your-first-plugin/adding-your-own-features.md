# Hinzufügen eigener Funktionen

### In den Gruppen HTML, JavaScript und CSS

Wenn Sie im Beispiel-Plugin Plugin Playground auf Edit klicken, werden die Gruppen HTML, JavaScript (JS) und CSS angezeigt. In der Gruppe HTML (links) können Sie die Benutzeroberfläche Ihres Plugins ändern. Die Gruppe JS (Mitte) ermöglicht Ihnen das Schreiben von Funktionen, die über die FormIt-JS-Plugin-API mit FormIt kommunizieren können. Schließlich bestimmt die Gruppe CSS (rechts) den Stil Ihres HTML-Codes.

![](<../../../.gitbook/assets/image (27).png>)

### Hinzufügen einer Funktion zum Erstellen eines Zylinders

Wir fügen diesem Plugin eine Funktion hinzu, um einen Zylinder zu erstellen.

Zunächst konfigurieren wir das Eingabefeld und die Schaltfläche UI in der Gruppe HTML. Kopieren Sie den folgenden Code, und fügen Sie ihn nach Zeile 23 und vor _\<! ein.-- Entfernen Sie die unten aufgeführten Skripte nicht, es sei denn, Sie wissen, was Sie tun- - >_

Dadurch werden einige grundlegende Elemente der Benutzeroberfläche zu unserem Plugin hinzugefügt.

```
<p>Cylinder: Create a cylinder at the origin.</p>
<div>
    <input id="Radius" type=number value=2 />
    <label>Radius</label>
</div>

<div>
    <input id="CHeight" type=number value =0.5 />
    <label>Height</label>
</div>


<input id="CreateCylinderBtn" type=button value="Create Cylinder" />

```

![](<../../../.gitbook/assets/image (86).png>)

Als Nächstes fügen wir zwei Funktionen in der JS-Gruppe hinzu. Kopieren Sie den folgenden Code, und fügen Sie ihn am Ende der Datei (nach Zeile 16) ein.

Dadurch wird ein Zylinder im FormIt-Arbeitsbereich erstellt.

```
// Create cylinder
const createCylinder = async (r,h) =>
{
    const posCenter = await WSM.Geom.Point3d(0,0,0);

    const histID = await FormIt.GroupEdit.GetEditingHistoryID();
    console.log(histID,posCenter,r,h);

    const cyl = await WSM.APICreateCylinder(histID,posCenter,r,h);
}


// Execute function when 'create cylinder' button is clicked
document.getElementById("CreateCylinderBtn").addEventListener("click", ()=>
{
    console.log('create cylinder clicked')

    const r = Number(document.getElementById("Radius").value);
    const h = Number(document.getElementById("CHeight").value);

    createCylinder(r,h);

});
```

![](<../../../.gitbook/assets/image (82).png>)

### Ausführen und Vorschau

Wenn Sie die Ergebnisse sehen möchten, klicken Sie erneut auf die Schaltfläche Wiedergabe ![](<../../../.gitbook/assets/image (81).png>). Ihre Aktualisierungen des Plugins werden in derselben Gruppe angezeigt.

![](<../../../.gitbook/assets/image (14).png>)

### FormIt-Plugin-API

Eine vollständige Dokumentation zur FormIt-Plugin-API finden Sie im Abschnitt [Nützliche Links](../useful-links.md).
