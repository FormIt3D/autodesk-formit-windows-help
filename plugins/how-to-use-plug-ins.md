# Jak używać wtyczek

![](<../.gitbook/assets/g3 (1).gif>)

## Narzędzie Plugin Manager

Narzędzie Plugin Manager programu FormIt to kompleksowy punkt obsługi do wyszukiwania wtyczek programu Formit i zarządzania nimi.

Narzędzie Plugin Manager jest wczytywane automatycznie podczas uruchamiania programu FormIt, o ile program FormIt ma dostęp do Internetu.

Dostęp do niego można uzyskać, klikając ikonę karty ![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PluginManagerTab.PNG) po prawej stronie aplikacji:

![](../.gitbook/assets/c1.PNG)

## Kategorie wtyczek

W narzędziu Plugin Manager wtyczki są zorganizowane w kategoriach, aby ułatwić użytkownikom znalezienie tych najbardziej ich interesujących.

![](../.gitbook/assets/d16.png)

**Installed Plugins (Zainstalowane wtyczki):** wtyczki już zainstalowane przez użytkownika.&#x20;

**Recommended Plugins (Zalecane wtyczki):** wtyczki zalecane przez zespół programu FormIt na potrzeby rozszerzenia podstawowych funkcji programu FormIt i udostępnienia nowych procesów roboczych. Po zatwierdzeniu przez zespół programu FormIt pojawiają się tutaj wtyczki opracowane przez społeczność.\
Oznaczenie GitHub: _formit-plugin-recommended_

**Public Plugins (Wtyczki publiczne):** wtyczki opracowane przez społeczność. Wtyczki w tej kategorii nie zostały zweryfikowane ani zatwierdzone przez zespół programu FormIt. \
Oznaczenie GitHub: _formit-plugin_

**For Developers Plugins (Wtyczki dla programistów)**: wtyczki opracowane przez społeczność w celu umożliwienia tworzenia nowych wtyczek programu FormIt. \
Oznaczenie GitHub: _formit-plugin-developers_

## Dodawanie wtyczki prywatnej lub lokalnej

Jeśli [tworzysz własną wtyczkę](how-to-develop-plugins/), możesz dodać jej prywatny adres URL w polu na dole i kliknąć (+):

![](../.gitbook/assets/d4.PNG)

Aby uzyskać więcej informacji na temat dodawania wtyczki prywatnej lub lokalnej, zobacz sekcję [Wyświetlanie podglądu wtyczki w narzędziu Plugin Manager. ](how-to-develop-plugins/advanced-development/previewing-a-plugin-in-the-plugin-manager.md)

## Resetowanie narzędzia Plugin Manager

Narzędzie Plugin Manager używa kluczy rejestru w systemie Windows do przechowywania zainstalowanych repozytoriów i wtyczek. Aby przywrócić domyślne ustawienia narzędzia Plugin Manager, należy usunąć następujący klucz rejestru:

`Computer\HKEY_CURRENT_USER\Software\Autodesk\FormIt 360\Plugins`

⚠️ Uwaga: należy pamiętać, że spowoduje to odinstalowanie wszystkich repozytoriów i wtyczek dodanych przez użytkownika, a więc zresetowanie narzędzia Plugin Manager do stanu, w którym będzie zawierać tylko wbudowane repozytoria i wtyczki.

## Instalowanie wtyczek

Narzędzie [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) zawiera wiele wtyczek zorganizowanych w różnych kategoriach. Każda wtyczka ma nazwę, opis, łącze GitHub i przełącznik instalacji.&#x20;

![](../.gitbook/assets/d5.PNG)

Aby zainstalować wtyczkę, wystarczy włączyć przełącznik obok jej nazwy.&#x20;

![](../.gitbook/assets/d6.png)

Ikona wybranej wtyczki zostanie wyświetlona w prawym panelu. Kliknij ją, aby wyświetlić interfejs użytkownika wtyczki.

![](../.gitbook/assets/d7.PNG)

## Używanie wtyczek

Każda wtyczka ma niepowtarzalny interfejs użytkownika zdefiniowany przez jej programistę. Wtyczka zazwyczaj ma zestaw instrukcji dotyczących sposobu korzystania z niej, zestaw parametrów (pola tekstowe, suwaki, pola wyboru itp.) oraz jeden lub więcej przycisków do jej wykonania.

Przykładowo użyjemy jednego z prostszych przykładów w narzędziu Plugin Manager: Fillet 2D Corners. Najpierw wczytujemy wtyczkę z sekcji polecanych w narzędziu Plugin Manager. Następnie, postępując zgodnie z instrukcjami programisty wtyczki, ustawiamy promień zaokrąglenia, wybieramy grupę powierzchni do zaokrąglenia i klikamy przycisk Fillet Corners (Zaokrąglij narożniki).

![](../.gitbook/assets/g4.gif)

##

