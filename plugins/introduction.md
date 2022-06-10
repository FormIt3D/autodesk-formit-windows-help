# Úvod k modulům plug-in

![](../.gitbook/assets/gg4.gif)

Moduly plug-in jsou uživatelské softwarové doplňky, které rozšiřují základní funkce aplikace FormIt. Moduly plug-in mohou vylepšit, rozšířit a zjednodušit pracovní postupy 3D modelování v aplikaci FormIt.&#x20;

Moduly plug-in lze použít ke generování objektů, úpravám existujících objektů nebo extrahování informací o objektu. Moduly plug-in mohou také využívat pokročilá webová rozhraní k zobrazování dat a poskytování ovládacích prvků a vstupů přímo v aplikaci.&#x20;

## Přístup k modulům plug-in

Moduly plug-in jsou dostupné v nástroji [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) v aplikaci FormIt ve verzi pro počítač a web, pokud jste připojeni k internetu. Moduly plug-in se skládají z řady souborů a složek, které jsou uloženy na GitHubu (nebo na místním serveru, pokud si vytváříte vlastní).&#x20;

![](../.gitbook/assets/c17.PNG)

### Moduly plug-in vyžadují přístup k internetu

Externí moduly plug-in (moduly plug-in, které nejsou hostovány místně) vyžadují k počátečnímu načtení připojení k internetu, což znamená:

* Externí moduly plug-in nebudou načteny, pokud při spuštění aplikace FormIt není zjištěno připojení k internetu. Po načtení mohou některé externí moduly plug-in pro danou relaci pokračovat v práci v režimu offline, ale jiné se mohou přerušit, dokud nebude obnoveno připojení.&#x20;
* Externí moduly plug-in načítají nejnovější kód ze serveru při každém spuštění, takže jejich funkce se aktualizují vždy, když autor publikuje změnu. Moduly plug-in se načítají asynchronně, což znamená, že pořadí modulů plug-in v rozhraní aplikace FormIt se může v každé nové relaci měnit.

## Open Source

Moduly plug-in jsou open-source, díky čemuž můžete bezplatně používat moduly plug-in v nástroji [Plugin Manager](how-to-use-plug-ins.md#plugin-manager), snadno publikovat a sdílet vlastní moduly plug-in a vyhledávat další moduly plug-in na GitHubu a zkoumat, jak byly vytvořeny.&#x20;

Pokud jste vývojář a chcete získat další informace o publikování modulů plug-in, přečtěte si část [Hostování modulu plug-in na GitHubu](how-to-develop-plugins/advanced-development/hosting-a-plugin-on-github.md).&#x20;

Chcete-li vytvořit modul plug-in pro soukromé použití, můžete jej vytvořit a hostovat pomocí místní služby. Další informace naleznete v části [Používání integrovaného vývojového prostředí. ](how-to-develop-plugins/advanced-development/using-an-ide.md)

![](../.gitbook/assets/c18.PNG)



## Kontaktujte nás

Pokud potřebujete pomoc s moduly plug-in pro aplikaci FormIt, napište nám na [fórum aplikace FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=en).

![](../.gitbook/assets/c19.PNG)

&#x20;

&#x20;
