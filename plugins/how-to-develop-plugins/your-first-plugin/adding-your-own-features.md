# Dodawanie własnych funkcji

### Panele HTML, JavaScript i CSS

Po kliknięciu przycisku Edit (Edytuj) w przykładowej wtyczce w obszarze Plugin Playground (Zabawa z wtyczkami) zostaną wyświetlone panele HTML, JavaScript (JS) i CSS. Panel HTML (po lewej) umożliwia modyfikowanie interfejsu użytkownika wtyczki. Panel JS (środkowy) umożliwia pisanie funkcji, które mogą komunikować się z programem FormIt za pomocą interfejsu API wtyczki JS programu FormIt. Natomiast panel CSS (po prawej) określa styl HTML.

![](<../../../.gitbook/assets/image (27).png>)

### Dodawanie funkcji do tworzenia walca

Dodajmy do tej wtyczki element służący do tworzenia walca.

Najpierw skonfigurujmy pole wprowadzania i przycisk interfejsu użytkownika w panelu HTML. Skopiuj następujący kod i wklej go po 23. wierszu i przed tekstem _\<!-- Do not remove below scripts unless you know what you're doing- - >_

Spowoduje to dodanie do wtyczki pewnch podstawowych elementów interfejsu użytkownika.

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

Następnie dodajmy dwie funkcje w panelu JS. Skopiuj następujący kod i wklej go na końcu pliku (po 16. wierszu).

Spowoduje to utworzenie walca w obszarze roboczym programu FormIt.

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

### Uruchamianie i podgląd

Gdy wszystko będzie gotowe do wyświetlenia wyników, ponownie kliknij przycisk Odtwórz ![](<../../../.gitbook/assets/image (81).png>), a aktualizacje wtyczki pojawią się w tym samym panelu.

![](<../../../.gitbook/assets/image (14).png>)

### Interfejs API wtyczek programu FormIt

Aby zapoznać się z pełną dokumentacją dotyczącą interfejsu API wtyczek programu FormIt, zobacz sekcję [przydatnych łączy](../useful-links.md).
