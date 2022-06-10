# Vytvoření modulu plug-in panelu nástrojů

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### Struktura souboru manifest.json modulu plug-in panelu nástrojů

Modul plug-in založený na panelu nástrojů má soubor _manifest.json_ s následující strukturou:

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

Kromě [standardních vlastností JSON](../advanced-development/general-plugin-setup-in-the-manifest.md) obsahuje modul plug-in panelu nástrojů tuto speciální vlastnost JSON:

* „ToolbarURL“ říká aplikaci FormIt, že tento modul plug-in je panel nástrojů a odkazuje na umístění jiného souboru JSON, který popisuje funkce panelu nástrojů.

### Konfigurace formátu panelu nástrojů pomocí souboru JSON

Po vytvoření souboru manifestu, jako je soubor popsaný výše, bude nutné vytvořit soubor toolbar.json, který definuje tlačítka panelu nástrojů, jejich názvy, text, ikony a funkci onClick přiřazenou k jednotlivým tlačítkům. Soubor JSON panelu nástrojů bude mít následující formát:

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

Soubor toolbar.json obsahuje tyto vlastnosti JSON:

* „name“ představuje název celkového panelu nástrojů a používá se interně k přidružení všech tlačítek k jediné nabídce panelu nástrojů.
* „buttons“ představují jednotlivá tlačítka přidaná uvnitř panelu nástrojů. Panel nástrojů může obsahovat libovolný počet tlačítek.
* „name“ definuje interní název tlačítka, který se používá k přiřazení tlačítka k panelu nástrojů a k funkci onClick tlačítka.
* „command“ definuje funkci tlačítka, která může být buď funkcí jazyka JavaScript (kterou lze definovat ve skriptu obsaženém v poli „Scripts“ v souboru manifest.json), nebo příkazem aplikace FormIt, například „Draw: Circle“ (Kreslit: Kružnice). Seznam příkazů aplikace FormIt lze získat spuštěním modulu plug-in Messages.
* „iconText“ nastaví popis nástroje a popisný text v tlačítku. Pokud není zadána adresa URL ikony, vytvoří se automaticky generovaná ikona z formátovaného textu.
* Nastavením vlastnosti „iconURL“ lze definovat vlastní ikonu tlačítka.

Po definování všech tlačítek v souboru toolbar.json je modul plug-in připraven k použití.&#x20;

Pokud chcete definovat další funkce jazyka JavaScript, přidejte je do stejné složky jako soubor manifest.json. Nezapomeňte přidat odkaz na soubor do pole „Scripts“ v souboru manifestu, aby aplikace FormIt mohla soubory najít.
