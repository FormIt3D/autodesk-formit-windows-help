# Testowanie wtyczki stanowiącej połączenie panelu HTML i paska narzędzi

Wbudowany [Edytor skryptów](../advanced-development/setting-up-formit-for-development.md) w programie FormIt dla systemu Windows pozwala łatwo testować wtyczki podczas ich opracowywania

Zalecamy używanie podczas testowania polecenia `FormIt.LoadPlugin("URL");`, które tymczasowo wczytuje wtyczki na czas danej sesji (znikną one po ponownym uruchomieniu programu FormIt).&#x20;

Po zakończeniu testowania można utrwalić wtyczkę między sesjami, używając polecenia `FormIt.InstallPlugin("URL");`.

**Program FormIt dla systemu Windows w wersji 17 i nowszych**

****

### **Wtyczki paska narzędzi**

Wczytaj wtyczkę do programu FormIt, aby wyświetlić najnowszy interfejs użytkownika i przetestować najnowsze funkcje:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Wprowadź zmiany, a następnie ponownie wczytaj wtyczkę, używając polecenia powyżej.

W bieżącej sesji można wczytać wiele wystąpień tej samej wtyczki, każde z własnym interfejsem użytkownika, na potrzeby testowania.

Upewnij się, że testujesz najnowsze zmiany, korzystając z najnowszego wystąpienia interfejsu użytkownika.



### **Wtyczki panelu HTML**

Wczytaj wtyczkę do programu FormIt, aby wyświetlić najnowszy interfejs użytkownika i przetestować najnowsze funkcje:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Wprowadź zmiany, a następnie kliknij prawym przyciskiem myszy panel i wybierz opcję „Twarde ponowne wczytanie”, aby ponownie wczytać panel z najnowszymi skryptami HTML, CSS i HTML.

****

### **Wyświetlanie podglądu wtyczki za pomocą narzędzia Plugin Manager**

Po wczytaniu wtyczki zapoznaj się z [wcześniejszym rozdziałem](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md) tego podręcznika.

****

### **Wymuszanie wyczyszczenia internetowej pamięci podręcznej dla plików .JSON**

Jeśli zmodyfikujesz tytuł lub opis w pliku manifest.json dla wtyczki lub repozytorium, konieczne może być wymuszenie wyczyszczenia pamięci podręcznej w programie FormIt dla systemu Windows, aby te zmiany odniosły skutek przy następnym ponownym wczytywaniu narzędzia Plugin Manager.

Program FormIt dla systemu Windows przechowuje internetową pamięć podręczną w tym miejscu. Aby wyświetlić folder AppData, należy włączyć elementy ukryte w Eksploratorze Windows.

* C:\Users\user\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

Aby usunąć internetową pamięć podręczną, wystarczy usunąć folder „Default” (Domyślny) powyżej, a następnie ponownie wczytać narzędzie Plugin Manager w celu wyświetlenia zaktualizowanych tytułów i opisów.
