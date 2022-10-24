# Předpoklady a instalace

## Stažení a instalace

* Stáhněte si nejnovější verzi aplikace [FormIt pro systém Windows](https://formit.autodesk.com/page/download).
* Přihlaste se pomocí účtu Autodesk nebo [si zde vytvořte bezplatný účet Autodesk](https://accounts.autodesk.com).
* Součástí aplikace Revit 2017 a novějších verzí je doplněk FormIt pro aplikaci Revit. Tento doplněk si také můžete stáhnout a ručně nainstalovat [z našich webových stránek](https://formit.autodesk.com/page/formit-revit).

Nastavení aplikace FormIt na úrovni aplikace se nachází ve složce Computer\\HKEY_CURRENT_USER\\SOFTWARE\\Autodesk\\FormIt 360\\.

## Doporučená konfigurace systému

| Požadavek                    | Detaily                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Operační systém**           | <p>Microsoft® Windows® 8, 8.1, 10 nebo 11.</p><p><em>Poznámka: Software Parallels Desktop není oficiálně podporován kvůli sníženému výkonu a problémům s grafikou v ovladačích OpenGL.</em></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **CPU**                        | <p>Procesor Intel® Pentium®, Xeon® nebo i-Series nebo ekvivalentní procesor AMD® s technologií SSE2.</p><p>Doporučuje se nejvyšší dostupná kategorie povolené rychlosti procesoru.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Paměť**                     | Minimálně 4 GB paměti RAM, doporučeno 8 GB nebo více.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Grafická karta (GPU)**           | <p>Je vyžadována samostatná grafická karta NVIDIA nebo AMD podporující standard OpenGL 3.3. Důrazně doporučujeme podporu standardu OpenGL 4.2.</p><p>U systémů s výměnnými grafickými kartami postupujte podle pokynů výrobce, abyste zajistili, že aplikace FormIt vždy použije vyhrazený grafický procesor pro dosažení nejlepšího výkonu. Viz pokyny pro grafické karty <a href="https://www.amd.com/en/support/kb/faq/dh-017">AMD</a> a <a href="http://nvidia.custhelp.com/app/answers/detail/a_id/2615/kw/manage%203d%20settings/related/1">NVIDIA</a>.</p><p>Pro dosažení nejlepšího výkonu a spolehlivosti se ujistěte, že ovladače grafické karty jsou aktualizované z webu výrobce nebo služby Windows Update.</p><p>Aplikace FormIt zobrazí při spuštění zprávu, pokud nemůže použít vaši grafickou kartu kvůli zastaralým ovladačům nebo jiným problémům. Pokud se po aktualizaci ovladačů nepodaří aplikaci FormIt spustit, <a href="https://forums.autodesk.com/t5/formit-forum/bd-p/142">obraťte se na diskusní fóra</a>.</p> |
| **Místo na disku**                 | 1 GB volného místa na disku.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Konektivita a licencování** | <p>Pro přihlášení k účtu Autodesk je při prvním spuštění aplikace FormIt vyžadováno připojení k internetu.</p><p>Připojení k internetu je vyžadováno také k načtení modulů plug-in při spuštění aplikace FormIt. Pokud není při spuštění zjištěno připojení k internetu, aplikace se spustí bez modulů plug-in.</p><p>Ke spuštění aplikace FormIt Pro v systému Windows je vyžadován účet Autodesk s cloudovým předplatným aplikace FormIt Pro. Aplikace FormIt Pro je k dispozici jako součást <a href="https://www.autodesk.com/collections/architecture-engineering-construction/overview"><strong>sady Autodesk AEC Collection</strong></a>.</p>                                                                                                                                                                                                                                                                                                   |

## Offline přístup

Při prvním spuštění aplikace FormIt pro Windows musíte být připojeni k internetu, aby mohla být ověřena platnost licence. Po prvním přihlášení můžete aplikaci používat offline po dobu 30 dní. Poté budete muset přejít do režimu online, aby bylo možné licenci znovu ověřit.

Při použití aplikace FormIt pro systém Windows v režimu offline budou omezeny některé funkce:

* Nástroj Nastavit umístění nebude funkční, protože vyžaduje připojení k internetu kvůli načtení satelitních a terénních dat ze služby Bing Maps.
  * Jakákoli existující satelitní a terénní data, která se již v modelu nacházejí z předchozí online relace, však zůstanou zachována.
* Nebudou načteny žádné moduly plug-in, včetně nástroje Plugin Manager, protože při každém spuštění aplikace získají nejnovější kód z GitHubu.
  * Řešení: Pokud načtete všechny moduly plug-in, když jste online, a ponecháte relaci aplikace FormIt spuštěnou, když přejdete do režimu offline, dříve načtené moduly plug-in zůstanou zachovány a budou normálně fungovat.
* Nenačtou se vzorové materiály, protože se nacházejí na serveru hostovaném v cloudu.
  * Řešení: Při připojení k internetu přejděte do složek s kategoriemi vzorových materiálů. Složky budou staženy a uloženy v počítači a budete je moct později otevřít v režimu offline.
* Nebudete moci ukládat soubory do služby Autodesk Docs ani je z ní otevírat, a to ani z knihovny obsahu.

## Doporučená nastavení DPI v systému Windows

Aplikace FormIt pro systém Windows funguje nejlépe, pokud je v systému Windows nastavena obrazovka displeje na 125 % nebo menší hodnotu škálování DPI.

V systému Windows 10 lze tuto změnu provést následujícím způsobem:

* V nabídce Start vyhledejte položku Zobrazení a vyberte možnost Změnit nastavení zobrazení.
* Vyberte obdélník představující monitor, který budete používat s aplikací FormIt.
* V části Měřítko a rozložení otevřete rozevírací seznam Velikost textu, aplikací a dalších položek a vyberte hodnotu 125 % nebo nižší.

## Řešení potíží

### Chyba systému Windows 10 Pro N

Pokud používáte aplikaci FormIt v systému Windows 10 Pro N verze 1909 nebo novější, může se zobrazit následující chybová zpráva:

![Soubor FormIt.exe – systémová chyba v systému Windows 10](<../.gitbook/assets/windows 10 error message.png>)

Důvodem je známý problém s některými verzemi systému Windows 10 Pro N. Chcete-li se této chybě vyhnout, stáhněte si balíček Media Feature Pack pro svou verzi systému Windows 10: [seznam balíčků Media Feature Pack pro verze systému Windows N](https://support.microsoft.com/en-us/topic/media-feature-pack-list-for-windows-n-editions-c1c6fffa-d052-8338-7a79-a4bb980a700a).

### Nelze se přihlásit

Při pokusu o přihlášení k účtu v aplikaci FormIt může dialog přihlášení přestat reagovat, což vám zabrání pokračovat. Pokud k tomu dojde, bude pravděpodobně nutné v síťové bráně firewall odblokovat soubor *.autodesk.com. Požádejte o pomoc oddělení IT.
