# Generate String Lights (Generuj ciągi świateł)

_W tym rozdziale omówimy kilka przykładowych wtyczek dostarczanych z programem FormIt, aby wprowadzić ulepszenia w modelu_ _**Encode Campus Sample Model.axm**. Jeśli jeszcze nie zostało to zrobione, możesz pobrać plik z zestawu danych_ [_FormIt Primer Part II DataSet_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip)__

_Ta świetna wtyczka umożliwia szybkie dodawanie do modelu wiszących świateł na podstawie linii lub krzywej._

1 — Przed dodaniem jakichkolwiek nowych świateł sprawdźmy zamierzony rezultat, używając wstępnie przygotowanej sceny w modelu.

1. Aby przejść do sceny zawierającej istniejące ciągi świateł, otwórz **paletę Sceny** i kliknij dwukrotnie scenę o nazwie **Eye Level – Short Alley** \(Poziom wzroku — Krótka uliczka\).
2. Zwróć uwagę na ciąg świateł, który pojawił się w tym modelu — zamierzamy go odtworzyć, ale w innym miejscu.
3. Na **palecie Warstwy** włącz warstwę **Helper Geometry** \(Geometria pomocnicza\), aby wyświetlić oryginalne linie użyte do wygenerowania tego ciągu świateł.

![](<../../.gitbook/assets/3 (10).png>)

2 — Teraz przejdźmy do drugiej uliczki i dodajmy trochę świateł. W **palecie Sceny** otwórz scenę **Eye Level – Long Alley** \(Poziom wzroku — Długa uliczka\). Zwróć uwagę, że w tej uliczce nie ma jeszcze żadnego ciągu świateł.

3 — Aby utworzyć nowy ciąg świateł:

1. Otwórz nowo zainstalowaną **paletę Generate String Lights** \(Generuj ciągi świateł\), klikając ikonę ciągu świateł. Domyślnie ikony nowych wtyczek są wyświetlane u dołu.
2. Zmień opcję **Number of Fixtures** \(Liczba opraw\) na **10**.
3. Kliknij dwukrotnie jedną z linii pomocniczych, aby przeprowadzić edycję wstępnie utworzonej grupy **String Lights – Long Alley** \(Ciąg świateł — Długa uliczka\). Następnie kliknij jedną ze wstępnie narysowanych linii pomocniczych, aby ją zaznaczyć.
4. Kliknij przycisk **Generate String Lights** \(Generuj ciąg świateł\) znajdujący się w palecie wtyczki. Powinien pojawić się nowy ciąg świateł. Pamiętaj, że każdy ciąg świateł jest tworzony jako osobna, niepowtarzalna grupa.

![](<../../.gitbook/assets/4 (6) (1).png>)

_**Uwaga:**_ _niektóre linie przechodzą przez znak „Groove Coffee”, ponieważ wtyczka ciągu świateł tworzy krzywą łańcucha, która będzie realistycznie zwisać pod znakiem._

4 — Spróbuj utworzyć więcej ciągów świateł, używając innej wstępnie utworzonej linii pomocniczej i/lub utworzyć kilka własnych linii pomocniczych. Pobaw się ustawieniami wtyczki, aby uzyskać różne wyniki.

5 — Aby ułatwić zachowanie porządku w modelu, po zakończeniu zalecamy zgrupowanie wszystkich linii pomocniczych i umieszczenie tej grupy w warstwie **Helper Geometry** \(Geometria pomocnicza\), jak również przypisanie wszystkich grup ciągów świateł do warstwy **Context – Exterior Lighting** \(Kontekst — Oświetlenie zewnętrzne\). Zapobiegnie to wyświetlaniu linii pomocniczych we wszystkich scenach „Eye Level” \(Poziom wzroku\), w których nie chcemy ich widzieć. Po zakończeniu wyniki powinny wyglądać podobnie jak na następnym zrzucie ekranu.

![](<../../.gitbook/assets/5 (3) (1).png>)

_**Uwaga:**_ _w odróżnieniu od geometrii utworzonej ze skryptu Dynamo, którą można zaktualizować i wygenerować ponownie za pomocą_ _**palety Właściwości**, obiekty utworzone przez wtyczkę to (przeważnie) zwykła geometria programu FormIt. Po utworzeniu można je edytować tylko za pomocą narzędzi modelowania wbudowanych w programie FormIt._
