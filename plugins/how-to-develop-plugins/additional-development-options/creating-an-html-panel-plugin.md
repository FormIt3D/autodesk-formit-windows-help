# Vytvoření modulu plug-in panelu HTML

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

Modul plug-in založený na panelu, který zobrazuje stránku HTML, má soubor _manifest.json_ s následující strukturou:

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

Kromě [standardních vlastností JSON](../advanced-development/general-plugin-setup-in-the-manifest.md) obsahuje modul plug-in založený na panelu tyto speciální vlastnosti JSON:

* Paramer „Panel“sděluje aplikaci FormIt, že tento modul plug-in je panel a odkazuje na umístění souboru HTML, který má být načten do panelu.
* Soubor HTML bude potřebovat odkazy v záhlaví na příslušné soubory jazyka JavaScript a také na soubor CSS pro styly.
* Soubor HTML se na panelu aplikace FormIt rendruje stejně jako v prohlížeči.
* Příklady rozhraní HTML naleznete v naší [struktuře FormIt3D](https://github.com/FormIt3D/)
* „PanelIcon“ definuje ikonu tohoto modulu plug-in, která se zobrazí na kartě v pravé části aplikace. Pokud není definována, aplikace FormIt vytvoří automatickou ikonu pomocí iniciál z názvu modulu plug-in.

Po nastavení souborů HTML, CSS a JavaScript můžete začít testovat modul plug-in panelu HTML [jeho načtením nebo instalací](../advanced-development/setting-up-formit-for-development.md#load-vs.-install).
