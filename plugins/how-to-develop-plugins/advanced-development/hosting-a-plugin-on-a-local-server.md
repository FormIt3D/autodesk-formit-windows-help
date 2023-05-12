# Hostování modulu plug-in na místním serveru

Před zobrazením náhledu klonovaného modulu plug-in v aplikaci FormIt je nutné jej hostovat na místním serveru.

### **Zobrazení terminálu v integrovaném vývojovém prostředí**

Místo v samostatném okně terminálu můžete server spustit uvnitř aplikace Visual Studio Code. **** Před spuštěním terminálu se ujistěte, že je v aplikaci Visual Studio Code otevřena správná složka.

Klikněte na nabídku View > Terminal (Zobrazit > Terminál), nebo použijte klávesovou zkratku Ctrl + \`.

![](<../../../.gitbook/assets/image (11) (1).png>)

### Nastavení serveru HTTP

Dobře fungující server HTTP je server [http-server](https://www.npmjs.com/package/http-server)společnosti npm.

Nejprve je nutné stáhnout a nainstalovat prostředí [NodeJS](https://nodejs.org/en/), pokud již není nainstalováno.

Pokud v následujících krocích narazíte na chyby, zkuste restartovat počítač a dokončit instalaci NodeJS.

Zadáním následujícího příkazu do příkazového řádku globálně nainstalujte _http-server_ společnosti npm (jednorázová instalace).

* `npm install http-server -g`

![](<../../../.gitbook/assets/image (47).png>)

### Spuštění místního serveru

Po dokončení instalace zadejte v terminálu následující příkaz, který spustí npm http-server:

* `http-server`

![](<../../../.gitbook/assets/image (84).png>)

Tip 1: V případě problémů se spuštěním http-serveru (instalovaného globálně nebo místně) jej můžete spustit přímo prostřednictvím npx:

* `npx http-server`

Tip 2: Pokud uživatelé systému Windows 10 nebo 11 narazí při spuštění skriptu v novém počítači na chybu, může to být způsobeno zakázaným nastavením. Opravte problém následujícím způsobem:

* Spusťte skript PowerShell jako správce.
* Zadejte: `Set-ExecutionPolicy RemoteSigned`

### Vývoj pro webovou aplikaci FormIt

Chcete-li vytvářet moduly plug-in pro webovou aplikaci FormIt, jednoduše spusťte následující příkaz:

* `http-server --cors`

![](<../../../.gitbook/assets/image (10) (1).png>)

### Ověření serveru

Server můžete ověřit přechodem na následující adresu ve webovém prohlížeči:

* http://localhost:8080

V okně prohlížeče by se měly zobrazit soubory ve složce projektu.

**Pokud používáte jiný webový server než npm, může se výchozí adresa nebo port lišit.

![](<../../../.gitbook/assets/image (41).png>)
