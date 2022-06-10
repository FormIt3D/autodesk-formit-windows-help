# Modul plug-in Properties Plus

_Tento modul plug-in je pokročilejší verzí standardní_ _**palety Vlastnosti**. Pokud vyberete více skupin nebo typů geometrie, tento modul plug-in vám poskytne přehled o tom, co bylo vybráno, a také umožní hromadné přejmenování skupin a instancí skupin._

1 **–** Nejprve se podíváme na vlastnosti skupiny dveří z našeho hlavního modelu. Znovu otevřete soubor **Encode Campus Sample Model.axm** a přejděte zpět do scény **Eye Level**. Chcete-li začít využívat modul plug-in **Properties Plus**, proveďte následující kroky:

1. Kliknutím na vlastnost s ikonou symbolu „+“ otevřete **paletu Properties Plus**.
2. Ujistěte se, že je zaškrtnuta možnost **Update on Selection Change** (Aktualizovat při změně výběru).
3. Vyberte jednu ze skupin dveří s dvojitým sklem nazvanou **Dveře** na pravé straně uličky.
4. V části **Počet výběrů** se v poli **Celkový počet objektů** zobrazí informace, že je vybrán jeden objekt (**1**).
5. Níže naleznete další informace o tom, jaké typy objektů byly vybrány. V tomto případě je vybrána jedna skupina (**1**), ale tato skupina má někde v modelu čtyři instance (**4**).

![](<../../.gitbook/assets/10 (2) (1).png>)

_**Poznámka:**_ _Kontrola počtu instancí vybrané skupiny může být velmi užitečná, aby se zabránilo nechtěné změně více prvků, pokud jste chtěli změnit pouze vybraný prvek, ale zapomněli jste jej nejprve učinit jedinečným._

2 – Tento modul plug-in umožňuje upravit název skupiny nebo instance skupiny, aniž by bylo nutné přejít do režimu úprav skupiny, a přejmenovat více instancí najednou. Jak jsme se již dříve dozvěděli, každá skupina má název, ale každá instance této skupiny může mít také jedinečný název „instance“. Protože v tomto modelu bude pravděpodobně existovat mnoho typů dveří, chceme tuto skupinu a některé její instance pojmenovat konkrétněji.

1. Se stále vybranou první skupinou **Dveře** přidejte další skupinu **Dveře** do aktuálního výběru tak, že podržíte klávesu **Shift** nebo **Ctrl** a kliknete na druhou skupinu **Dveře** s dvojitým sklem poblíž první skupiny.
2. Všimněte si, že paleta **Vlastnosti Plus** nyní aktualizovala **počet výběrů**. Nyní zobrazuje, že jsou vybrány dvě (**2**) instance, ale stále je vybrána pouze jedna (**1**) jedinečná **rodina** (neboli skupina). (Přestože tento modul plug-in používá termín **Rodina**, který by měl být uživatelům aplikace Revit známý, v tomto kontextu znamená totéž co skupina aplikace FormIt.)
3. V části **Group Family** (Rodina skupin) aktualizujte hodnotu v poli **Name** (Název) na **Doors – Double Glass Storefront** (Dveře – výloha s dvojitým sklem). Tím se aktualizuje název skupiny pro všechny instance bez ohledu na to, kde se nacházejí nebo zda jsou aktuálně vybrány či nikoli, aniž by bylo nutné na skupinu dvakrát kliknout a upravit ji.
4. Protože obě tyto instance jsou dveře v části Groove Coffee, přejmenujte pouze tyto dvě instance zadáním názvu **Dveře Groove Coffee** do pole **Name** (Název) v části **Multiple Group Instances** (Instance více skupin).

**Poznámka:** Ve standardní **paletě Vlastnosti** neexistuje způsob, jak přejmenovat více instancí skupiny najednou. Tato funkce může být velmi užitečná, pokud chcete přejmenovat desítky nebo stovky instancí se stejným názvem najednou.

![](<../../.gitbook/assets/11 (6) (1).png>)

_**Poznámka:**_ _Pokud myš opustí paletu, nebudete již moci vybrané textové pole upravovat. To platí pro všechny palety, takže při úpravách čehokoli uvnitř palety dávejte pozor, aby se kurzor stále nacházel uvnitř hranic palety._

3 – Pokud nyní vyberete skleněné dveře Groove Coffee nebo jiné skleněné dveře a podíváte se na jejich vlastnosti v **běžné paletě Vlastnosti**, uvidíte, že název **skupiny** byl aktualizován pro každou instanci, ale pouze u dveří Groove Coffee byla jejich vlastnost **Name** (Název) pro danou instanci změněna oproti výchozí hodnotě.

![](<../../.gitbook/assets/12 (3) (1).png>)

4 – Nakonec se podívejme, jak tento modul plug-in třídí různé typy prvků:

1. Rychle nakreslete **čáru (L)**, **obdélník (R)** a **krychli (Alt+B)** kdekoli v modelu. Budou dočasné, takže jejich přesné umístění není důležité.
2. Znovu otevřete paletu **Properties Plus**, pokud jste ji zavřeli, a poté stisknutím kláves **Ctrl+A** vyberte všechny viditelné prvky v modelu.
3. Podívejte se na část **Počet výběrů** a všimněte si, že vybrané prvky jsou rozděleny na **hrany** (čáry), **plochy**, **tělesa** (3D tvary vytvořené z ploch a hran, například krychle)**,** **skupiny** a další.

![](<../../.gitbook/assets/13 (3) (1).png>)

_**Poznámka:**_ _Tento modul plug-in také detekuje_ _**vrcholy** které lze vytvořit pomocí jiného modulu plug-in s názvem_ _**Generate Vertex**. Pokud chcete experimentovat, nainstalujte si_ _**modul plug-in Generate Vertex**_ _a zopakujte výše uvedené kroky._
