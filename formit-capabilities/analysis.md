---
popis: >-
  Pracovní postup BIM zahajte hodnocením výkonnosti prvků na začátku procesu návrhu.
---

# Analýza slunečního záření a energetická analýza

\![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## Energetická analýza v aplikaci FormIt

Analyzujte model budovy z hlediska energetické účinnosti již v rané fázi procesu návrhu.

[Zobrazení projektů v aplikaci Insight](https://gbs.autodesk.com/OneEnergy/Insight)

## Energetická analýza pomocí aplikace Insight

S předplatným aplikace **FormIt Pro** prostřednictvím sady [AEC Collection](https://www.autodesk.com/collections/architecture-engineering-construction/overview) získáte přístup k energetické analýze pomocí aplikace **Insight**:

* Pomocí modulu analýzy služby Green Building Studio analyzujte modely návrhů v rané fázi projektu.
* Připojte se k řídicímu panelu s výsledky analýzy a porovnejte možnosti pro váš návrh.
* Upravte faktory energetické analýzy, například poměr oken a stěn, orientaci budovy a další.
* Shrňte energetický dopad budovy pomocí jediného čísla, které se vypočte jako výsledné náklady na plochu.
* Uložte výsledky energetické analýzy pro budoucí kontrolu s klienty a dalšími zúčastněnými stranami.

## Co je nového ohledně spolupráce aplikací FormIt a Insight<a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Vylepšení spolehlivosti aplikace Insight** <a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* Aplikace [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) nyní před spuštěním aplikace Insight kontroluje běžné problémy v modelu a opravuje běžné chyby aplikace Insight, aby bylo zajištěno spolehlivější prostředí.
* Aplikace FormIt 2021 také obecně zlepšuje spolehlivost propojení aplikací FormIt a Insight, řeší řadu známých chyb a zvyšuje úspěšnost fungování.

## Začínáme<a href="#insight-getting-started" id="insight-getting-started"></a>

### **Popis funkce** <a href="#how-it-works" id="how-it-works"></a>

* Funkce energetické analýzy v aplikaci Insight nahraje data modelu aplikace FormIt a provede v cloudu několik set analýz, aby určila různá energetická hodnocení.
* Energetická analýza používá k analýze modelu aplikaci Revit, takže stejně jako při odesílání dat aplikace FormIt do aplikace Revit je nutné [zajistit, aby byl model aplikace FormIt vodotěsný a rozložený](https://formit.autodesk.com/blog/post/repairing-solid-models).

### **Příprava modelu aplikace FormIt** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Aplikace Insight použije veškerou viditelnou geometrii v náčrtu aplikace FormIt.
  * Ujistěte se, že skořepina budovy, kterou chcete analyzovat, je jedinou viditelnou geometrií.
  * Umístěte podpůrnou geometrii, například stafáž, nábytek a prvky pozemku, do samostatné [hladiny](../tool-library/layers.md) a tuto hladinu vypněte.
* Aplikace Insight funguje nejlépe s jednoduchým modelem budovy.
  * Ujistěte se, že objem budovy je [vodotěsné těleso](https://formit.autodesk.com/blog/post/repairing-solid-models).
  * Pokud již návrh budovy obsahuje otvory pro okna a dveře, je nejlepší vytvořit nový objem bez otvorů speciálně pro energetickou analýzu a detailnější verzi skrýt pomocí hladin.
* U jednoduchého objemu budovy je nutné použít [podlaží](../tool-library/levels-and-area.md).
* Model aplikace FormIt musí mít nastaveno [umístění](../tool-library/setting-location.md).

![](../.gitbook/assets/insight.png)

### **Spuštění energetické analýzy** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* Vyhledejte tlačítko Energetická analýza na panelu nástrojů.

![](../.gitbook/assets/generate\_insight.png)

* Kliknutím na možnost Generovat přehled spusťte proces.
* Tím se nahrají viditelná data modelu a provede se několik stovek simulací v cloudu.
* Po dokončení se v horní části obrazovky zobrazí zpráva a nabídka se aktualizuje, aby označila, že je k dispozici nový přehled.
  * Kliknutím na možnost Zobrazit přehled zobrazíte analýzu ve webovém prohlížeči.
  * Všechny své přehledy naleznete také v aplikaci [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight).

## Řešení potíží <a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **Běžné chyby** <a href="#common-errors" id="common-errors"></a>

* „Projekt přehledu nebylo možné vytvořit. Zkuste to znovu později.“
  * Přihlaste se k [řídicímu panelu služby Green Building Studio](https://gbs.autodesk.com/GBS/Project) a poté restartujte aplikaci FormIt.
    * Pokud se nemůžete přihlásit nebo se zobrazí stránka „přístup odepřen“, možná si budete muset [zakoupit předplatné služby Green Building Studio](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/ENU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html).
  * Zkontrolujte, zda je váš model [vodotěsné těleso](https://formit.autodesk.com/blog/post/repairing-solid-models).
  * Případné problémy se službami FormIt můžete zkontrolovat na [řídicím panelu stavu Autodesk](https://health.autodesk.com/).
* Chcete-li zjistit, zda služba Green Building Studio úspěšně provedla energetickou analýzu pro tento projekt, podívejte se na [řídicí panel služby Green Building Studio](https://gbs.autodesk.com/GBS/Project).
  * Nejnovější projekt by se měl objevit v horní části seznamu a měl by zobrazovat 248 spuštění.
  * Pokud se zobrazí 0 spuštění, [informujte nás na fórech aplikace FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142) a my vám pomůžeme s řešením problémů.

### **Podrobné protokoly** <a href="#detailed-logs" id="detailed-logs"></a>

* Další podrobnosti o selhání energetické analýzy můžete získat ve webové aplikaci FormIt:
  * Přejděte na [webovou aplikaci FormIt](https://formit.autodesk.com/app).
  * Otevřete model, který má problémy s energetickou analýzou.
  * Spusťte energetickou analýzu.
  * Otevřete nástroje pro vývojáře (stiskněte klávesu F12 v prohlížeči Google Chrome nebo Firefox).
  * Zobrazte kartu Konzole.
  * Zkopírujte všechny chyby nebo pořiďte snímky obrazovky a [nahlaste je na fórech aplikace FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142).

## Analýza slunečního záření

S předplatným aplikace **FormIt Pro** prostřednictvím sady [AEC Collection](https://www.autodesk.com/collections/architecture-engineering-construction/overview) můžete vizualizovat vliv slunce na budovu:

* Určete relevantní plochy, u kterých má být analyzován vliv slunečního záření.
* Vizualizujte výsledky během několika sekund na plátně aplikace.
* Přesunutím ukazatele myši nad vstupní bod zobrazte konkrétní vypočítané hodnoty dopadu slunečního záření.
* Vyberte si, zda chcete zobrazit výsledky jako měsíční studii zasklení nebo jako roční studii proveditelnosti solárních panelů.

Přečtěte si další informace o [analýze slunečního záření](../tool-library/solar-analysis.md) v aplikaci FormIt Pro.
