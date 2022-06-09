# Wtyczka Properties Plus (Właściwości Plus)

_Ta wtyczka jest bardziej funkcjonalną wersją standardowej_ _**palety Właściwości**. Jeśli zostało wybranych wiele grup i/lub typów geometrii, ta wtyczka zapewni podział elementów, które zostały wybrane, jak również umożliwi masową zmianę nazw grup i wystąpień grup._

1 **—** Najpierw przyjrzymy się właściwościom grupy drzwi z naszego modelu głównego. Otwórz ponownie plik **Encode Campus Sample Model.axm** i wróć do sceny **Eye Level — Long Alley** \(Poziom wzroku — Długa uliczka\). Aby rozpocząć korzystanie z wtyczki **Properties Plus** \(Właściwości Plus\):

1. Otwórz **paletę Properties Plus** \(Właściwości Plus\), klikając właściwość z ikoną symbolu „plus”.
2. Upewnij się, że jest zaznaczona opcja **Update on Selection Change**\(Aktualizuj przy zmianie wyboru\).
3. Wybierz jedną z grup podwójnych szklanych drzwi o nazwie **Door** \(Drzwi\) po prawej stronie uliczki.
4. W obszarze **Selection Count** (Liczba wybranych elementów) w polu **Total Objects** (Całkowita liczba obiektów) jest wyświetlany komunikat, że wybrano jeden (**1**) obiekt.
5. Tuż poniżej możemy znaleźć więcej informacji na temat typów obiektów, które zostały zaznaczone. W tym przypadku zaznaczona jest jedna (**1**) grupa, ale ma ona cztery (**4**) wystąpienia w innych miejscach w modelu.

![](<../../.gitbook/assets/10 (2) (1).png>)

_**Uwaga:**_ _sprawdzenie liczby wystąpień wybranej grupy może być bardzo przydatne, ponieważ pozwala zapobiec przypadkowym zmianom wielu elementów, gdy w rzeczywistości chcesz zmienić tylko wybrany element, ale zapominasz zmienić go na unikatowy._

2 — Ta wtyczka umożliwia edycję nazwy grupy lub wystąpienia grupy bez konieczności przechodzenia do trybu edycji grupy oraz zmianę nazw wielu wystąpień jednocześnie. Jak dowiedzieliśmy się wcześniej, każda grupa ma nazwę, ale każde wystąpienie tej grupy może również mieć niepowtarzalną nazwę „wystąpienia”. Ponieważ w tym modelu najprawdopodobniej będzie wiele typów drzwi, chcemy nadać tej grupie i niektórym jej wystąpieniom bardziej charakterystyczne nazwy.

1. Przy wciąż zaznaczonej grupie pierwszych szklanych **drzwi** dodaj do bieżącego zaznaczenia inną grupę **Door** \(Drzwi\), przytrzymując naciśnięty klawisz **Shift** lub **Ctrl** i klikając jednokrotnie drugą grupę podwójnych szklanych **drzwi** w pobliżu pierwszej.
2. Zwróć uwagę, że na **palecie Properties Plus** (Właściwości Plus) została zaktualizowana wartość **Selection Count** (Liczba wybranych elementów), aby pokazać, że zaznaczone są dwa (**2**) wystąpienia, ale nadal zaznaczona jest tylko jedna (**1**) unikatowa **rodzina** (grupa). W tej wtyczce używany jest termin **Family** (Rodzina), który powinien być znany użytkownikom programu Revit, ale w tym kontekście oznacza on to samo co grupa programu FormIt.
3. W obszarze **Group Family** \(Rodzina grup\), w polu **Name** \(Nazwa\) zmień wartość na **Doors — Double Glass Storefront** \(Drzwi — Podwójna szklana witryna\). Spowoduje to zaktualizowanie nazwy grupy nazw dla wszystkich wystąpień, niezależnie od tego, gdzie one się znajdują i czy są aktualnie zaznaczone, bez konieczności dwukrotnego kliknięcia i edycji grupy.
4. Ponieważ oba te wystąpienia są drzwiami w obszarze kawiarni Groove Coffee, zmieńmy nazwę tylko tych dwóch wystąpień, wprowadzając nazwę **Groove Coffee Door** \(Drzwi kawiarni Groove Coffee\) w polu **Name** \(Nazwa\) w obszarze **Multiple Group Instances** \(Wiele wystąpień grupy\).

**Uwaga:** w standardowej **palecie Właściwości** nie można zmienić nazw wielu wystąpień grupy jednocześnie. Może to być szczególnie przydatne, gdy chcesz zmienić nazwy kilkudziesięciu lub kilkuset wystąpień o tej samej nazwie jednocześnie.

![](<../../.gitbook/assets/11 (6) (1).png>)

_**Uwaga:**_ _jeśli wskaźnik myszy wyjdzie poza paletę, nie będzie można dalej edytować wybranego pola tekstowego. Dotyczy to wszystkich palet, dlatego podczas edycji dowolnego elementu wewnątrz palety pamiętaj o utrzymywaniu wskaźnika w obrębie palety._

3 — Jeśli teraz zaznaczysz szklane drzwi kawiarni Groove Coffee lub inne szklane drzwi i przyjrzysz się ich właściwościom na zwykłej **palecie Właściwości**, zobaczysz, że nazwa w polu **Grupa** została zaktualizowana dla każdego wystąpienia, ale tylko w przypadku drzwi kawiarni Groove Coffee zmieniła się domyślna wartość właściwości **Nazwa**.

![](<../../.gitbook/assets/12 (3) (1).png>)

4 — Na koniec przyjrzyjmy się, w jaki sposób wtyczka sortuje różne typy elementów:

1. Szybko narysuj **linię (L)**, **prostokąt (R)** i **sześcian (Alt + B)** w dowolnie wybranym miejscu w modelu. Będą one tymczasowe, dlatego ich dokładne położenie nie jest ważne.
2. Otwórz ponownie **paletę Properties Plus** \(Właściwości Plus\), jeśli była zamknięta, a następnie naciśnij klawisze **Ctrl + A**, aby zaznaczyć wszystkie widoczne elementy w modelu.
3. W obszarze **Selection Count** (Liczba wybranych elementów) zwróć uwagę, że zaznaczone elementy są podzielone na kategorie **Edges** (Krawędzie) (linie), **Faces** (Powierzchnie), **Bodies** (Bryły) (kształty 3D wykonane z powierzchni i krawędzi, takie jak sześcian)**,** **Groups** (Grupy) itd.

![](<../../.gitbook/assets/13 (3) (1).png>)

_**Uwaga:**_ _ta wtyczka wykrywa również_ _**wierzchołki**, które można utworzyć za pomocą innej wtyczki o nazwie_ _**Generate Vertex** \(Generuj wierzchołek\). Jeśli chcesz poeksperymentować, zainstaluj_ _**wtyczkę Generate Vertex**_ \(Generuj wierzchołek\)_i powtórz powyższe czynności._
