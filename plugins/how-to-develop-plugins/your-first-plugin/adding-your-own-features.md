# Добавление собственных функций

### Внутри панелей HTML, JavaScript и CSS

При нажатии кнопки «Изменить» в примере подключаемого модуля Plugin Playground отображаются панели HTML, JavaScript (JS) и CSS. Панель HTML (слева) позволяет изменять пользовательский интерфейс подключаемого модуля. Панель JS (в середине) позволяет записывать функции, которые могут взаимодействовать с FormIt посредством API подключаемого модуля FormIt JS. Наконец, панель CSS (справа) определяет стиль HTML.

![](<../../../.gitbook/assets/image (27).png>)

### Добавление функции для создания цилиндра

Чтобы создать цилиндр, добавим функцию в этот подключаемый модуль.

Сначала необходимо настроить поле ввода и кнопку пользовательского интерфейса на панели HTML. Скопируйте следующий код и вставьте его после строки 23 и перед разделом _\<!-- Не удаляйте приведенные ниже сценарии, если не уверены в своих действиях -- > _

Это позволит добавить некоторые базовые элементы пользовательского интерфейса в наш подключаемый модуль.

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

Теперь добавим две функции на панели JS. Скопируйте следующий код и вставьте его в конец файла (после строки 16).

Это приведет к созданию цилиндра в рабочем пространстве FormIt.

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

### Запуск и предварительный просмотр

Когда вы будете готовы посмотреть результаты, снова нажмите кнопку воспроизведения ![ ](<../../../.gitbook/assets/image (81).png>). На той же панели будут отображаться обновления подключаемого модуля.

![](<../../../.gitbook/assets/image (14).png>)

### API подключаемых модулей FormIt

Полную документацию по API для подключаемых модулей FormIt см. в разделе [полезных ссылок](../useful-links.md).
