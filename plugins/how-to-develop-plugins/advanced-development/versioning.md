# Zarządzanie wersjami

Podczas tworzenia i aktualizowania wtyczki może być w pewnym momencie konieczne zarządzanie wersjami kodu.

Na przykład interfejsy API programu FormIt mogą się zmieniać w kolejnych wersjach, ale mimo że nowa wersja wtyczki może korzystać z nowych interfejsów API programu FormIt lub WSM, niekiedy warto zachować również możliwość używania wtyczki w starszych klientach.

Od wersji FormIt **18.0** można zaimplementować dla wtyczki zarządzanie wersjami w 3 prostych krokach:

* Dodaj plik _version.json_ do katalogu głównego wtyczki.
* Określ w pliku _version.json_ poszczególne zgodne wersje programu FormIt oraz katalogi zawierające te pliki wtyczek.
* Użyj wewnętrznego numeru wersji programu FormIt, czyli „numeru kompilacji”, który jest podany w programie FormIt w obszarze Informacje > Informacje o programie.



### Jak zorganizować zarządzanie wersjami dla wtyczki

Zorganizuj pliki i katalogi wtyczki tak, aby były zgodne z plikiem _version.json_

Plik _version.json_ powinien wyglądać następująco:

```
        [
            {
                "version":{
                    "major":18,
                    "minor":0
                },
                "path":"v18_0"
            },
            {
                "version":{
                    "major":19,
                    "minor":1
                },
                "path":"v19_0"
            }
        ]

```

Powyższe ścieżki _v18\_0_ i _v19\_0_ muszą być poprawnymi ścieżkami podrzędnymi z katalogu głównego danego katalogu/repozytorium.

![](../../../.gitbook/assets/i1.png)

![](../../../.gitbook/assets/i2.png)

![](../../../.gitbook/assets/i3.png)

Dobrym rozwiązaniem jest przeniesienie kodu wtyczki do podkatalogów. W przypadku powyższego pliku _version.json_ struktura katalogów wygląda następująco:

* **version.json** (plik)
* **v18\_0** (katalog)

   * **manifest.json** (plik)
   * **plugin.html** (plik)
   * **plugin.js** (plik)


* **v19\_0** (katalog)
   * **manifest.json** (plik)
   * **plugin.html** (plik)
   * **plugin.js** (plik)

Opcjonalne właściwości wersji to „exactVersion” i „lastVersion”. „exactVersion” wskazuje, że wersja musi być dokładnie zgodna z wersją programu FormIt. „lastVersion” wskazuje ostatnią wersję, którą można uruchomić w programie FormIt.\


```
[
    {
      "version":{
        "major":18,
        "minor":0,
        "exactVersion":true
        },
        "path":"v18_0"
    },
    {
        "version":{
            "major":19,
            "minor":1,
            "lastVersion":true
       },
        "path":"v19_0"
    }
 ]
```

Można również używać rozgałęzień/oznaczeń/zatwierdzeń systemu git dla ścieżek.

Jeśli pracujesz z wersją wstępną lub beta programu FormIt i chcesz przetestować zmiany we wtyczce, która współdziała tylko z wersją wstępną:

* Wykonaj powyższe czynności, ale użyj nazwy pliku _versions\_prerelease.json_
* Jeśli zatwierdzisz w repozytorium wersję _versions\_prerelease_, usuń ją, gdy ta wersja wstępna programu FormIt zostanie opublikowana
   * W przeciwnym razie przyszłe wersje wstępne programu FormIt będą wczytywać wtyczkę z lokalizacji, która może być przestarzała lub przeznaczona dla starszej wersji.
