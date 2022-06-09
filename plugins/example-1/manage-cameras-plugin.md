# Wtyczka Manage Cameras \(Zarządzaj kamerami\)

_W tym rozdziale omówimy kilka przykładowych wtyczek dostarczanych z programem FormIt, aby wprowadzić ulepszenia w modelu_ _**Encode Campus Sample Model.axm**. Jeśli jeszcze nie zostało to zrobione, możesz pobrać plik z zestawu danych_ [_FormIt Primer Part II DataSet_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip)__

W tym przewodniku używaliśmy scen jako wartościowych narzędzi do nawigacji i sterowania widocznością w całym modelu. Ta wtyczka umożliwia wyświetlanie i edycję wysokości bieżącej kamery, eksportowanie kamer dla każdej sceny jako obiektów 3D i kopiowanie tych scen między modelami.

1 — Najpierw dostosujemy scenę **Eye Level – Long Alley** \(Poziom wzroku — Długa uliczka\) tak, aby jej kamera rzeczywiście znajdowała się na poziomie wzroku:

1. Jeśli scena **Eye Level – Long Alley** \(Poziom wzroku — Długa uliczka\) nie jest jeszcze wyświetlana, wróć do niej, klikając ją dwukrotnie w **palecie Sceny**.
2. Otwórz **paletę Manage Cameras** \(Zarządzaj kamerami\), klikając kamerę z ikoną koła zębatego.
3. Zmień wartość opcji **Height Above Ground** \(Wysokość nad ziemią\) na **5’-8”**.

![](<../../.gitbook/assets/6 (6) (1).png>)

_**Uwaga:**_ _jeśli model zawiera poziomy, ta wtyczka będzie również pokazywała wysokość nad najbliższym poziomem poniżej_ _**kamery głównej**._

2 — Następnie:

1. Wróć do **palety Sceny**.
2. Upewnij się, że scena **Eye Level — Long Alley** (Poziom wzroku — Długa uliczka) jest nadal zaznaczona (w przeciwnym razie kliknij raz, aby ją wybrać).
3. Kliknij przycisk **Aktualizuj scenę**, aby zapisać nową wysokość kamery w tej scenie.

![](<../../.gitbook/assets/7 (1) (1).png>)

_**Uwaga:**_ _kąt i położenie kamery sceny możesz również dostosować, przełączając przycisk_ _**Edytuj kamery sceny**_ _w górnej części_ _**palety Sceny**_ _(między przyciskami aktualizacji i odtwarzania)._

3 — Teraz wyeksportujmy nasze sceny do nowego modelu. Najpierw musimy utworzyć obiekty kamery dla wszystkich scen za pomocą wtyczki **Manage Cameras** \(Zarządzaj kamerami\):

1. Otwórz ponownie **paletę Manage Cameras** \(Zarządzaj kamerami\).
2. Upewnij się, że jest zaznaczona opcja **Copy Cameras to Clipboard** \(Kopiuj kamery do schowka\).
3. Kliknij przycisk **Export Scenes to Cameras** \(Eksportuj sceny do kamer\). Może to potrwać kilka sekund.
4. Jeśli cały obszar rysunku stał się biały, oznacza to, że **kamera główna** została dopasowana do jednej z kamer sceny. **Powiększaj (Z)** obraz, aż zobaczysz 3 budynki główne i nowo utworzone obiekty kamery. Pamiętaj, że obiekty kamery są automatycznie umieszczane w jednej dużej grupie o nazwie **Cameras** \(Kamery\). W obrębie tej grupy każda kamera jest umieszczana we własnej grupie o takiej samej nazwie jak sceny, z których została utworzona.

![](<../../.gitbook/assets/8 (7) (1).png>)

4 — Skopiujmy te sceny do nowego modelu. Ponieważ dane kamery zostały zapisane w schowku, nie ma wiele do zrobienia:

1. **Zapisz** **(Ctrl + S)** bieżący model i zamknij go.
2. Rozpocznij nowy pusty szkic, wybierając opcję **Nowy szkic (Ctrl + N)** z listy rozwijanej **Plik** na pasku **Menu główne**.
3. Otwórz wtyczkę **Manage Cameras** \(Zarządzaj kamerami\), jeśli nie jest jeszcze otwarta, i upewnij się, że jest zaznaczona opcja **Look for Cameras on Clipboard** \(Szukaj kamer w schowku\).
4. Kliknij przycisk **Import Scenes from Cameras** \(Importuj sceny z kamer\) w pobliżu dolnej części wtyczki. Sceny z drugiego modelu zostaną zaimportowane. Aby to sprawdzić, otwórz **paletę Sceny** i/lub włącz warstwę **Camera** \(Kamera\). Zobaczysz, że wszystkie sceny i obiekty kamery 3D zostały zaimportowane do tego modelu.

![](<../../.gitbook/assets/9 (7) (1).png>)
