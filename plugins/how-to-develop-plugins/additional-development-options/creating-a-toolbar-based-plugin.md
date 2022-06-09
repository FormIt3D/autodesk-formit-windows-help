# Tworzenie wtyczki opartej na pasku narzędzi

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### Struktura pliku manifest.json wtyczki opartej na pasku narzędzi

Wtyczka oparta na pasku narzędzi ma plik _manifest.json_ o następującej strukturze:

```
{
    "PluginName": "Flip Along",
    "PluginType": "Toolbar",
    "PluginDescription": "Creates a toolbar with X, Y, and Z buttons to quickly flip selected geometry in the direction of the selected axis.",
    "ToolbarURL": "PLUGINLOCATION/toolbar.json",
    "Scripts": [
        "PLUGINLOCATION/flipalong.js"
    ]
}               
```

Oprócz [standardowych właściwości JSON](../advanced-development/general-plugin-setup-in-the-manifest.md) wtyczka oparta na pasku narzędzi zawiera tę specjalną właściwość JSON:

* „ToolbarURL” — informuje program FormIt, że ta wtyczka jest paskiem narzędzi i zapewnia połączenie z położeniem innego pliku JSON, w którym opisano funkcje paska narzędzi.

### Konfigurowanie formatu paska narzędzi za pomocą pliku JSON

Po utworzeniu pliku manifestu, takiego jak opisany powyżej, należy utworzyć plik toolbar.json, w którym zdefiniowane zostaną przyciski paska narzędzi, ich nazwy, tekst, ikony i funkcja onClick przypisana do każdego przycisku. Plik JSON paska narzędzi będzie miał następujący format:

```
{
    "name": "Flip Along Toolbar",
    "buttons": [
        {
            "name": "Flip Along X",
            "command": "FlipAlongPlugin.ButtonX",
            "iconText": "X",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Y",
            "command": "FlipAlongPlugin.ButtonY",
            "iconText": "Y",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Z",
            "command": "FlipAlongPlugin.ButtonZ",
            "iconText": "Z",
            "iconURL": "[Icon URL]"
        }
    ]
}               
```

Plik toolbar.json zawiera następujące właściwości JSON:

* „name” — reprezentuje nazwę całego paska narzędzi i jest wewnętrznie używana do kojarzenia wszystkich przycisków z pojedynczym menu paska narzędzi.
* „buttons” — reprezentuje poszczególne przyciski dodane wewnątrz paska narzędzi. Pasek narzędzi może mieć dowolną liczbę przycisków.
* „name” — definiuje nazwę wewnętrzną przycisku, która jest używana do kojarzenia przycisku z paskiem narzędzi oraz z funkcją onClick przycisku.
* „command” — definiuje funkcję przycisku, która może być w jednej z dwóch postaci: funkcji JavaScript (może być ona zdefiniowana w skrypcie zawartym w polu „Scripts” pliku manifest.json) lub polecenia programu FormIt, na przykład „Draw: Circle” (Rysuj: okrąg). Listę poleceń programu FormIt można uzyskać, uruchamiając wtyczkę komunikatów: Messages.
* „iconText” — ustawia tekst etykiety narzędzia i tekst opisu przycisku. Jeśli nie podano adresu URL ikony, z tekstu zostanie automatycznie wygenerowana ikona sformatowanego tekstu.
* Można ustawić właściwość „iconURL”, aby zdefiniować ikonę niestandardową dla przycisku.

Po zdefiniowaniu wszystkich przycisków w pliku toolbar.json wtyczka jest gotowa do użycia.&#x20;

Jeśli chcesz zdefiniować jakieś dodatkowe funkcje JavaScript, dodaj je do tego samego folderu, w którym znajduje się plik manifest.json. Ponadto koniecznie dodaj odniesienie do pliku w polu „Scripts” pliku manifestu, aby program FormIt mógł znaleźć pliki.
