# Ladění

Ladění modulu plug-in FormIt vyžaduje různé postupy v závislosti na modulu, který ladíte. (Další informace o modulech naleznete v [předchozí části](client-side-vs-web-side-engines.md))

### **Ladění na straně klienta (FormIt)**

Chcete-li ladit kód na straně aplikace FormIt, což platí pro moduly plug-in panelů nástrojů i moduly plug-in panelů, můžete do kódu přidat řádek, který spustí vestavěný ladicí program JS počítačové aplikace:

`debugger`

![](../../../.gitbook/assets/debugger.gif)

### **Ladění na straně webu (HTML)**

Moduly plug-in panelů aplikace FormIt nabízejí ladění uživatelského rozhraní založené na jazyce HTML, protože panely jsou v podstatě webové stránky HTML se styly a skripty.

Ladění kódu HTML pro moduly plug-in panelů, včetně skriptů a stylů:

* **Aplikace FormIt pro systém Windows 2021.1 a novější**
   * Klikněte pravým tlačítkem na stránku HTML modulu plug-in a kliknutím na položku Debug (Ladit) zobrazte vestavěný ladicí program HTML aplikace FormIt.

![](../../../.gitbook/assets/debugpanelplugin.gif)

* **FormIt pro web**
   * Pomocí klávesové zkratky F12 nebo Ctrl+Shift+I spusíte ladicí program HTML v prohlížeči.

![](../../../.gitbook/assets/debugonweb.gif)

