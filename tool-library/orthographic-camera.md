# Ortografická a perspektivní kamera

Aplikace FormIt 2023 obsahuje několik možností ortografické a perspektivní kamery. V plovoucí navigační nabídce jsou k dispozici tlačítka Ortografická, 2bodová perspektiva a 3bodová perspektiva:

![Tlačítka pohledů kamery – 3bodová perspektiva (nahoře), 2bodová perspektiva (uprostřed) a ortografická (dole)](../.gitbook/assets/camera-2point-floating-nav-blurred.png)

### 3bodová perspektiva

* Toto je výchozí perspektivní kamera. Při určitých úhlech kamery se svislé čáry zdánlivě sbíhají v blízkosti horního okraje kamery.
* Poloha kamery nastavená v tomto režimu bude definovat rovinu oříznutí pro ortografickou kameru.
* Při stisknuté klávese Ctrl a přiblížení v tomto režimu bude přiblížení prováděno konstantním tempem, aniž by se kamera při přibližování k objektům zpomalovala.

### 2bodová perspektiva

* Tato kamera je podobná 3bodové perspektivě, ale zajišťuje, že svislé čáry zůstanou svislé.
* Při určitých úhlech kamery se může geometrie jevit jako zkreslená, aby svislé čáry zůstaly vždy svislé.
* Poloha kamery nastavená v tomto režimu bude definovat rovinu oříznutí pro ortografickou kameru.
* Při stisknuté klávese Ctrl a přiblížení v tomto režimu bude přiblížení prováděno konstantním tempem, aniž by se kamera při přibližování k objektům zpomalovala.
* 2bodová perspektiva je také pracovní režim, takže si všimnete, že svislé čáry zůstanou svislé i při změně kamery – to může při určitých úhlech kamery zkreslovat scénu.

![](../.gitbook/assets/camera-2point-working-mode.gif)

### Ortografická

* Režim ortografického promítání vhodný pro diagramy, 3D detailní výkresy a další neperspektivní grafiku.
* Poloha kamery nastavená v jednom ze dvou perspektivních režimů definuje rovinu oříznutí pro ortografickou kameru. Pokud se scéna neočekávaně ořízne, přepněte do perspektivního režimu, oddalte scénu a poté přepněte zpět do ortografického režimu.

### Použití režimů

Všechny režimy kamery jsou plnohodnotné pracovní režimy s přístupem k navigačním a kreslicím nástrojům v libovolném režimu, který upřednostňujete. V nabídce je možné snadno přepínat mezi různými kamerami. 

![Přepínání tří různých režimů kamery: 3bodová perspektiva, 2bodová perspektiva a ortografická.](../.gitbook/assets/perspective-gif.gif)

Po výběru kamery budou všechny ostatní nástroje kamery respektovat aktuální režim. Například možnost **Zarovnat kameru s plochou** zarovná ortografickou kameru s plochou, čímž vznikne ortografický bokorysný pohled.

Pokud ručně přejdete k přednastavenému ortografickému pohledu, například hornímu pohledu nebo přednímu pohledu, ortografická kamera se k této poloze přichytí, což usnadní používání těchto přednastavených pohledů.

![](../.gitbook/assets/orthoorienttoface.gif)

### Axonometrická kamera

Kromě ortografické a perspektivní kamery, které jsou k dispozici na panelu nástrojů navigace, nabízí aplikace FormIt axonometrickou kameru dostupnou pouze v nabídce Pohled (pouze v systému Windows):

<figure><img src="../.gitbook/assets/AxonometricMenu (2).png" alt=""><figcaption></figcaption></figure>

Výběrem této možnosti umístíte kameru do axonometrického pohledu:

<figure><img src="../.gitbook/assets/Axonometric (2).png" alt=""><figcaption></figcaption></figure>

### Šikmá kamera

Aplikace FormIt také nabízí šikmou kameru, která je dostupná pouze v nabídce Pohled (pouze v systému Windows):

<figure><img src="../.gitbook/assets/ObliqueMenu.png" alt=""><figcaption></figcaption></figure>

Výběrem této možnosti umístíte kameru do šikmého pohledu:

<figure><img src="../.gitbook/assets/Oblique (2).png" alt=""><figcaption></figcaption></figure>
