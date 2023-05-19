# Konfiguracja ogólna wtyczki w manifeście 

Wtyczki programu FormIt mają kluczowy komponent — plik _manifest.json_.

Plik manifestu to [obiekt JSON](http://www.json.org) informujący infrastrukturę programu FormIt, które pliki należy pobrać i jaki rodzaj wtyczki należy utworzyć.

### Struktura i właściwości pliku Manifest.json

Struktura pliku manifest.json jest następująca. Plik ten ma dodatkowe właściwości w zależności od tego, czy jest to [wtyczka oparta na pasku narzędzi](../additional-development-options/creating-a-toolbar-based-plugin.md), czy [wtyczka oparta na panelu HTML](../additional-development-options/creating-an-html-panel-plugin.md).

```
{
    "PluginName": "[PluginName]",
    "PluginType": "[PluginType]"
    "PluginDescription": "[PluginDescription]",
    "Scripts": [
        "PLUGINLOCATION/[script1].js",
        "PLUGINLOCATION/[script2].js",
        ...
        "PLUGINLOCATION/[scriptn].js"
    ]
}               
```

Typowa wtyczka ma następujące właściwości JSON:

* „PluginName” — reprezentuje nazwę wtyczki do celów wewnętrznych i większości celów związanych z wyświetlaniem, w tym dla narzędzia [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager).
* „PluginType” — reprezentuje typ wtyczki, informując użytkowników w opisie w narzędziu [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager), czego oczekiwać w przypadku zainstalowania wtyczki.
* W narzędziu [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) jest wyświetlany opis wtyczki („PluginDescription”) z wyszczególnieniem jej możliwości.
* „Scripts” — zawiera wymagane skrypty zewnętrzne skojarzone z wtyczką, które zostaną wczytane do aplikacji FormIt i mogą być wykonywane po wywołaniu funkcji wtyczki.

![](<../../../.gitbook/assets/image (5) (1).png>)

Rozpocznij tworzenie wtyczki, tworząc plik manifest.json w folderze wtyczki. Następnie należy zdecydować, czy tworzona wtyczka będzie oparta na pasku narzędzi, czy panelu.

![](<../../../.gitbook/assets/image (36).png>)

**Uwaga:** używanie zmiennej PLUGINLOCATION w całym pliku manifest.json powyżej jest bardzo ważne i jest w nim uwzględniana wielkość liter. Program FormIt zastąpi zmienną PLUGINLOCATION położeniem wtyczki na serwerze.
