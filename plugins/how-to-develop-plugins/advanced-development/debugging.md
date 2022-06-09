# Usuwanie błędów

Debugowanie wtyczki programu FormIt wymaga różnych procedur w zależności od debugowanego mechanizmu. (Aby uzyskać więcej informacji na temat mechanizmów, zapoznaj się z [poprzednią sekcją](client-side-vs-web-side-engines.md))

### **Debugowanie po stronie klienta (FormIt)**

Aby debugować w kodzie po stronie programu FormIt, co dotyczy zarówno wtyczek opartych na paskach narzędzi, jak i na panelach, można dodać wiersz w kodzie służący do wyświetlania wbudowanego debuggera JS aplikacji komputerowej:

`debugger`

![](../../../.gitbook/assets/debugger.gif)

### **Debugowanie po stronie WWW (HTML)**

Wtyczki programu FormIt oparte na panelach umożliwiają debugowanie interfejsu użytkownika opartego na kodzie HTML, ponieważ panele są zasadniczo witrynami HTML ze stylami i skryptami.

Debugowanie kodu po stronie HTML dla wtyczek wbudowanych w panel, wraz ze skryptami i stylizacją:

* **Program FormIt dla systemu Windows 2021.1 i nowsze wersje**
   * Kliknij prawym przyciskiem myszy stronę HTML wtyczki i kliknij pozycję Debuguj, aby wyświetlić wbudowany debuger HTML aplikacji.

![](../../../.gitbook/assets/debugpanelplugin.gif)

* **Wersja internetowa programu FormIt**
   * Użyj skrótu F12 lub kombinacji Ctrl + Shift + I, aby uruchomić debuger HTML przeglądarki.

![](../../../.gitbook/assets/debugonweb.gif)

