---
opis: >- 
  Rozpocznij proces roboczy BIM, oceniając wydajność elementów od początku procesu projektowania.
---

# Analiza oświetlenia naturalnego i analiza energetyczna

\![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## Analiza energetyczna w programie FormIt

Analizuj model budynku pod kątem wydajności energetycznej na wczesnym etapie procesu projektowania.

[Wyświetlanie projektów usługi Insight](https://gbs.autodesk.com/OneEnergy/Insight)

## Analiza energetyczna w usłudze Insight

W ramach subskrypcji programu **FormIt Pro** dostępnej za pośrednictwem [kolekcji z zakresu architektury, inżynierii i budownictwa (AEC)](https://www.autodesk.com/collections/architecture-engineering-construction/overview) masz dostęp do analizy energetycznej w usłudze **Insight**:

* Analizuj wczesne etapy modeli projektowych za pomocą aparatu analitycznego programu Green Building Studio
* Połącz się z widokiem panelu nawigacyjnego wyników analizy, aby porównać opcje dostępne dla projektu
* Dopasuj widżety współczynników analizy energetycznej, takich jak stosunek powierzchni okna do ściany, orientacji budynku i innych
* Podsumuj wpływ energetyczny na budynek za pomocą jednej wartości liczbowej obliczanej jako koszt końcowy na powierzchnię
* Zapisz wyniki analizy energetycznej w celu późniejszego przejrzenia ich wspólnie z klientami i innymi interesariuszami

## Co nowego w połączeniu produktów FormIt + Insight <a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Ulepszenia niezawodności usługi Insight** <a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* Program [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) sprawdza teraz model pod kątem typowych problemów z modelem przed uruchomieniem usługi Insight i naprawia typowe błędy usługi Insight, aby zapewnić bardziej niezawodne środowisko.
* Program FormIt 2021 zwykle zwiększa również niezawodność połączenia FormIt + Insight, rozwiązując problemy z wieloma znanymi awariami i poprawiając wskaźniki pomyślnych przebiegów.

## Pierwsze kroki <a href="#insight-getting-started" id="insight-getting-started"></a>

### **Zasada działania** <a href="#how-it-works" id="how-it-works"></a>

* Funkcja analizy energetycznej usługi Insight przesyła dane modelu FormIt i w chmurze wykonuje kilkaset analiz w celu określenia różnych wyników energetycznych
* Funkcja analizy energetycznej używa programu Revit do analizy modelu, więc tak samo jak podczas wysyłania danych programu FormIt do programu Revit należy [upewnić się, że model programu FormIt jest szczelny i rozgałęziony](https://formit.autodesk.com/blog/post/repairing-solid-models)

### **Przygotowanie modelu programu FormIt** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Usługa Insight użyje całej widocznej geometrii w szkicu programu FormIt
  * Upewnij się, że powłoka budynku, która ma być analizowana, jest jedyną widoczną geometrią
  * Umieść geometrię pomocniczą, taką jak elementy otoczenia, mebli i terenu, na osobnej [warstwie](../tool-library/layers.md) i wyłącz tę warstwę
* Usługa Insight działa najlepiej w przypadku prostego, jednolitego modelu budynku
  * Upewnij się, że bryła budynku jest [szczelna i bryłowa](https://formit.autodesk.com/blog/post/repairing-solid-models)
  * Jeśli projekt budynku zawiera już otwory na okna i drzwi, najlepiej utworzyć nową bryłę bez otworów przeznaczoną specjalnie do analizy energetycznej i ukryć bardziej szczegółową wersję za pomocą warstw
* Ta prosta bryła budynku musi mieć zastosowane [poziomy](../tool-library/levels-and-area.md)
* Model programu FormIt musi mieć ustawione [położenie](../tool-library/setting-location.md)

![](../.gitbook/assets/insight.png)

### **Uruchamianie analizy energetycznej** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* Odszukaj przycisk Analiza energetyczna na pasku narzędzi

![](../.gitbook/assets/generate\_insight.png)

* Kliknij opcję „Generuj Insight”, aby rozpocząć proces
* Spowoduje to przekazanie widocznych danych modelu i uruchomienie kilkuset symulacji w chmurze
* Po zakończeniu u góry ekranu zostanie wyświetlony komunikat, a menu zostanie zaktualizowane, co oznacza, że nowa analiza Insight jest gotowa do wyświetlenia
  * Kliknij opcję „Wyświetl Insight”, aby wyświetlić analizę w przeglądarce internetowej
  * Wszystkie analizy Insight można również znaleźć w witrynie [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight).

## Rozwiązywanie problemów <a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **Typowe błędy** <a href="#common-errors" id="common-errors"></a>

* „Nie można utworzyć projektu Insight. Należy ponowić próbę później”.
  * Zaloguj się na [pulpicie nawigacyjnym Green Building Studio](https://gbs.autodesk.com/GBS/Project), a następnie uruchom ponownie program FormIt
    * Jeśli nie możesz się zalogować lub jeśli widzisz stronę „odmowa dostępu”, może być konieczne [zakupienie subskrypcji Green Building Studio](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/ENU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html)
  * Upewnij się, że model jest [szczelny i bryłowy](https://formit.autodesk.com/blog/post/repairing-solid-models)
  * Sprawdź, czy nie występują problemy z usługami FormIt, na [pulpicie nawigacyjnym kondycji usług Autodesk](https://health.autodesk.com/)
* Aby sprawdzić, czy program Green Building Studio pomyślnie wykonał analizę energetyczną dla tego projektu, sprawdź [pulpit nawigacyjny Green Building Studio](https://gbs.autodesk.com/GBS/Project)
  * Najnowszy projekt powinien być wyświetlany u góry listy i powinna być dla niego podana liczba 248 przebiegów
  * Jeśli zostanie wyświetlona liczba 0 przebiegów, [poinformuj nas o tym na forach programu FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142), abyśmy mogli pomóc w kontynuowaniu rozwiązywania problemów

### **Dzienniki szczegółowe** <a href="#detailed-logs" id="detailed-logs"></a>

* W przypadku niepowodzenia analizy energetycznej aplikacja internetowa programu FormIt zapewnia dodatkowe informacje:
  * Przejdź do [aplikacji internetowej FormIt](https://formit.autodesk.com/app)
  * Otwórz model, w którym występują problemy z analizą energetyczną
  * Uruchom analizę energetyczną
  * Otwórz narzędzia programistyczne (naciśnij klawisz F12 w przeglądarce Google Chrome lub Firefox)
  * Sprawdź kartę Console (Konsola)
  * Skopiuj wszelkie błędy lub utwórz ich zrzuty ekranu i [zgłoś je na forach programu FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142)

## Analiza oświetlenia naturalnego

W ramach subskrypcji programu **FormIt Pro** dostępnej za pośrednictwem [kolekcji z zakresu architektury, inżynierii i budownictwa (AEC)](https://www.autodesk.com/collections/architecture-engineering-construction/overview) możesz wizualizować wpływ słońca na budynek:

* Określ odpowiednie powierzchnie do analizy pod kątem wpływu oświetlenia naturalnego
* Wizualizuj wyniki w ciągu sekund w obszarze rysunku aplikacji
* Umieść wskaźnik myszy na punkcie danych wejściowych, aby wyświetlić konkretne obliczone wartości wpływu oświetlenia naturalnego
* Wybierz opcję wyświetlania wyników w formie miesięcznego badania przeszklenia lub rocznego badania wykonalności paneli słonecznych

Dowiedz się więcej na temat [analizy oświetlenia naturalnego](../tool-library/solar-analysis.md) w programie FormIt Pro.
