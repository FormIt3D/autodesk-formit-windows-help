# Wprowadzenie do wtyczek

![](../.gitbook/assets/gg4.gif)

Wtyczki to niestandardowe dodatki programowe, które rozszerzają podstawowe funkcje programu FormIt. Wtyczki mogą rozszerzać, usprawniać i upraszczać procesy robocze modelowania 3D w programie FormIt.&#x20;

Wtyczki mogą służyć do generowania obiektów, modyfikowania istniejących obiektów lub wyodrębniania informacji o obiekcie. Wtyczki mogą również używać rozbudowanych interfejsów internetowych do wyświetlania danych oraz zapewniania elementów sterujących i danych wejściowych bezpośrednio w aplikacji.&#x20;

## Uzyskiwanie dostępu do wtyczek

Wtyczki są dostępne w narzędziu [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) w wersjach komputerowej oraz internetowej programu FormIt, o ile komputer jest połączony z Internetem. Wtyczki składają się z serii plików i folderów przechowywanych w serwisie GitHub lub na serwerze lokalnym (w przypadku tworzenia własnej wtyczki).&#x20;

![](../.gitbook/assets/c17.PNG)

### Wtyczki wymagają dostępu do Internetu

Wtyczki zewnętrzne (wtyczki inne niż hostowane lokalnie) wymagają połączenia z Internetem do wstępnego wczytania, co ma następujące konsekwencje:

* Wtyczki zewnętrzne nie zostaną wczytane, jeśli podczas uruchamiania programu FormIt nie zostanie wykryte połączenie z Internetem. Po wczytaniu niektóre wtyczki zewnętrzne mogą nadal działać w trybie offline w danej sesji, ale działanie innych może zostać przerwane, dopóki połączenie nie zostanie przywrócone.&#x20;
* Wtyczki zewnętrzne wczytują najnowszy kod na serwerze przy każdym uruchomieniu, więc ich funkcje są aktualizowane za każdym razem, gdy autor wprowadza zmiany. Wtyczki są wczytywane asynchronicznie, co oznacza, że kolejność wtyczek w interfejsie programu FormIt może się zmieniać podczas każdej nowej sesji.

## Otwórz źródło

Wtyczki są składnikami typu open source, dzięki czemu można bezpłatnie używać wtyczek w narzędziu [Plugin Manager](how-to-use-plug-ins.md#plugin-manager), łatwo je publikować i udostępniać oraz znajdować inne wtyczki w serwisie GitHub, aby analizować ich konstrukcję.&#x20;

Jeśli jesteś programistą i chcesz uzyskać więcej informacji na temat publikowania wtyczek, zobacz temat [Hostowanie wtyczki w serwisie GitHub](how-to-develop-plugins/advanced-development/hosting-a-plugin-on-github.md).&#x20;

Aby utworzyć wtyczkę do użytku prywatnego, można ją opracować i hostować za pomocą usługi lokalnej. Aby uzyskać więcej informacji, zobacz temat [Korzystanie ze środowiska IDE. ](how-to-develop-plugins/advanced-development/using-an-ide.md)

![](../.gitbook/assets/c18.PNG)



## Skontaktuj się z nami

Jeśli potrzebujesz pomocy dotyczącej wtyczek programu FormIt, daj nam znać na [forum programu FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=en).

![](../.gitbook/assets/c19.PNG)

&#x20;

&#x20;
