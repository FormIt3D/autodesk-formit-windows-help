# Přidání vlastních funkcí

### Panely jazyků HTML, JavaScript a CSS

Když kliknete na tlačítko Edit (Upravit) ve vzorovém modulu plug-in Plugin Playground, uvidíte panely HTML, JavaScript (JS) a CSS. Panel HTML (vlevo) umožňuje upravit uživatelské rozhraní modulu plug-in. Panel JS (uprostřed) umožňuje psát funkce, které mohou komunikovat s aplikací FormIt pomocí rozhraní API modulu plug-in FormIt JS. Pomocí panelu CSS (vpravo) můžete definovat styl HTML.

![](<../../../.gitbook/assets/image (27).png>)

### Přidání funkce pro vytvoření válce

Přidejte do tohoto modulu plug-in funkci pro vytvoření válce.

Nejprve nakonfigurujte vstupní pole a tlačítko uživatelského rozhraní v panelu HTML. Zkopírujte následující kód a vložte jej za řádek 23 a před řádek _\<!-- Do not remove below scripts unless you know what you're doing- - >_

Tím do modulu plug-in přidáte některé základní prvky uživatelského rozhraní.

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

Nyní přidejte dvě funkce na panelu JS. Zkopírujte následující kód a vložte jej na konec souboru (za řádek 16).

Tento kód umožní v pracovním prostoru aplikace FormIt vytvořit válec.

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

### Spuštění a náhled

Až si budete chtít prohlédnout výsledky, klikněte znovu na tlačítko Přehrát ![] (<../../../.gitbook/assets/image (81).png>) a na stejném panelu se zobrazí aktualizace modulu plug-in.

![](<../../../.gitbook/assets/image (14).png>)

### Rozhraní API modulů plug-in pro aplikaci FormIt

Úplnou dokumentaci k rozhraní API modulů plug-in pro aplikaci FormIt naleznete v části [užitečné odkazy](../useful-links.md).
