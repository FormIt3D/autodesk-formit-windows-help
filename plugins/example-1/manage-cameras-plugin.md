# Modul plug-in Manage Cameras

_V této kapitole si ukážeme několik modulů plug-in, které jsou součástí aplikace FormIt, a provedeme několik vylepšení souboru_ _**Encode Campus Sample Model.axm**. Pokud jste tak ještě neučinili, můžete si soubor stáhnout z _[_datové sady k příručce Základy aplikace FormIt, Část II_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip)__

V celé příručce jsme používali scény jako cenné nástroje pro navigaci a řízení viditelnosti v celém modelu. Tento modul plug-in umožňuje zobrazit a upravit výšku aktuální kamery, exportovat kamery pro každou scénu jako 3D objekty a kopírovat tyto scény mezi modely.

1 – Nejprve upravíme scénu **Eye Level – Long Alley**, aby její kamera byla skutečně v úrovni očí:

1. Pokud již není k dispozici, vraťte se do scény **Eye Level – Long Alley** tak, že na ni dvakrát kliknete na **paletě Scény**.
2. Kliknutím na kameru s ikonou ozubeného kola otevřete **paletu Manage Cameras**.
3. Změňte parametr **Height Above Ground** (Výška nad terénem) na hodnotu **5’-8"**.

![](<../../.gitbook/assets/6 (6) (1).png>)

_**Poznámka:**_ _Pokud má model podlaží, tento modul plug-in také zobrazí výšku nad nejbližším podlažím pod_ _**hlavní kamerou**._

2 – Poté postupujte následovně:

1. Přejděte zpět na **paletu Scény**.
2. Ujistěte se, že je scéna **Eye Level – Long Alley** stále vybrána (v opačném případě ji vyberte jedním kliknutím).
3. Kliknutím na tlačítko **Aktualizovat scénu** uložte novou výšku kamery do této scény.

![](<../../.gitbook/assets/7 (1) (1).png>)

_**Poznámka:**_ _Úhel a polohu kamery scény můžete také upravit přepnutím tlačítka_ _**Upravit kamery scény**_ _v horní části palety_ _**Scény**_ _(mezi tlačítky pro aktualizaci a přehrávání)._

3 – Nyní vyexportujeme scény do nového modelu. Nejprve je nutné vytvořit objekty kamery pro všechny scény pomocí modulu plug-in **Manage Cameras**:

1. Znovu otevřete **paletu Manage Cameras**.
2. Ujistěte se, že je zaškrtnuto políčko **Copy Cameras to Clipboard** (Kopírovat kamery do schránky).
3. Klikněte na tlačítko **Export Scenes to Cameras** (Exportovat scény do kamer). Export může trvat několik sekund.
4. Pokud celá kreslicí plocha zbělela, je to proto, že **hlavní kamera** byla zarovnána s jednou z kamer scény. **Oddalte (Z)** pohled tak, abyste viděli 3 hlavní budovy a nově vytvořené objekty kamery. Všimněte si, že objekty kamery jsou automaticky umístěny do jedné velké skupiny s názvem **Kamery**. Uvnitř této skupiny je každá jednotlivá kamera umístěna do vlastní skupiny se stejným názvem jako scény, ze kterých byla vytvořena.

![](<../../.gitbook/assets/8 (7) (1).png>)

4 – Zkopírujme tyto scény do nového modelu. Vzhledem k tomu, že data kamery byla uložena do schránky, stačí provést jen pár kroků:

1. **Uložte** **(Ctrl+S)** aktuální model a zavřete jej.
2. Vytvořte nový prázdný náčrt výběrem možnosti **Nový náčrt (Ctrl+N)** v rozevíracím seznamu **Soubor** na panelu **Hlavní nabídka**.
3. Otevřete modul plug-in **Manage Cameras**, pokud ještě není otevřený, a ujistěte se, že je zaškrtnuta možnost **Look for Cameras on Clipboard** (Hledat kamery ve schránce).
4. Kliknutím na tlačítko **Import Scenes from Cameras** (Importovat scény z kamer) v dolní části modulu plug-in importujte scény z našeho druhého modelu. Chcete-li provést kontrolu, otevřete **paletu Scény** nebo zapněte hladinu **Kamera**. Uvidíte, že do tohoto modelu byly importovány všechny scény a 3D objekty kamery.

![](<../../.gitbook/assets/9 (7) (1).png>)
