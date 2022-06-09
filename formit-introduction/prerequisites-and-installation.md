# Wymagania wstępne i instalacja

## Pobieranie i instalacja

* Pobierz najnowszą wersję programu [FormIt dla systemu Windows](https://formit.autodesk.com/page/download).
* Zaloguj się na koncie Autodesk lub [utwórz bezpłatne konto Autodesk tutaj](https://accounts.autodesk.com).
* Dodatek FormIt dla programu Revit jest dołączony do programu Revit 2017 i nowszych wersji. Dodatek ten można również pobrać i ręcznie zainstalować z naszej witryny[https://formit.autodesk.com/page/formit-revit]().

Ustawienia poziomu aplikacji dla programu FormIt znajdują się w ścieżce Computer\HKEY\_CURRENT\_USER\SOFTWARE\Autodesk\FormIt 360\\

## Zalecana konfiguracja systemu

| Wymaganie | Szczegóły |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **System operacyjny** | <p>Microsoft® Windows® 8, 8.1, 10 lub 11.</p><p><em>Uwaga: narzędzie Parallels Desktop nie jest oficjalnie obsługiwane z powodu pogorszenia się wydajności i problemów z grafiką w przypadku sterowników OpenGL.</em></p> |
| **Procesor** | <p>Procesor Intel® Pentium®, Xeon® lub i-Series albo równoważny procesor AMD® z technologią SSE2.</p><p>Zaleca się stosowanie najwyższej rzeczywistej prędkości procesora.</p> |
| **Pamięć** | Co najmniej 4 GB pamięci RAM, zalecane 8 GB lub więcej. |
| **Karta graficzna (GPU)** | <p>Wymagana jest osobna karta graficzna NVIDIA lub AMD obsługująca technologię OpenGL 3.3. Zdecydowanie zaleca się obsługę technologii OpenGL 4.2.</p><p>Na potrzeby zapewnienia najlepszej wydajności w przypadku systemów z przełączalnymi kartami wideo należy postępować zgodnie z instrukcjami producenta w celu zadbania o to, aby program FormIt zawsze używał dedykowanego procesora graficznego. Zobacz instrukcje dotyczące kart <a href="https://www.amd.com/en/support/kb/faq/dh-017">AMD</a> i <a href="http://nvidia.custhelp.com/app/answers/detail/a_id/2615/kw/manage%203d%20settings/related/1">NVIDIA</a>.</p><p>Aby uzyskać najlepszą wydajność i niezawodność, należy zadbać o aktualność sterowników karty wideo, korzystając z witryny internetowej producenta lub usługi Windows Update.</p><p>Jeśli nie będzie można użyć karty graficznej z powodu nieaktualnych sterowników lub innych problemów, podczas uruchamiania programu FormIt zostanie wyświetlony komunikat. Jeśli po aktualizacji sterowników nie można uruchomić programu FormIt, <a href="https://forums.autodesk.com/t5/formit-forum/bd-p/142">poproś o pomoc na forach</a>.</p> |
| **Miejsce na dysku twardym** | 1 GB wolnego miejsca na dysku. |
| **Łączność i licencjonowanie** | <p>Podczas pierwszego uruchomienia programu FormIt wymagane jest połączenie z Internetem w celu zalogowania się na koncie Autodesk.</p><p>Połączenie z Internetem jest również wymagane do wczytania wtyczek podczas uruchamiania programu FormIt. Jeśli podczas uruchamiania nie zostanie wykryte połączenie z Internetem, aplikacja zostanie uruchomiona bez wtyczek.</p><p>Do uruchomienia programu FormIt Pro w systemie Windows wymagane jest konto Autodesk z subskrypcją FormIt Pro w chmurze. Subskrypcja FormIt Pro jest zawarta w <a href="https://www.autodesk.com/collections/architecture-engineering-construction/overview"><strong>kolekcji Autodesk z zakresu architektury, inżynierii i budownictwa (Autodesk AEC Collection)</strong></a>.</p> |

## Dostęp w trybie offline

Przy pierwszym uruchomieniu programu FormIt dla systemu Windows wymagane jest połączenie z Internetem, aby można było zweryfikować licencję. Po pierwszym zalogowaniu się można używać aplikacji w trybie offline przez 30 dni. Po tym okresie należy przejść do trybu online, aby ponownie zweryfikować licencję.

Podczas korzystania z programu FormIt dla systemu Windows w trybie offline niektóre funkcje będą ograniczone:

* Narzędzie Ustaw lokalizację nie będzie działać, ponieważ wymaga połączenia z Internetem w celu pobrania danych satelitarnych i danych terenu z usługi Mapy Bing.
   * Jednak wszystkie już istniejące w modelu dane satelitarne i terenu z poprzedniej sesji online pozostaną.
* Wtyczki, w tym narzędzie Plugin Manager, nie zostaną wczytane, ponieważ przy każdym uruchomieniu aplikacji pobierają najnowszy kod z serwisu GitHub.
   * Obejście problemu: jeśli wczytasz wszystkie wtyczki w trybie online i przejdziesz w tryb offline, utrzymując działanie sesji programu FormIt, wczytane wcześniej wtyczki pozostaną i będą działać normalnie.
* Przykładowe materiały nie zostaną wczytane, ponieważ pochodzą z serwera hostowanego w chmurze.
   * Obejście problemu: przejdź do folderów kategorii materiałów przykładowych, gdy komputer ma połączenie z Internetem. Foldery zostaną pobrane i zapisane na komputerze użytkownika — będzie można uzyskać do nich dostęp później w trybie offline.
* Nie będzie można niczego zapisywać ani otwierać w usłudze Autodesk Docs, w tym w obrębie Biblioteki elementów.

## Zalecane ustawienia DPI systemu Windows

Program FormIt dla systemu Windows działa najlepiej, gdy dla wyświetlacza ekranu w systemie Windows ustawiono skalowanie DPI równe co najwyżej 125%.

W systemie Windows 10 można to zmienić, wykonując następujące czynności:

* W menu Start wyszukaj „ekran” i wybierz opcję „Zmień ustawienia ekranu”.
* Wybierz prostokąt reprezentujący monitor, który będzie używany z programem FormIt.
* W sekcji „Skala i układ” otwórz menu rozwijane „Zmień rozmiar tekstu, aplikacji i innych elementów” i wybierz wartość 125% lub mniejszą.

## Rozwiązywanie problemów

### Błąd systemu Windows 10 Pro N

W programie FormIt uruchomionym w systemie Windows 10 Pro N w wersji 1909 lub nowszej może zostać wyświetlony następujący komunikat o błędzie:

![FormIt.exe System Error on Windows 10](<../.gitbook/assets/windows 10 error message.png>)

Jest to spowodowane znanym problemem z niektórymi wersjami systemu Windows 10 Pro N. Aby uniknąć tego błędu, pobierz pakiet funkcji multimedialnych, Media Feature Pack, dla używanej wersji systemu Windows 10 stąd: [lista pakietów Media Feature Pack dla wersji systemu Windows N](https://support.microsoft.com/pl-pl/topic/lista-dodatku-media-feature-pack-dla-windows-n-c1c6fffa-d052-8338-7a79-a4bb980a700a).

### Nie można się zalogować

Podczas próby zalogowania się na koncie w programie FormIt okno dialogowe logowania może się zawiesić, co uniemożliwi kontynuowanie. W takim przypadku może być konieczne odblokowanie adresu \*.autodesk.com w zaporze sieciowej. Skontaktuj się z działem informatycznym swojej organizacji, aby uzyskać pomoc.
