# Nastavení aplikace FormIt pro vývoj

Chcete-li testovat a vytvářet moduly plug-in v počítačové aplikaci FormIt, budete potřebovat aplikaci FormIt pro systém Windows verze 17.0 nebo novější.

### **Zobrazení panelů Editor skriptů a Výstup skriptu**

V horní nabídce aplikace FormIt přejděte do nabídky **Okno** a zaškrtněte políčka **Editor skriptů** a **Výstup skriptu**.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

V dolní části okna aplikace FormIt se zobrazí panely Editor skriptů a Výstup skriptu.

Mezi panely Editor skriptů a Výstup skriptu můžete přepínat pomocí tlačítek v dolní části.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

Můžete také uspořádat oba panely vedle sebe. Kliknutím na tlačítko vedle tlačítka „x“ v pravém horním rohu odpojte jeden z panelů a poté přetáhněte panely vedle sebe:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **Editor skriptů**

Editor skriptů poskytuje jednoduché vývojové prostředí pro psaní a testování kódu.

Editor skriptů ukládá napsaný kód do souboru scratch.js v adresáři, v němž je umístěn soubor FormIt.exe.

Nahoře jsou dvě tlačítka:

**Spustit** \![](<../../../.gitbook/assets/image (8) (1).png>): Spustí veškerý kód zapsaný v okně.

**Spustit výběr** \![](<../../../.gitbook/assets/image (52).png>): Spustí pouze vybrané/zvýrazněné řádky kódu.

### **Výstup skriptu**

Okno Výstup skriptu zobrazuje všechny zprávy vypsané do konzoly z modulů plug-in.

Výstup můžete vymazat spuštěním příkazu `console.clear();` v Editoru skriptů.

## Práce se vzorovými moduly plug-in

Po [klonování úložiště](cloning-a-sample-plugin.md) a [nastavení webového serveru](hosting-a-plugin-on-a-local-server.md) můžete nyní v aplikaci FormIt zobrazit místní moduly plug-in.

Můžete načíst nebo nainstalovat kterýkoli z modulů plug-in, ale pro účely tohoto cvičení budete instalovat jak modul plug-in založený na panelu, tak modul plug-in založený na panelu nástrojů. Budeme předpokládat, že váš npm http-server běží na portu 8080 a hostuje obě vzorová úložiště.

### Příkazy **Load vs. Install**

Příkaz `FormIt.LoadPlugin();` načte modul plug-in pouze pro aktuální relaci. Modul plug-in bude automaticky uvolněn při ukončení a restartování aplikace.

Jedná se o skvělou možnost, jak dočasně zobrazit modul plug-in pro účely testování pouze v aktuální relaci.

Příkaz `FormIt.InstallPlugin();` zajistí, že modul plug-in zůstane zachován pomocí klíče registru. Jedná se o vhodnou volbu pro moduly plug-in, které budete často používat v různých relacích.

V systému Windows se k zachování modulů plug-in používají následující klíče registru:

* Plugins: Computer\\HKEY_CURRENT_USER\\Software\\Autodesk\\FormIt 360\\Plugins\\InstalledPlugins

K odinstalaci použijte příkaz `FormIt.UninstallPlugin();`.

Pokud není uvedeno jinak, v následujících příkladech můžete použít příkaz _Install_ nebo _Load_ podle toho, zda chcete, aby výsledky cvičení byly trvalé nebo nikoli.

### **Vzorový modul plug-in panelu nástrojů: Flip Along**

V Editoru skriptů spusťte následující příkaz:

Pokud používáte místní server:

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

Pokud se modul plug-in načítá z úložiště služby [FormIt GitHub](https://github.com/FormIt3D/) (nutné připojení k internetu):

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

V horní části okna aplikace by se měl zobrazit panel nástrojů Flip Along:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **Vzorový modul plug-in panelu HTML: Properties Plus**

V Editoru skriptů spusťte následující příkaz:

Pokud používáte místní server:

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

Pokud se modul plug-in načítá z úložiště služby [FormIt GitHub](https://github.com/FormIt3D/) (nutné připojení k internetu):

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

V pravé části okna aplikace by se měl zobrazit panel Properties Plus:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **Vzorový modul plug-in modálního a nemodálního dialogu**

Moduly plug-in dialogu jsou jedinečné: lze je pouze načíst, nelze je instalovat.

V Editoru skriptů spusťte následující příkaz:

Pokud používáte místní server:

* Modální: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* Nemodální: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

Pokud se modul plug-in načítá z úložiště služby [FormIt GitHub](https://github.com/FormIt3D/) (nutné připojení k internetu):

* Modální: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* Modální: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

Panel Hello Block! z příkladu panelu HTML by se měl zobrazit na obrazovce jako modální nebo nemodální dialog.
