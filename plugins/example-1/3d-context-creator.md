# Kreator kontekstu 3D

\![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## Co to jest?

3D Context Creator to bardzo łatwa w użyciu wtyczka, która pomaga wygenerować kontekst 3D budynków w programie FormIt. 

Wtyczka ta ułatwia wizualizację terenu projektu z otaczającym go kontekstem i podejmowanie świadomych decyzji na wczesnym etapie procesu projektowania.

Ta wtyczka pobiera dane z usługi [Open Street Map](https://www.openstreetmap.org/about), aby ułatwić przekształcenie ich w geometrie programu FormIt. Kod źródłowy tej wtyczki jest dostępny w serwisie [Github](https://github.com/matterlab-co/FormIt-Context-Plugin).

## Sposób korzystania

Aby zainstalować tę wtyczkę, wystarczy włączyć jej przełącznik w narzędziu Plugin Manager, tak jak w przypadku każdej innej wtyczki.

![](../../.gitbook/assets/contextcreator3.png)

Po włączeniu wtyczki za pomocą przełącznika powinna ona być widoczna po prawej stronie aplikacji i gotowa do użycia.

\![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

Jeśli teren nie ma jeszcze położenia, można kliknąć link **Ustaw położenie...**, aby ustawić położenie i zdefiniować obwiednię, która zostanie użyta do wygenerowania kontekstu 3D.

Po ustawieniu położenia wtyczka 3D Context Creator wykona aktualizację z uwzględnieniem bieżącego położenia i przycisk zostanie włączony:

\![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

Wtyczka 3D Context Creator użyje po prostu zakresu obrazu satelitarnego do wygenerowania kontekstu 3D. Wystarczy kliknąć przycisk **Generate 3D Context** (Generuj kontekst 3D).

Generowanie może potrwać kilka sekund w zależności od zakresu obrazu satelitarnego i złożoności budynków.

Budynki kontekstowe 3D zostaną automatycznie umieszczone w wystąpieniu grupy i umieszczone na warstwie o nazwie „Context Buildings” (Budynki kontekstowe). Widoczność kontekstu można przełączać za pomocą tej warstwy.

\![](<../../.gitbook/assets/3D Context Creator_layers.png>)

\![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

Jeśli później zdecydujesz się na zmianę położenia lub dopasujesz zakres obrazu satelitarnego, możesz ponownie kliknąć opcję **Generate 3D Context** (Generuj kontekst 3D), aby ponownie wygenerować budynki. 

_Uwaga: ponowne wygenerowanie kontekstu spowoduje zastąpienie wystąpienia grupy zawierającego budynki nowym wystąpieniem, więc wszystkie zmiany wprowadzone w budynkach zostaną utracone._ Aby temu zapobiec, można rozgrupować kontener kontekstu, a następnie ponownie go zgrupować.

## **Kilka przykładów**

Spróbuj zgadnąć, jakie znane miasta są reprezentowane w następujących kontekstach:

\![](<../../.gitbook/assets/image (2) (1).png>)

\![](<../../.gitbook/assets/image (34).png>)

\![](<../../.gitbook/assets/image (13) (1) (1).png>)

\![](<../../.gitbook/assets/image (59).png>)
