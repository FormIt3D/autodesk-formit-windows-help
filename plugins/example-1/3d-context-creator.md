# 3D Context Creator 

![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## O co se jedná?

3D Context Creator je snadno použitelný modul plug-in, který vytvoří 3D kontextové budovy v aplikaci FormIt. 

Tento modul plug-in vám pomůže vizualizovat pozemek projektu v okolním kontextu a přijímat informovaná rozhodnutí v rané fázi procesu návrhu.

Tento modul plug-in načítá data ze služby [Open Street Map](https://www.openstreetmap.org/about) a pomáhá je transformovat do geometrie aplikace FormIt. Zdrojový kód pro tento modul plug-in je k dispozici na webu [Github](https://github.com/matterlab-co/FormIt-Context-Plugin).

## Jak se používá

Chcete-li jej nainstalovat, jednoduše zapněte přepínač doplňku v nástroji Plugin Manager, jako u jakéhokoli jiného doplňku.

![](../../.gitbook/assets/contextcreator3.png)

Po přepnutí by se měl modul plug-in zobrazit v pravé části aplikace a měl by být připraven k použití.

![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

Pokud váš pozemek ještě nemá umístění, můžete kliknutím na odkaz **Nastavit umístění...** nastavit umístění a definovat hranici, která bude použita pro generování 3D kontextu.

Po nastavení umístění se v modulu plug-in 3D Context Creator aktualizuje aktuální umístění a tlačítko bude aktivní:

![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

3D Context Creator jednoduše použije rozsah satelitního snímku k vytvoření 3D kontextu. Stačí kliknout na položku **Generovat 3D kontext**.

V závislosti na rozsahu satelitního snímku a složitosti budov může generování chvíli trvat.

3D kontextové budovy budou automaticky umístěny do instance skupiny a umístěny na hladinu s názvem Kontextové budovy. Pomocí této hladiny můžete přepínat viditelnost kontextu.

![](<../../.gitbook/assets/3D Context Creator_layers.png>)

![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

Pokud se později rozhodnete změnit umístění nebo upravit rozsah satelitního snímku, můžete znovu kliknout na tlačítko **Generovat 3D kontext** a znovu vygenerovat budovy. 

_Upozorňujeme, že nově vytvořený kontext nahradí instanci skupiny obsahující budovy novou instancí, takže veškeré změny provedené v budovách budou ztraceny._ Chcete-li tomu zabránit, můžete zrušit seskupení kontejneru kontextu a poté jej znovu seskupit.

## **Některé příklady**

Zkuste uhodnout, která známá města jsou zobrazena v následujících kontextech:

![](<../../.gitbook/assets/image (2) (1).png>)

![](<../../.gitbook/assets/image (34).png>)

![](<../../.gitbook/assets/image (13) (1) (1).png>)

![](<../../.gitbook/assets/image (59).png>)
