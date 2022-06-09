# Создание подключаемого модуля панели HTML

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

Подключаемый модуль панели HTML, отображающий HTML-страницу, имеет файл _manifest.json_ со следующей структурой.

```
{
    "PluginName": "Hello Block!",
    "PluginType": "Panel",
    "PluginDescription": "Creates a panel with an HTML form that allows dimensional input for a 3D block which will get generated at the world origin.",
    "Scripts": [
        "PLUGINLOCATION/block.js"
    ],
    "Panel": "PLUGINLOCATION/hello_block.html",
    "PanelIcon": "PLUGINLOCATION/hello_block.png"
}               
```

В дополнение к [стандартным свойствам JSON](../advanced-development/general-plugin-setup-in-the-manifest.md) подключаемый модуль панели HTML содержит следующие специальные свойства JSON.

* Panel сообщает FormIt, что этот подключаемый модуль является панелью, и указывает на местоположение файла HTML, который должен быть загружен на панель.
* Для файла HTML в заголовке требуются ссылки на соответствующие файлы JavaScript, а также на файл CSS для определения стиля.
* Файл HTML будет визуализирован на панели FormIt в таком же виде, как это могло быть сделано в браузере.
* Примеры полнофункциональных интерфейсов HTML можно найти на странице [организации FormIt3D](https://github.com/FormIt3D/).
* PanelIcon определяет значок для этого подключаемого модуля, который будет отображаться на вкладке в правой части приложения. Если ничего не определено, FormIt создает автоматический значок, использующий заглавные буквы из имени подключаемого модуля.

После настройки файлов HTML, CSS и JavaScript можно начать тестирование подключаемого модуля панели HTML посредством [его загрузки или установки](../advanced-development/setting-up-formit-for-development.md#load-vs.-install).
