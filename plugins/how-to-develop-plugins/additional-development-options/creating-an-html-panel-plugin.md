# Tworzenie wtyczki panelu HTML

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

Wtyczka oparta na panelu, która wyświetla stronę HTML, ma plik _manifest.json_ o następującej strukturze:

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

Oprócz [standardowych właściwości JSON](../advanced-development/general-plugin-setup-in-the-manifest.md) wtyczka oparta na panelu zawiera następujące specjalne właściwości JSON:

* „Panel” — informuje program FormIt, że ta wtyczka jest panelem i zapewnia połączenie z położeniem pliku HTML, który powinien zostać wczytany do panelu.
* Plik HTML musi mieć w nagłówku łącza do odpowiednich plików JavaScript, jak również do pliku CSS, za pomocą którego zostaną przypisane style.
* Plik HTML będzie renderowany w panelu programu FormIt tak jak w przeglądarce.
* Przykłady zaawansowanych interfejsów HTML można znaleźć w naszej [organizacji FormIt3D](https://github.com/FormIt3D/).
* „PanelIcon” — definiuje ikonę tej wtyczki, która ma być wyświetlana na karcie po prawej stronie aplikacji. Jeśli nie jest zdefiniowana, program FormIt tworzy automatyczną ikonę, używając pierwszych liter wyrazów z nazwy wtyczki.

Po skonfigurowaniu plików HTML, CSS i JavaScript można rozpocząć testowanie wtyczki panelu HTML, [wczytując ją lub instalując](../advanced-development/setting-up-formit-for-development.md#load-vs.-install).
