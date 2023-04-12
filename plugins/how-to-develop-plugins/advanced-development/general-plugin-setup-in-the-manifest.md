# Obecné nastavení modulu plug-in v manifestu

Moduly plug-in aplikace FormIt se skládají z hlavní komponenty zvané soubor _manifest.json_.

Soubor manifestu je [objekt JSON](http://www.json.org), který aplikaci FormIt říká, jaké soubory má načíst a jaký druh modulu plug-in vytvořit.

### Struktura a vlastnosti souboru manifest.json

Soubor manifest.json má následující strukturu. V závislosti na tom, zda se jedná o [modul plug-in založený na panelu nástrojů](../additional-development-options/creating-a-toolbar-based-plugin.md) nebo [modul plug-in založený na panelu HTML](../additional-development-options/creating-an-html-panel-plugin.md) má další vlastnosti.

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

Typický modul plug-in obsahuje tyto vlastnosti JSON:

* „PluginName“ představuje název modulu plug-in pro interní účely a většinu zobrazovacích účelů, včetně nástroje [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager).
* „PluginType“ představuje typ modulu plug-in, který uživatelům v popisu v nástroji [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) umožňuje zjistit, na co se mají při instalaci modulu plug-in zaměřit.
* „PluginDescription“ se zobrazuje v okně nástroje [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) a informuje o možnostech modulu plug-in.
* „Scripts“ uvádí požadované externí skripty přidružené k modulu plug-in, které budou načteny do aplikace FormIt a mohou být spuštěny při vyvolání funkce modulu plug-in.

![](<../../../.gitbook/assets/image (5) (1).png>)

Vývoj modulu plug-in začněte vytvořením souboru manifest.json ve složce modulu plug-in. Dále se musíte rozhodnout, zda vytváříte modul plug-in panelu nástrojů nebo panelu.

![](<../../../.gitbook/assets/image (36).png>)

**Poznámka:** Použití parametru PLUGINLOCATION ve výše uvedeném souboru manifest.json je nezbytné a jsou rozlišována malá a velká písmena. Aplikace FormIt nahradí parametr PLUGINLOCATION umístěním serveru pro modul plug-in.
