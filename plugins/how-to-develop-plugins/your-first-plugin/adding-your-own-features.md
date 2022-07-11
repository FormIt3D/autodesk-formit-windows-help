# Aggiunta di funzionalità personalizzate

### All'interno dei pannelli HTML, JavaScript e CSS

Quando si fa clic su Edit nel plug-in di esempio Plugin Playground, vengono visualizzati i pannelli HTML, JavaScript (JS) e CSS. Il pannello HTML (a sinistra) consente di modificare l'interfaccia utente del plug-in. Il pannello JS (al centro) consente di scrivere funzioni in grado di comunicare con FormIt utilizzando l'API del plug-in JS di FormIt. Infine, il pannello CSS (a destra) determinerà lo stile del codice HTML.

![](<../../../.gitbook/assets/image (27).png>)

### Aggiunta di una funzione per la creazione di un cilindro

Aggiungiamo una funzionalità a questo plug-in per creare un cilindro.

Innanzitutto, configuriamo il campo di input e il pulsante dell'interfaccia utente nel pannello HTML. Copiare il seguente codice e incollarlo dopo la riga 23 e prima di _\<!-- Do not remove below scripts unless you know what you're doing- - >_.

In questo modo verranno aggiunti alcuni elementi dell'interfaccia utente di base al plug-in.

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

Ora, aggiungiamo due funzioni nel nostro pannello JS. Copiare il seguente codice e incollarlo alla fine del file (dopo la riga 16).

In questo modo verrà creato un cilindro nell'area di lavoro di FormIt.

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

### Esecuzione e anteprima

Quando si è pronti a vedere i risultati, fare nuovamente clic sul pulsante di riproduzione ![](<../../../.gitbook/assets/image (81).png>) e visualizzare gli aggiornamenti al plug-in nello stesso pannello.

![](<../../../.gitbook/assets/image (14).png>)

### API dei plug-in di FormIt

Per la documentazione completa sull'API dei plug-in di FormIt, vedere la sezione dei [collegamenti utili](../useful-links.md).
