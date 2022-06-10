# Adicionar seus próprios recursos

### Dentro dos painéis HTML, JavaScript e CSS

Quando você clicar em Editar no plug-in de amostra Plugin Playground, verá os painéis HTML, JavaScript (JS) e CSS. O painel HTML (à esquerda) permite modificar a interface do usuário do plug-in. O painel JS (meio) permite gravar funções que podem se comunicar com o FormIt usando a API do plug-in JS do FormIt. Finalmente, o painel CSS (direita) determinará o estilo do HTML.

![](<../../../.gitbook/assets/image (27).png>)

### Adicionar uma função para criar um cilindro

Vamos adicionar uma figura a esse plug-in para criar um cilindro.

Primeiro, vamos configurar o campo de entrada e o botão da interface do usuário no painel HTML. Copie o seguinte código e cole-o após a linha 23 e antes de _\<!— Não remova os scripts abaixo, a menos que você saiba o que está fazendo — >_

Isso adicionará alguns elementos básicos da interface do usuário ao nosso plug-in.

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

Em seguida, vamos adicionar duas funções ao painel JS. Copie o seguinte código e cole-o no final do arquivo (após a linha 16).

Isso criará um cilindro em nosso espaço de trabalho do FormIt.

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

### Execução e visualização

Quando estiver pronto para ver os resultados, clique no botão Reproduzir ![](<../../../.gitbook/assets/image (81).png>) novamente e você verá no mesmo painel as atualizações que fez no plug-in.

![](<../../../.gitbook/assets/image (14).png>)

### API de plug-ins do FormIt

Para obter a documentação completa sobre a API de plug-ins do FormIt, consulte a seção [links úteis](../useful-links.md).
