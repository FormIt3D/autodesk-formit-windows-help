# Jak používat moduly plug-in

![](<../.gitbook/assets/g3 (1).gif>)

## Nástroj Plugin Manager

Plugin Manager aplikace FormIt je komplexní nástroj pro vyhledávání a správu modulů plug-in.

Nástroj Plugin Manager je načten automaticky při spuštění aplikace FormIt, pokud má aplikace FormIt přístup k internetu.

Přístup k nástroji získáte kliknutím na ikonu karty ![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PluginManagerTab.PNG) v pravé části aplikace:

![](../.gitbook/assets/c1.PNG)

## Kategorie modulů plug-in

Nástroj Plugin Manager uspořádává moduly plug-in do kategorií, což usnadňuje nalezení modulů, které vás nejvíce zajímají.

![](../.gitbook/assets/d16.png)

**Installed:** Moduly plug-in již byly nainstalovány uživatelem.&#x20;

**Recommended:** Moduly plug-in, které tým aplikace FormIt doporučuje k rozšíření základních funkcí aplikace FormIt a odemknutí nových pracovních postupů. Moduly plug-in vyvinuté komunitou se zde objeví po schválení týmem aplikace FormIt.\
Štítek GitHub: _formit-plugin-recommended_

**Public:** Moduly plug-in vytvořené komunitou. Moduly plug-in v této kategorii nebyly zkontrolovány ani schváleny týmem FormIt. \
Štítek tag: _formit-plugin_

**For Developers**: Moduly plug-in vytvořené komunitou za účelem vytváření nových modulů plug-in aplikace FormIt. \
Štítek tag: _formit-plugin-developers_

## Přidání soukromého nebo místního modulu plug-in

Pokud [vyvíjíte vlastní modul plug-in](how-to-develop-plugins/), můžete přidat jeho soukromou adresu URL do pole v dolní části a kliknout na tlačítko (+):

![](../.gitbook/assets/d4.PNG)

Další informace o přidávání soukromého nebo místního modulu plug-in naleznete v části [Zobrazení náhledu modulu plug-in v nástroji Plugin Manager. ](how-to-develop-plugins/advanced-development/previewing-a-plugin-in-the-plugin-manager.md)

## Obnovení nástroje Plugin Manager

Nástroj Plugin Manager používá v systému Windows k ukládání nainstalovaných úložišť a modulů plug-in klíče registru. Pokud potřebujete obnovit výchozí nastavení nástroje Plugin Manager, odstraňte následující klíč registru:

`Computer\HKEY_CURRENT_USER\Software\Autodesk\FormIt 360\Plugins`

⚠️ Poznámka: Tímto způsobem odinstalujete všechny úložiště a moduly plug-in přidané uživatelem a obnovíte nástroj Plugin Manager tak, aby obsahoval pouze integrovaná úložiště a moduly plug-in.

## Instalace modulů plug-in

[Plugin Manager](how-to-use-plug-ins.md#plugin-manager) obsahuje řadu modulů plug-in, které jsou uspořádány v různých kategoriích. U každého modulu plug-in je zobrazen název, popis, odkaz na GitHub a přepínač pro instalaci.&#x20;

![](../.gitbook/assets/d5.PNG)

Chcete-li nainstalovat modul plug-in, jednoduše přepněte přepínač vedle názvu modulu.&#x20;

![](../.gitbook/assets/d6.png)

Ikona vybraného modulu plug-in se zobrazí v pravém panelu. Kliknutím na tuto ikonu zobrazíte uživatelské rozhraní modulu plug-in.

![](../.gitbook/assets/d7.PNG)

## Používání modulů plug-in

Každý modul plug-in má jedinečné uživatelské rozhraní definované vývojářem. Modul plug-in obvykle obsahuje sadu pokynů, jak jej používat, sadu parametrů (textová pole, posuvníky, zaškrtávací políčka atd.) a jedno nebo více tlačítek pro jeho spuštění.

Jako příklad použijeme jeden z jednodušších příkladů v nástroji Plugin Manager: Fillet 2D Corners. Nejprve načtete modul plug-in z části Recommended (Doporučené) v nástroji Plugin Manager. Poté podle pokynů vývojáře nastavíme poloměr zaoblení, vybereme skupinu ploch, které chcete zaoblit, a klikneme na tlačítko Fillet Corners (Zaoblit rohy).

![](../.gitbook/assets/g4.gif)

##

