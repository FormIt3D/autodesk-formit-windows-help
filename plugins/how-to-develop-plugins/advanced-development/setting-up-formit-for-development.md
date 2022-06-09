# Konfigurowanie programu FormIt pod kątem programowania

Aby testować i opracowywać wtyczki w aplikacji komputerowej FormIt, należy używać programu FormIt dla systemu Windows w wersji 17.0 lub nowszej.

### **Wyświetlanie edytora skryptów i wyniku skryptu**

W programie FormIt przejdź do pozycji **Okno** w górnym menu i zaznacz pola wyboru **Edytor skryptów** oraz **Wynik skryptu**.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

W dolnej części okna programu FormIt zostaną wyświetlone panele Edytor skryptów i Wynik skryptu.

Używając przycisków u dołu, możesz przełączać się między panelami Edytor skryptów i Wynik skryptu.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

Możesz również rozmieścić oba panele obok siebie. Kliknij przycisk obok znaku „x” w prawym górnym rogu, aby odłączyć jeden z paneli, a następnie przeciągnij i upuść panele obok siebie:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **Edytor skryptów**

Edytor skryptów zapewnia proste środowisko programistyczne, w którym można pisać i testować kod.

Edytor skryptów przechowuje zapisany kod w pliku scratch.js w katalogu, w którym znajduje się plik FormIt.exe.

W górnej części znajdują się dwa przyciski:

**Uruchom** ![](<../../../.gitbook/assets/image (8).png>): wykonuje cały kod napisany w oknie.

**Uruchom wybór** ![](<../../../.gitbook/assets/image (52).png>): wykonuje tylko wybrane/wyróżnione wiersze kodu.

### **Wynik skryptu**

W oknie Wynik skryptu wyświetlane są wszystkie komunikaty drukowane z wtyczek w konsoli.

Te dane wyjściowe można usunąć, uruchamiając polecenie `console.clear();` w Edytorze skryptów.

## Praca z przykładowymi wtyczkami

Po [sklonowaniu repozytorium](cloning-a-sample-plugin.md) i [skonfigurowaniu serwera internetowego](hosting-a-plugin-on-a-local-server.md) można teraz wyświetlić wtyczki lokalne w programie FormIt.

Można wczytać lub zainstalować dowolne wtyczki, ale w ramach tego ćwiczenia zostanie zainstalowana zarówno wtyczka oparta na panelu, jak i na pasku narzędzi. Załóżmy, że serwer http-server programu npm działa na porcie 8080. Są w nim hostowane oba repozytoria przykładowe.

### **Wczytywanie a instalowanie**

`FormIt.LoadPlugin();` wczytuje wtyczkę tylko na potrzeby bieżącej sesji. Wtyczka zostanie automatycznie usunięta z pamięci po zamknięciu i ponownym uruchomieniu aplikacji.

Jest to doskonała opcja do tymczasowego wygenerowania wtyczki na potrzeby testowania tylko w bieżącej sesji.

`FormIt.InstallPlugin();` utrwala wtyczkę przy użyciu klucza rejestru. Jest to przydatne w przypadku wtyczek, które będą często używane w kolejnych sesjach.

W systemie Windows do utrwalania wtyczek są używane następujące klucze rejestru:

* Plugins: Computer\HKEY\_CURRENT\_USER\Software\Autodesk\FormIt 360\Plugins\InstalledPlugins

Użyj opcji `FormIt.UninstallPlugin();`, aby odinstalować.

W poniższych przykładach, o ile nie zaznaczono inaczej, można używać opcji _zainstalowania_ lub _wczytania_ w zależności od tego, czy wyniki ćwiczenia mają być trwałe.

### **Przykład wtyczki paska narzędzi: Flip Along (Odwróć wzdłuż)**

W Edytorze skryptów uruchom następujące polecenie:

W przypadku serwera lokalnego:

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

W przypadku wczytywania z [repozytorium GitHub programu FormIt](https://github.com/FormIt3D/) (wymagane jest połączenie z Internetem):

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

Pasek narzędzi Flip Along (Odwróć wzdłuż) powinien pojawić się w górnej części okna aplikacji:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **Przykład wtyczki panelu HTML: Properties Plus (Właściwości plus)**

W Edytorze skryptów uruchom następujące polecenie:

W przypadku serwera lokalnego:

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

W przypadku wczytywania z [repozytorium GitHub programu FormIt](https://github.com/FormIt3D/) (wymagane jest połączenie z Internetem):

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

Panel Properties Plus (Właściwości plus) powinien pojawić się po prawej stronie okna aplikacji:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **Przykład wtyczki modalnego i niemodalnego okna dialogowego**

Wtyczki okien dialogowych są unikatowe: można je tylko wczytać, nie można ich zainstalować.

W Edytorze skryptów uruchom następujące polecenie:

W przypadku serwera lokalnego:

* Modalne: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* Niemodalne: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

W przypadku wczytywania z [repozytorium GitHub programu FormIt](https://github.com/FormIt3D/) (wymagane jest połączenie z Internetem):

* Modalne: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* Modalne: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

Na ekranie powinien pojawić się panel Hello Block! z przykładu panelu HTML jako modalne lub niemodalne okno dialogowe.
