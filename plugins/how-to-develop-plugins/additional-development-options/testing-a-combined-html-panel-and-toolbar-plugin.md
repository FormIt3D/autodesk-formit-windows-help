# Testování kombinovaného modulu plug-in panelu HTML a panelu nástrojů

Rozpracované moduly plug-in můžete snadno testovat pomocí vestavěného [Editoru skriptů](../advanced-development/setting-up-formit-for-development.md) v aplikaci FormIt pro systém Windows.

Při testování doporučujeme použít příkaz `FormIt.LoadPlugin("URL");`, který dočasně načte moduly plug-in pro danou relaci (po restartování aplikace FormIt moduly zmizí).&#x20;

Po dokončení testování můžete modul plug-in zachovat mezi relacemi příkazem `FormIt.InstallPlugin("URL");`.

**Aplikace FormIt pro systém Windows verze 17 a novější**

****

### **Moduly plug-in panelu nástrojů**

Načtěte modul plug-in do aplikace FormIt, abyste si mohli prohlédnout nejnovější uživatelské rozhraní a otestovat nejnovější funkce:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Proveďte nějaké změny a pak znovu načtěte modul plug-in pomocí výše uvedeného příkazu.

Při testování můžete v aktuální relaci načíst mnoho instancí stejného modulu plug-in, přičemž každá z nich bude mít vlastní uživatelské rozhraní.

Přesvědčte se, že používáte nejnovější instanci uživatelského rozhraní, abyste měli jistotu, že testujete nejnovější změny.



### **Moduly plug-in panelu HTML**

Načtěte modul plug-in do aplikace FormIt, abyste si mohli prohlédnout nejnovější uživatelské rozhraní a otestovat nejnovější funkce:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Proveďte nějaké změny, pak klikněte pravým tlačítkem myši na panel a vyberte položku Hard Reload. Tím panel znovu načtete s nejnovějšími kódy HTML, CSS a skripty.

****

### **Náhled modulu plug-in pomocí nástroje Plugin Manager**

Po načtení modulu plug-in si přečtěte [tuto kapitolu](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md) této příručky.

****

### **Vynucení vymazání webové vyrovnávací paměti pro soubory .JSON**

Pokud změníte název nebo popis v souboru manifest.json pro modul plug-in nebo úložiště, bude možná nutné vynutit vymazání vyrovnávací paměti v aplikaci FormIt pro systém Windows, aby se tyto změny projevily při příštím načtení nástroje Plugin Manager.

Aplikace FormIt pro systém Windows ukládá svou webovou vyrovnávací paměť v následujícím umístění. Chcete-li zobrazit složku AppData, bude nutné v Průzkumníku Windows povolit skryté položky.

* C:\Users\uživatel\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

Chcete-li odstranit webovou vyrovnávací paměť, jednoduše odstraňte složku „Default“ a poté znovu načtěte nástroj Plugin Manager, abyste viděli aktualizované názvy a popisy.
