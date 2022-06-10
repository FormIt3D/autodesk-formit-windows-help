# Generování světelných řetězů

_V této kapitole si ukážeme několik modulů plug-in, které jsou součástí aplikace FormIt, a provedeme několik vylepšení souboru_ _**Encode Campus Sample Model.axm**. Pokud jste tak ještě neučinili, můžete si soubor stáhnout z _[_datové sady k příručce Základy aplikace FormIt, Část II_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip)__

_Tento praktický modul plug-in umožňuje do modelu rychle přidat závěsná světla na ve tvaru čáry nebo křivky._

1 – Před přidáním nových světel se podívejme na zamýšlený výsledek pomocí předem vytvořené scény v modelu.

1. Chcete-li přejít na scénu obsahující existující světelné řetězy, otevřete **paletu Scény** a dvakrát klikněte na scénu s názvem **Eye Level – Short Alley**.
2. Všimněte si světelného řetězu obsaženého v tomto modelu – tento řetěz chceme znovu vytvořit, ale někde jinde.
3. Na **paletě Hladina** zapněte hladinu **Pomocná geometrie**, aby se zobrazily původní čáry použité k vytvoření těchto světelných řetězů.

![](<../../.gitbook/assets/3 (10).png>)

2 – Nyní přejdeme do druhé uličky a přidáme světla. Na **paletě Scény** otevřete scénu **Eye Level – Long Alley**. Všimněte si, že v této uličce ještě nejsou žádné světelné řetězy.

3 – Vytvoření nových světelných řetězů:

1. Kliknutím na ikonu světelného řetězu otevřete nově nainstalovanou **paletu Generování světelných řetězů**. Ve výchozím nastavení se ikony nových modulů plug-in zobrazují v dolní části.
2. Do pole **Počet svítidel** zadejte hodnotu **10**.
3. Dvakrát klikněte na jednu z pomocných čar, abyste upravili předem vytvořenou skupinu **Světelné řetězy – dlouhá ulička**. Poté jedním kliknutím vyberte jednu z předpřipravených pomocných čar.
4. Na paletě modulu plug-in klikněte na tlačítko **Generovat světelné řetězy**. Měl by se zobrazit nový světelný řetěz. Všimněte si, že každý světelný řetěz je vytvořen jako vlastní jedinečná skupina.

![](<../../.gitbook/assets/4 (6) (1).png>)

_**Poznámka:**_ _Nedělejte si starosti, že některé čáry procházejí nápisem „Groove Coffee“, protože modul plug-in světelných řetězů vytváří řetězovou křivku, která se pod nápisem realisticky prohne._

4 – Zkuste vytvořit další světelné řetězy pomocí další přednastavené pomocné čáry nebo si vytvořte vlastní pomocné čáry. Experimentujte s nastavením modulu plug-in, abyste získali různé výsledky.

5 – Aby byl model lépe uspořádán, doporučujeme po dokončení seskupit všechny pomocné čáry a umístit tuto skupinu do hladiny **Pomocná geometrie** a také přiřadit všechny skupiny světelných řetězů k hladině **Kontext – vnější osvětlení**. Tím se zabrání tomu, aby se pomocné čáry objevily v některé ze scén „Eye Level", kde je nechceme vidět. Až budete hotovi, měly by vaše výsledky vypadat podobně jako na následujícím obrázku.

![](<../../.gitbook/assets/5 (3) (1).png>)

_**Poznámka:**_ _Na rozdíl od geometrie vytvořené pomocí skriptu aplikace Dynamo, kterou lze aktualizovat a znovu vytvořit prostřednictvím_ _**palety Vlastnosti**, jsou objekty vytvořené pomocí modulu plug-in (většinou) běžnou geometrií aplikace FormIt. Po vytvoření je lze upravovat pouze pomocí integrovaných modelovacích nástrojů aplikace FormIt._
