# Hostowanie wtyczki na serwerze lokalnym

Zanim będzie można wyświetlić podgląd sklonowanej wtyczki w programie FormIt, należy umieścić ją jako hostowaną na serwerze lokalnym.

### **Wyświetlanie terminala w środowisku IDE**

Istnieje możliwość uruchomienia serwera w programie Visual Studio Code zamiast w oddzielnym oknie terminala. **** Przed otwarciem terminala upewnij się, że w programie Visual Studio Code jest otwarty właściwy folder.

Widok > Terminal (lub skrót Ctrl + \`)

![](<../../../.gitbook/assets/image (11) (1).png>)

### Konfigurowanie serwera HTTP

Serwer HTTP, który działa poprawnie, to serwer [http-server](https://www.npmjs.com/package/http-server) programu npm.

Najpierw należy pobrać i zainstalować [środowisko NodeJS](https://nodejs.org/en/), jeśli nie zostało jeszcze zainstalowane.

W przypadku wystąpienia błędów w kolejnych punktach spróbuj ponownie uruchomić komputer, aby ukończyć instalację środowiska NodeJS.

W wierszu polecenia wprowadź następujące wartości, aby zainstalować globalnie _http-server_ programu npm (konfiguracja jednorazowa).

* `npm install http-server -g`

![](<../../../.gitbook/assets/image (47).png>)

### Uruchamianie serwera licencji

Po ukończeniu instalacji uruchom następujące polecenie w terminalu, aby uruchomić serwer npm http-server:

* `http-server`

![](<../../../.gitbook/assets/image (84).png>)

Wskazówka 1: w przypadku problemów z uruchomieniem serwera http-server (zainstalowanego globalnie lub lokalnie) może być przydatne uruchomienie go bezpośrednio za pośrednictwem serwera npx:

* `npx http-server`

Wskazówka 2: w przypadku użytkowników systemu Windows 10/11, jeśli wystąpi błąd podczas uruchamiania skryptu na nowym komputerze, może to być spowodowane wyłączeniem ustawień. Aby to naprawić:

* Uruchom skrypt programu PowerShell jako administrator
* Wprowadź: `Set-ExecutionPolicy RemoteSigned`

### Programowanie dla wersji internetowej programu FormIt

Aby zaprogramować rozwiązanie dla wersji internetowej programu FormIt, zamiast tego należy po prostu uruchomić następujące polecenie:

* `http-server --cors`

![](<../../../.gitbook/assets/image (10) (1).png>)

### Weryfikowanie serwera

Możesz zweryfikować swój serwer, przechodząc do następującego adresu w przeglądarce internetowej:

* http://localhost:8080

Pliki folderu projektu powinny być widoczne w oknie przeglądarki.

**Jeśli używany jest serwer internetowy inny niż npm, domyślny adres/port może być inny.

![](<../../../.gitbook/assets/image (41).png>)
