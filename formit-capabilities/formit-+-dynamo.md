---
description: Computational Design in FormIt
---

# FormIt a Dynamo

\![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

Aplikace FormIt pro systém Windows má integrovanou aplikaci Dynamo, díky čemuž můžete využívat neuvěřitelné pracovní postupy výpočetního návrhu.

## Co je nového v aplikacích FormIt a Dynamo

Aplikace FormIt 2024 je aktuální s nejnovější verzí aplikace Dynamo 2.17.

### **Datové grafy, odesílání podlaží do aplikace Excel a řízení tvorby plošek**

Aplikace [FormIt 2023](https://formit.autodesk.com/blog/post/introducing-formit-2023/) umožňuje spouštět grafy aplikace Dynamo[ bez uzlu SendToFormIt](formit-+-dynamo.md#graph-types), přidává možnost [odesílání podlaží aplikace FormIt do aplikace Excel](formit-+-dynamo.md#send-formit-levels-to-excel) a umožňuje řízení [tvorby plošek křivek a povrchů prostřednictvím nových uzlů FormItGroupOptions](../tool-library/curve-+-surface-faceting.md).

### **Vstupy kót a předběžný přístup k rozhraní API JS**

Aplikace [FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1) přidává možnost používat [známé kóty aplikace FormIt jako vstupy](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes), zavádí [možnosti na úrovni objektů](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes) a nabízí předběžný náhled [přístupu k rozhraním API jazyka JavaScript](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes). Získáte ji [zde](https://formit.autodesk.com/page/download).

### **Více uzlů SendToFormIt**

Aplikace [FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3) přidává možnost používat [více uzlů SendToFormIt a vnořené grafy aplikace Dynamo](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

### **Uzel SelectFromFormIt**

Aplikace [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) přidává uzel [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) a umožňuje vždy připojené relace, úpravy více instancí a mnoho dalšího.

## Začínáme

Seznamte se s rozhraním a připojte adresáře aplikace Dynamo k aplikaci FormIt.

### **Nastavení při prvním použití**

Používáte aplikace FormIt a Dynamo poprvé? Aby se 3D plátno zobrazilo v aplikaci Dynamo, bude možná nutné nejprve [nakonfigurovat systém](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes).

### **Panel Dynamo**

Pomocí panelu Dynamo můžete spustit aplikaci Dynamo, umisťovat skupiny aplikace Dynamo a upravovat grafy aplikace Dynamo:

\![Panel Dynamo](<../.gitbook/assets/dynamo_dynamopanel (1).png>)

### **Přidávání a správa místních adresářů aplikace Dynamo**

* Panel Dynamo funguje stejně jako [knihovna obsahu](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library), takže můžete připojovat a spravovat místní adresáře obsahující soubory aplikace Dynamo.
* Na panelu Dynamo klikněte na tlačítko Připojit adresář. Poté klikněte znovu na tlačítko (+) v dialogu Předvolby a vyberte adresář, který chcete připojit k aplikaci FormIt: <img src="../.gitbook/assets/dynamo_selectdirectory.png" alt="" data-size="line">
* Mezi připojenými adresáři můžete přepínat pomocí rozevíracího seznamu:

![](../.gitbook/assets/dynamo\_dropdown.png)

* Na panelu Dynamo můžete zobrazit pouze soubory .dyn a podsložky.
* Pomocí panelu Filtr můžete vyfiltrovat soubory a podsložky aplikace Dynamo, abyste snadno našli, co potřebujete:

![](../.gitbook/assets/dynamo\_filter.png)

## Různé způsoby práce s aplikací Dynamo

Vytvářejte a upravujte grafy v aplikaci Dynamo nebo upravujte parametry v aplikaci FormIt, aniž byste kdy viděli graf. Nebo obojí najednou!

### **Typy grafů**

Aplikace FormIt podporuje tři typy grafů aplikace Dynamo:

* Datový graf: Datové grafy nemají uzly _SendToFormIt_ a slouží k zobrazení nebo předávání dat prostřednictvím aplikace FormIt. Datové grafy můžete například použít k odeslání dat do aplikace Excel nebo k výpočtu negeometrických dat a jejich zobrazení v uzlu Watch.
* Graf geometrie: Tyto grafy okamžitě vytvářejí geometrii a je třeba je umístit na kreslicí plochu, aby se zobrazily jejich parametry. Po kliknutí na miniaturu se na kurzoru objeví geometrie, kterou můžete umístit do 3D scény. Tento graf vyžaduje, aby byl na konci grafu přítomen alespoň jeden uzel _SendToFormIt_, který přijímá geometrii.
* Graf výběru: Tyto grafy vyžadují před spuštěním výběr aplikace FormIt. V levém horním rohu aplikace FormIt se zobrazí výzva k výběru. Po zadání výběru se graf spustí a vygeneruje geometrii vzhledem k výběru. Tento graf vyžaduje, aby byl na konci grafu přítomen alespoň jeden uzel _SendToFormIt_, který přijímá geometrii.

![](../.gitbook/assets/dynamo-graph-types.png)

### **Graf geometrie: Umístění skupiny aplikace Dynamo do aplikace FormIt**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* Na panelu Dynamo klikněte na miniaturu grafu aplikace Dynamo, který chcete spustit.
  * Můžete použít integrované ukázky nebo [připojit knihovnu](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) vlastních souborů aplikace Dynamo.
* Umístěním geometrie do aplikace FormIt vložíte kopii grafu aplikace Dynamo do souboru aplikace FormIt.
  * Chcete-li vytvořit geometrii, je třeba k výstupním uzlům geometrie v grafu připojit uzel [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes).
* Geometrie z uzlu SendToFormIt bude k dispozici na kurzoru k umístění.
  * Pokud má graf uzly [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) označené jako Je vstup, aplikace FormIt se nejprve dotáže na výběr (každý uzel výběru ve svislém pořadí) a poté vygeneruje geometrii ve správném umístění vzhledem k výběru.
* Kopie původního souboru aplikace Dynamo je nyní vložena do skupiny aplikace FormIt a je nezávislá na zdrojovém grafu.
* Po umístění se panel Vlastnosti automaticky přepne a zobrazí dostupné parametry.

### **Graf geometrie: Úprava parametrů**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* Po umístění skupiny aplikace Dynamo ji vyberte a přejděte na panel Vlastnosti, nebo jednoduše dvakrát klikněte na skupinu, čímž se automaticky přepnete na panel Vlastnosti.
  * Zde budou uvedeny všechny vstupní uzly označené v aplikaci Dynamo jako „Je vstup“.
  * Vstupní uzly [**SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) se zobrazí jako tlačítka v horní části a lze je použít k aktualizaci výběru, který je použit k řízení grafu.
  * Aplikace FormIt podporuje tyto vstupní uzly: posuvníky čísel, posuvníky celých čísel, přepínače booleovských hodnot a pole čísel a řetězců.
* Proveďte změny vstupů v aplikaci FormIt a poté klikněte na tlačítko Spustit. Tlačítko Spustit se zbarví modře, což znamená, že parametry byly upraveny a graf je třeba spustit.
  * Aplikace Dynamo se spustí na pozadí, zpracuje změny a vrátí aktualizovanou geometrii do aplikace FormIt.
  * V aplikaci FormIt 2022 a novějších verzích první spuštění z panelu Vlastnosti spustí vyhrazenou instanci aplikace Dynamo, čímž se následné úpravy výrazně zrychlí.
  * Aplikaci FormIt můžete používat i při spuštěné aplikaci Dynamo. 
* Všimněte si, že při spuštění grafu Dynamo bude odstraněna a nahrazena veškerá geometrie uvnitř každé skupiny SendToFormIt.

### Datový graf: Odeslání podlaží aplikace FormIt do aplikace Excel

V aplikaci FormIt 2023 a novějších verzích můžete pomocí aplikace Dynamo odeslat podlaží aplikace FormIt do aplikace Excel: 

* Stáhněte si [ukázkový graf aplikace Dynamo](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn).
* Na paletě Dynamo přejděte do místního adresáře, do kterého byl uložen graf aplikace Dynamo.
* Klikněte pravým tlačítkem na miniaturu a klikněte na položku _Upravit vložený graf_.
* Vytvořte prázdnou tabulku aplikace Excel.
* Do pole Umístění tabulky zadejte cestu k tabulce aplikace Excel.
* Upravte libovolná další pole, například Název listu.
* Zavřete aplikaci Dynamo a graf uložte.

Nyní můžete jednoduše kliknout na vzorový soubor na paletě a ten se spustí v aplikaci FormIt bez nutnosti generovat geometrii. 

Na paletě Dynamo se zobrazí vstupy aplikace Dynamo a zobrazí se aplikace Excel, ve které se zobrazí výsledky z grafu. 

Při provádění změn v modelu můžete znovu kliknout na miniaturu grafu nebo na tlačítko _Spustit_ a aktualizovat tabulku s daty podlaží z nejnovější verze náčrtu aplikace FormIt.

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### Spuštění nového okna aplikace Dynamo

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* V aplikaci FormIt 2021 a novějších verzích se po kliknutí na tlačítko Spustit aplikaci Dynamo na panelu Dynamo automaticky spustí připojená relace s aplikací FormIt.
  * Tím se v aplikaci Dynamo otevře šablona grafu a v aplikaci FormIt se automaticky vygeneruje geometrie šablony.
  * Výsledná geometrie se zobrazí v nové skupině na počátku aktuálního kontextu úprav skupiny. Před spuštěním aplikace Dynamo je nejlepší být v požadovaném kontextu skupiny. 
  * Šablona obsahuje uzly aplikace FormIt i některé vzorové geometrie. Úpravou posuvníků se upraví velikost krychle v obou aplikacích.
  * Zde můžete otevřít různé grafy aplikace Dynamo nebo pomocí těchto základních komponent v šabloně vytvořit nové a pomocí příkazu Uložit jako v aplikaci Dynamo je uložit do nového umístění.

### **Úpravy vložených a zdrojových grafů**

Existující grafy aplikace Dynamo lze upravovat dvěma různými způsoby: úpravou vložených grafů, které již byly umístěny v aplikaci FormIt, nebo úpravou zdrojového grafu, který je uložen v počítači.

### **Vložené grafy**

Po umístění objektu aplikace Dynamo do aplikace FormIt se jeho základní graf zkopíruje a vloží do aktuálního souboru aplikace FormIt. Úpravy tohoto grafu v aplikaci Dynamo se provádějí pomocí tlačítka **Upravit vložený graf**.

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* Vyberte skupinu aplikace Dynamo a přejděte na panel Vlastnosti nebo jednoduše dvakrát klikněte na skupinu, čímž se automaticky přepnete na panel Vlastnosti.
* Klikněte na tlačítko **Upravit vložený graf**.
* V aplikaci Dynamo si všimněte, že název souboru v horní části bude nyní obsahovat text „(FormIt)“, což znamená, že upravujete graf, který je vložen v tomto souboru aplikace FormIt, a neupravujete zdrojový graf.
* Ujistěte se, že jeden nebo více uzlů [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) je připojeno ke geometrii, kterou chcete odeslat do aplikace FormIt.
* Aplikace FormIt zobrazí aktualizace geometrie v reálném čase při úpravě grafu.
* Pokud neuložíte změny v aplikaci Dynamo, vrátí se aplikace FormIt zpět k poslední uložené verzi grafu aplikace Dynamo.
* Všimněte si, že při spuštění grafu Dynamo bude odstraněna a nahrazena veškerá geometrie uvnitř každé skupiny SendToFormIt.

### **Zdrojové grafy**

Zdrojové grafy se zobrazí na panelu Dynamo po [připojení místních adresářů](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started). Tyto grafy jsou uloženy v počítači a lze je v aplikaci Dynamo upravit kliknutím na tlačítko Upravit zdrojový graf.

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* [Připojte adresář](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) obsahující soubory aplikace Dynamo k panelu Dynamo a poté přejděte do tohoto umístění na panelu. 
* Klikněte pravým tlačítkem myši na miniaturu grafu aplikace Dynamo, který chcete upravit (nebo klikněte na šipku), a vyberte tlačítko **Upravit zdrojový graf**.
* Aplikace Dynamo se spustí s otevřeným požadovaným grafem a v aplikaci FormIt uvidíte geometrii z konečného výstupu grafu.
  * U grafů, které jako vstup používají jeden nebo více uzlů [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes), se může stát, že výslednou geometrii neuvidíte, dokud nebudou uzly SelectFromFormIt vyplněny výběry.
* Výsledná geometrie se zobrazí v nové skupině na počátku aktuálního kontextu úprav skupiny.
  * Před kliknutím na tlačítko Upravit zdrojový graf je nejlepší být v požadovaném kontextu skupiny.
* Po dokončení úprav uložte a zavřete aplikaci Dynamo. V aplikaci FormIt byl zdrojový graf zkopírován a vložen do souboru aplikace FormIt.
  * Pokud potřebujete provést další úpravy **zdrojového grafu**, odstraňte vloženou kopii a znovu postupujte podle těchto kroků.

### **Řízení tvorby plošek křivek a povrchů**

*   Počínaje aplikací FormIt 2023 můžete řídit tvorbu plošek křivek a povrchů připojených k uzlům SendToFormIt pomocí uzlů FormItGroupOptions SetCurveFacetingCount a SetSurfaceFacetingCount.

    <img src="../.gitbook/assets/dynamo-formitgroupoptions-faceting-nodes.png" alt="" data-size="original">
* Tyto uzly přepisují globální nastavení plošek křivek a povrchů definovaných v nabídce Upravit -> Předvolby -> Jednotky + Přesnost.
* To je velmi užitečné, pokud graf aplikace Dynamo potřebuje generovat zakřivené objekty pomocí specifických hodnot plošek, protože se tím sníží nutnost měnit globální nastavení pro každý graf Dynamo spuštěný v aktuální relaci.

![](../.gitbook/assets/dynamo-formitgroupoptions-faceting.gif)

* Nastavení plošek můžete také nastavit globálně v nabídce Upravit -> Předvolby -> Jednotky + Přesnost.
* Po nastavení kvality oploškování v předvolbách znovu spusťte graf, aby se použila nová globální nastavení plošek.

![](../.gitbook/assets/dynamo\_controlcurve.gif)

[Další informace o nastavení plošek křivek a povrchů v aplikaci FormIt.](https://windows.help.formit.autodesk.com/tool-library/curve-+-surface-faceting)

## Použití skupin aplikace FormIt s aplikací Dynamo

Využijte výkonné skupiny aplikace FormIt pro lepší organizaci geometrie aplikace Dynamo a neuvěřitelné pracovní postupy.

### **Skupiny a uzel SelectFromFormIt**

* Při výběru geometrie pro uzel [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) je užitečné uložit geometrii do skupiny FormIt a vybrat tuto skupinu.
  * Získáte tím možnost flexibilně měnit obsah vybrané skupiny FormIt a poté jednoduše znovu spustit graf, který na tuto skupinu odkazuje, abyste viděli aktualizovaný výsledek.
* Pokud vyberete neseskupenou geometrii, změny této geometrie mohou mít za následek, že vás aplikace FormIt při příštím spuštění grafu vyzve k novému výběru geometrie.

### **Generování geometrie ve skupinách**

* Když je graf aplikace Dynamo spuštěn v aplikaci FormIt, jeho geometrické výsledky jsou obsaženy ve skupině aplikace FormIt.
* Každý uzel [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) v grafu vytvoří podskupinu, která bude obsahovat geometrii ze vstupního portu uzlu.
* Po vygenerování objektu aplikace Dynamo v aplikaci FormIt je celý graf i s jeho parametry vložen jako kopie do souboru aplikace FormIt.
* Po spuštění grafu je geometrie uvnitř každé podskupiny odstraněna a znovu vytvořena.
  * Při úpravách geometrie nebo vykreslení povrchů uvnitř podskupin buďte opatrní, protože tyto změny budou při dalším spuštění grafu Dynamo ztraceny.
  * Pokud však podskupiny (nikoli geometrii uvnitř nich) vykreslíte pomocí materiálů aplikace FormIt, tyto materiály zůstanou mezi jednotlivými spuštěními zachovány. Viz níže.

### **Práce se skupinami a materiály**

* Při použití více uzlů aplikace **SendToFormIt** můžete uspořádat uzly podle materiálu, abyste mohli různé podskupiny aplikace FormIt vykreslit pomocí různých materiálů.
* V tomto příkladu je celá budova vygenerována z jednoduchých rovin v aplikaci FormIt. Každá komponenta budovy vyžadující jedinečné materiály získá vlastní uzel **SendToFormIt**:

\![](<../.gitbook/assets/dynamo_sendtoformit (1).png>)

* Po použití materiálů na každou z podskupin zůstanou tyto materiály zachovány mezi spuštěními aplikace Dynamo:

![](../.gitbook/assets/dynamo\_materialsgif.gif)

### **Vnoření skupin aplikace Dynamo**

* Pomocí uzlu **SelectFromFormIt** můžete vybrat výsledky podskupiny z jednoho grafu aplikace Dynamo a řídit tak výsledky jiného grafu. 
* V návaznosti na výše uvedený příklad se výstup zasklení z grafu generátoru budovy použije jako geometrie výběru pro vestavěný vzorek obvodového pláště výlohy:

![](../.gitbook/assets/dynamo\_storefront\_curtainwallgif.gif)

* Když se tvar budovy změní, můžete jednoduše vybrat systémovou skupinu příčlí a kliknout na tlačítko Spustit na panelu Vlastnosti.
  * Přestože se obsah skupiny zasklení změnil, samotná skupina se nezměnila, takže při opakovaném spuštění grafu není třeba znovu vybírat zasklení.
* Výše uvedený model je k dispozici v aplikaci FormIt 2022 a novějších verzích jako „Roof Planes Building“ v podsložce **Building Masses** ve složce **Dynamo Samples**.
* V kombinaci s rozsáhlými možnostmi aplikace FormIt můžete pomocí aplikace Dynamo vytvořit a přizpůsobovat plně parametrický návrh, včetně materiálů a vnořené logiky, v bohatém kontextu výkonného koncepčního modelování:

![](../.gitbook/assets/dynamo\_parametricdesigngif.gif)

### **Stále platí standardní chování skupin aplikace FormIt**

* Kromě toho, co je uvedeno výše, se skupiny aplikace Dynamo v aplikaci FormIt řídí stejnými pravidly jako ostatní skupiny:
  * Umístění nového objektu aplikace Dynamo z panelu Dynamo vytvoří jedinečnou skupinu a neovlivní žádné instance stejného objektu, které již byly do náčrtu umístěny.
  * Při kopírování a vkládání zůstávají skupiny aplikace Dynamo identické. Veškeré změny provedené v jedné kopii grafu aplikace Dynamo aktualizují také geometrii v jejích identických instancích, pokud nejsou nastaveny jako jedinečné.
  * Skupiny aplikace Dynamo lze nastavit jako jedinečné pomocí klávesové zkratky MU nebo pomocí místní nabídky:

\![](<../.gitbook/assets/dynamo_makeunique (1).png>)

## Základní uzly aplikace FormIt

Nejvýkonnější uzly pro odesílání dat mezi aplikacemi FormIt a Dynamo.

### **Uzel SendToFormIt**

* Chcete-li v aplikaci FormIt vytvořit objekty aplikace Dynamo, připojte požadované výstupy geometrických uzlů ke vstupu _geometrie_ alespoň jednoho uzlu SendToFormIt:

\![](<../.gitbook/assets/dynamo_sendtoformitnode (1).png>)

* FormItGroupOptions je nový (volitelný) port v aplikaci FormIt 2022, který je podrobně popsán níže v části **Uzly FormItGroupOptions**.
* V aplikaci FormIt 2021.3 a novějších verzích můžete použít více uzlů SendToFormIt k uspořádání výsledků aplikace Dynamo do přehledných skupin a podskupin aplikace FormIt.
* [Podívejte se, jak aplikace Dynamo funguje se skupinami aplikace FormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

\![](<../.gitbook/assets/dynamo_sendtoformitnodes (1).png>)

* Uzel SendToFormIt bere ohled na příznak Je výstup, který je ve výchozím nastavení zaškrtnutý. Stav příznaku můžete ověřit kliknutím pravým tlačítkem myši na uzel:

\![](<../.gitbook/assets/dynamo_isoutput (1).png>)

* Pokud je tato možnost zaškrtnuta, geometrie připojená k tomuto uzlu SendToFormIt se zobrazí v aplikaci FormIt uvnitř podskupiny.
* Pokud není zaškrtnuta, nebude do aplikace FormIt odeslána žádná geometrie a odpovídající podskupina (pokud existuje) bude odstraněna.

### **Uzel SelectFromFormIt**

* Aplikace FormIt 2021 a novější nabízí možnost výběru geometrií z aplikace FormIt, které budou použity jako vstupy v grafech aplikace Dynamo:

\![](<../.gitbook/assets/dynamo_selectfromformitnode (1).png>)

* Název uzlu SelectFromFormIt bude použit ve výzvách v aplikaci FormIt, proto byste jej měli pojmenovat tak, aby popisoval, jaký typ geometrie aplikace FormIt by měl být vybrán:

\![](<../.gitbook/assets/dynamo_selectobjectstoarraynode (1).png>)

* Když kliknete na tlačítko Vybrat z aplikace FormIt v editoru grafu aplikace Dynamo nebo na panelu Vlastnosti, aplikace FormIt spustí režim průvodce výběrem, který vás provede výběrem geometrie:

![](../.gitbook/assets/dynamo\_selectobjectstoarrayUI.png)

* Uzel SelectFromFormIt bere ohled na příznak Je vstup, který je ve výchozím nastavení zaškrtnutý. Tuto možnost je nutné zaškrtnout, aby výběr v aplikaci FormIt fungoval. Stav příznaku můžete ověřit kliknutím pravým tlačítkem myši na uzel.

\![](<../.gitbook/assets/dynamo_isinput (1).png>)

* Pokud je zaškrtnut příznak Je vstup:
  * Miniatura grafu na panelu Dynamo označuje, že je třeba provést výběr:

![](../.gitbook/assets/dynamo\_patharray.png)

* Při spuštění grafu vás průvodce výběrem aplikace FormIt provede nastavením výběrů pro každý uzel SelectFromFormIt počínaje horní částí grafu.
* Po prvním vygenerování se na panelu Vlastnosti aplikace FormIt zobrazí tlačítko pro každý uzel SelectFromFormIt.

![](../.gitbook/assets/dynamo\_selectarraypath.png)

* Kliknutím na tato tlačítka spustíte průvodce výběrem a budete moct změnit výběr použitý k vytvoření konečné geometrie. Po novém výběru se graf automaticky znovu spustí.

### **Tipy, triky a poznámky**

* Uzel SelectFromFormIt pojmenujte tak, aby označoval, jaký typ geometrie je očekáván, například „Výběr hranice pozemku (hrany)“.
  * Můžete vybrat libovolný typ geometrie aplikace FormIt, ale často je nejlepší zahrnout výběr do skupiny aplikace FormIt a [vybrat ji místo nezpracované geometrie](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).
* Pokud potřebujete přesunout výsledky grafu aplikace Dynamo založeného na výběru, je nejlepší nejprve přesunout geometrii výběru a poté znovu spustit graf, který zachytí aktualizovanou geometrii výběru a odpovídajícím způsobem změní své umístění. 
  * Můžete také seskupit výsledky aplikace Dynamo **a** výběr a poté přesunout příslušnou skupinu.
* Při odeslání geometrie aplikace FormIt do aplikace Dynamo budou při vrácení geometrie zpět do aplikace FormIt ztraceny všechny atributy, materiály nebo vnořené skupiny.
* Pokud v aplikaci Dynamo upravujete graf založený na výběru a vybraná geometrie v aplikaci FormIt se změní, bude nutné geometrii znovu vybrat kliknutím na tlačítko Vybrat z aplikace FormIt v uzlu SelectFromFormIt. 
* Při výběru v aplikaci FormIt se použije aktivní [filtr výběru](https://windows.help.formit.autodesk.com/tool-library/select-edge-face-or-object#selection-filtering). Pokud například chcete v aplikaci FormIt vybrat vrcholy, bude nutné je povolit ve filtru výběru.

![](../.gitbook/assets/dynamo\_filterselection.png)

## Další vstupní uzly

K dispozici je široká nabídka vstupních možností pro snadné přizpůsobení grafů aplikace Dynamo v aplikaci FormIt.

### **Uzel FormItLengthString**

V aplikaci FormIt 2022.1.0 nebo novější verzi můžete pomocí uzlu **FormItLengthString** zadat rozměry v libovolném podporovaném typu jednotky aplikace FormIt (stopy–palce, palec, m, cm, mm) bez ohledu na nastavení jednotek aplikace FormIt v aktivním náčrtu.

![](../.gitbook/assets/dynamo\_formitlengthstring.png)

Stejně jako ostatní podporované vstupní uzly se i uzel _FormItLengthString_ zobrazí na paletě Vlastnosti aplikace FormIt, pokud je označen jako Je vstup, a při přejmenování se jeho nový název zobrazí v aplikaci FormIt:

![](../.gitbook/assets/dynamo\_propertiespalette.png)

Každou instanci uzlu _FormItLengthString_ lze použít v libovolném typu jednotky, takže jeden graf aplikace Dynamo může obsahovat kombinaci jednotek, jak je znázorněno výše.

### **Přepínání z čísel na uzel FormItLengthString**

V aplikaci FormIt 2022.1.1 a novějších verzích přepnutí grafu na používání uzlů FormItLengthString (umístěním prvního z nich do grafu) nebo přepnutí grafu na používání pouze čísel (odebráním posledního uzlu FormItLengthString) změní určité chování při úpravách grafu v aplikaci Dynamo:

* Při použití uzlu [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) při úpravách grafu bude přepínání mezi čísly a uzlem _FormItLengthString_, jak je uvedeno výše, vyžadovat nový výběr geometrie pro každý uzel _SelectFromFormIt_, aby byly výsledky v aplikaci FormIt nadále správně škálovány.
* Po umístění prvního uzlu FormItLengthString do grafu budou všechna čísla v grafu určená jako rozměry (včetně vstupů čísel) odkazovat na metry (nativní jednotka aplikace Dynamo).
  * Uzel [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) tuto změnu zohlední a zajistí, že vygenerovaná geometrie v aplikaci FormIt zůstane ve správné velikosti.
  * Naopak, odstraněním všech uzlů FormItLengthString z grafu se čísla přepnout tak, aby odkazovala na nastavení jednotek aplikace FormIt (staré chování).
* Číselný výstup uzlů _FormItLengthString_ bude také v metrech, to však nezmění velikost geometrických výsledků v aplikaci FormIt:

\![](<../.gitbook/assets/dynamo_outputinmeters (1).png>)

### **Další podporované vstupní uzly**

Standardní vstupní uzly aplikace Dynamo se zobrazí na panelu Vlastnosti aplikace FormIt, pokud jsou v aplikaci Dynamo označeny příznakem Je vstup:

* Number Slider
* Integer Slider
* Number
* String
* Přepínače booleovských hodnot

Vstupní uzly můžete přejmenovat (doporučeno pro přehlednost) a jejich nový název se zobrazí v aplikaci FormIt:

\![](<../.gitbook/assets/dynamo_cuboidsize (1).png>)

![](../.gitbook/assets/dynamo\_inputs.png)

## Další výstupní uzly

Různé metody zobrazení negeometrických výsledků z aplikace Dynamo do aplikace FormIt.

### **Uzel Watch**

Uzly Watch označené jako Je výstup se v aplikaci FormIt 2022 a novějších verzích zobrazí na panelu Vlastnosti v části Sledovat výstup uzlů:

\![](<../.gitbook/assets/dynamo_watchnodes (1).png>)

### **Zobrazení oznámení aplikace FormIt**

V aplikaci FormIt 2022.1 nebo novější můžete zobrazit oznámení na straně aplikace FormIt z grafu aplikace Dynamo pomocí uzlu **UI.ShowNotification**: 

![](../.gitbook/assets/dynamo\_notifications.png)

### **Protokolování do konzole aplikace FormIt**

V aplikaci FormIt 2022.1 nebo novější můžete pomocí uzlu **FormIt.ConsoleLog** zaznamenávat další data přímo do konzole aplikace FormIt (okno Výstup skriptu):

![](../.gitbook/assets/dynamo\_logtoconsole.png)

## Uzly možností aplikace FormIt

Mějte pod kontrolou způsob odesílání dat do aplikace FormIt, buď na úrovni jednotlivých geometrií, nebo na úrovni obsahující skupiny.

### **FormItGeometryOptions**

Aplikace FormIt 2022.1 a novější nabízí možnost přizpůsobit způsob odesílání jednotlivých geometrií aplikace Dynamo do aplikace FormIt pomocí uzlů **FormItGeometryOptions**.

* Určete hladinu pro jednotlivé geometrie uvnitř vytvořené skupiny aplikace Dynamo.
* Určete atribut řetězce pro jednotlivé geometrie uvnitř vytvořené skupiny aplikace Dynamo.

Uzly _FormItGeometryOptions_ lze použít před uzlem _SendToFormIt_:

\![](<../.gitbook/assets/dynamo_formitgeometryoptions (1).png>)

### **FormItGroupOptions**

Aplikace FormIt 2022 a novější nabízí možnost přizpůsobit způsob generování skupiny aplikace Dynamo z uzlu _SendToFormIt_ v aplikaci FormIt pomocí uzlů **FormItGroupOptions**.

* Určete, zda uzel SendToFormIt odešle geometrii do aplikace FormIt jako síť nebo objekt.
* Určete hladinu pro skupinu vytvořenou uzlem SendToFormIt.
* Určete atribut řetězce pro skupinu vytvořenou uzlem SendToFormIt.

Můžete použít libovolnou kombinaci uzlů FormItGroupOptions v libovolném pořadí jejich zřetězením:

![](../.gitbook/assets/dynamo\_daisychain.png)

## Uzly rozhraní API jazyka JavaScript

Aplikace FormIt 2022.1 a novější nabízí přístup k rozhraním API jazyka JavaScript a uživatelským funkcím z aplikace Dynamo prostřednictvím dvou nových uzlů:

### **CallJSAPI**

Uzel **CallJSAPI** umožňuje vyvolat rozhraní API jazyka JavaScript aplikace FormIt přímo z aplikace Dynamo.

\![](<../.gitbook/assets/dynamo_calljsapi (1).png>)

Názvy a parametry funkcí naleznete v dokumentaci k jazyku JavaScript, která je rozdělena do dvou částí: [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) a [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (jádro pro modelování).

**CallPluginJS**

Naopak uzel **CallPluginJS** umožňuje vyvolat uživatelské funkce z načteného modulu plug-in nebo fragmentu skriptu, který byl proveden z okna Editor skriptů.

\![](<../.gitbook/assets/dynamo_callpluginjs (1).png>)

## Důležité poznámky

### **Systémové požadavky**

* Chcete-li v aplikaci FormIt použít aplikaci Dynamo, budete potřebovat aplikaci [FormIt pro systém Windows](https://formit.autodesk.com/page/download) verze 17.0 nebo novější.
  * Integrace aplikací FormIt a Dynamo je pravidelně vylepšována novými funkcemi a opravami, takže je vždy nejlepší stáhnout nejnovější aktualizaci, jakmile je k dispozici.
* Budete také potřebovat systém Windows 10. Z technických důvodů již nejsou starší verze systému Windows podporovány.

**Řešení potíží**

* Pokud máte systém s grafickou kartou [NVIDIA nebo AMD](https://www.howtogeek.com/414201/how-to-check-what-graphics-card-gpu-is-in-your-pc/) nebo s více kartami, může být nutné nastavit aplikace FormIt a Dynamo tak, aby používaly vysoce výkonný grafický procesor:
  * _C:/Program Files/Autodesk/FormIt/FormIt.exe_
  * _C:/Program Files/Autodesk/FormIt/DynamoSandbox/FormItDynamoSandbox.exe_
  * Pokud máte kartu NVIDIA, [zkontrolujte, zda máte nainstalovaný ovládací panel NVIDIA](https://whatsabyte.com/blog/find-nvidia-control-panel/).
  * Pomocí ovládacích panelů [NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a\_id/2615/\~/how-do-i-customize-optimus-profiles-and-settings%3F) nebo [AMD](https://www.amd.com/en/support/kb/faq/dh-017) nastavte následující aplikace tak, aby používaly samostatnou grafickou kartu:
* Pokud používáte jiné než anglické národní prostředí, bude možná nutné v nastavení oblasti systému Windows 10 nastavit angličtinu, abyste se vyhnuli problémům s některými uzly aplikace Dynamo:
  * V nabídce Start vyhledejte výraz „jazyk“ a vyberte možnost Nastavení jazyka.
  * V pravé horní části dialogu Jazyk klikněte na správu nastavení jazyka.
  * Klikněte na tlačítko Změnit národní prostředí systému.
  * Vyberte možnost Angličtina (Spojené státy).
* Pokud se vám při práci s malou geometrií nebo čísly v aplikaci FormIt nedaří generovat výsledky grafů, zkuste změnit nastavení měřítka aplikace Dynamo na hodnotu Malé:
  * Nabídka aplikace Dynamo > Předvolby > Obecné > Změna měřítka geometrie > Malé

![](../.gitbook/assets/dynamo\_geometryscaling.png)

### **Získání podpory**

Potřebujete nápovědu k aplikacím FormIt a Dynamo? [Dejte nám vědět na fórech](https://forums.autodesk.com/t5/formit-forum/bd-p/142).
