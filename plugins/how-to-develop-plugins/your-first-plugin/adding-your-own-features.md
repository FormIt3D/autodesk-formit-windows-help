# Ajout de vos propres fonctionnalités

### Dans les groupes de fonctions HTML, JavaScript et CSS

Lorsque vous cliquez sur Modifier dans l’exemple de plug-in Plugin Playground, les groupes de fonctions HTML, JavaScript (JS) et CSS s’affichent. Le groupe de fonctions HTML (à gauche) vous permet de modifier l’interface utilisateur de votre plug-in. Le groupe de fonctions JS (au milieu) vous permet d’écrire des fonctions qui peuvent communiquer avec FormIt à l’aide de l’API du plug-in JS FormIt. Enfin, le groupe de fonctions CSS (à droite) détermine le style de votre code HTML.

![](<../../../.gitbook/assets/image (27).png>)

### Ajout d’une fonction pour créer un cylindre

Ajoutez une fonction à ce plug-in pour créer un cylindre.

Commencez par configurer le champ de saisie et le bouton d’interface utilisateur dans le groupe de fonctions HTML. Copiez le code suivant et collez-le après la ligne 23 et avant _\<!-- Ne supprimez pas les scripts ci-dessous, sauf si vous savez ce que vous faites -- >_

Cela permet d’ajouter des éléments de base de l’interface utilisateur au plug-in.

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

Ajoutez ensuite deux fonctions dans le groupe de fonctions JS. Copiez le code suivant et collez-le à la fin du fichier (après la ligne 16).

Cela permet de créer un cylindre dans l’espace de travail FormIt.

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

### Exécution et aperçu

Lorsque vous êtes prêt à voir les résultats, cliquez sur le bouton Play (Lecture) ![](<../../../.gitbook/assets/image (81).png>), et vous verrez vos mises à jour du plug-in dans le même groupe de fonctions.

![](<../../../.gitbook/assets/image (14).png>)

### API des plug-ins FormIt

Pour obtenir une documentation complète sur l’API des plug-ins FormIt, reportez-vous à la section [liens utiles](../useful-links.md).
