# Adición de sus propias funciones

### Descripción de los paneles HTML, JavaScript y CSS

Al hacer clic en Edit en el módulo de extensión de ejemplo de Plugin Playground, verá los paneles HTML, JavaScript (JS) y CSS. El panel HTML (izquierda) permite modificar la interfaz de usuario del módulo de extensión. El panel JS (centro) permite escribir funciones que se pueden comunicar con FormIt mediante la API del módulo de extensión de JS de FormIt. Por último, el panel CSS (derecha) determinará el estilo del contenido HTML.

![](<../../../.gitbook/assets/image (27).png>)

### Adición de una función para crear un cilindro

Vamos a añadir una función a este módulo de extensión para crear un cilindro.

En primer lugar, vamos a configurar el campo de entrada y el botón de la interfaz de usuario en el panel HTML. Copie el código siguiente y péguelo después de la línea 23 y antes _\<!-- No elimine las siguientes secuencias de comandos a menos que esté familiarizado con este procedimiento- - >_

Esta acción añadirá algunos elementos básicos de la interfaz de usuario a nuestro módulo de extensión.

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

A continuación, vamos a añadir dos funciones en el panel JS. Copie el código siguiente y péguelo al final del archivo (después de la línea 16).

Esta acción creará un cilindro en el espacio de trabajo de FormIt.

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

### Ejecución y previsualización

Cuando esté listo para ver los resultados, haga clic de nuevo en el botón de reproducción ![](<../../../.gitbook/assets/image (81).png>); aparecerán las actualizaciones realizadas en el módulo de extensión dentro del mismo panel.

![](<../../../.gitbook/assets/image (14).png>)

### API de módulos de extensión de FormIt

Para obtener documentación completa sobre la API de módulos de extensión de FormIt, consulte la sección de [vínculos útiles](../useful-links.md).
