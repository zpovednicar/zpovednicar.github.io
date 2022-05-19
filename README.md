# Zpovědničář

> Doplňková funkcionalita stránek [Zpovědnice](https://www.zpovednice.eu/), pro všechny smutné lidičky a pro
> ty, kdo jim chtějí pomoci.

Po [jednoduché instalaci](INSTALL.md) jsou uživateli k dispozici rozšiřující možnosti ovládání co a jak
Zpovědnice (ne)zobrazuje. Konfigurační nastavení se ukládají pouze v prohlížeči a skripty na jiných stránkách
k nim nemají přístup. Neodesílají se žádné doplňkové síťové požadavky, ani na Zpovědnici ani nikam jinam,
pracuje se výhradně s informacemi zobrazenými na aktuálně zobrazených stránkách Zpovědnice, konkrétně na/v:

- hlavní straně (přehledu témat)
- detailu tématu
- uživatelském profilu
- návštěvní knize
- perličkách
- statistikách

| Zvýrazňování | Skrývání  | Nastavení |
| ------------ | --------- | --------- |
| ![Highlight](/assets/images/config-highlight.png) | ![Highlight](/assets/images/config-hide.png) | ![Highlight](/assets/images/config-settings.png) |

### Zvýrazňování/skrývání přezdívek a klíčových slov

1. **Přezdívky** lze vybrat ke zvýrazňování/skrývání u každého rozhřešení nebo vzkazu v profilu, anebo pomocí
   formuláře v konfiguraci. Ignoruje se velikost písmen, diakritika a mezery - tzn. zadáním
   např. `To mÁŠ JE dno` se budou zvýrazňovat/skrývat i přezdívky `tomasjedno` atd.
2. **Klíčová slova** lze zadat jen v konfiguraci a ignoruje se pouze velikost písmen (ignorací diakritiky a
   mezer by docházelo k příliš mnoha falešným shodám).

Zvýrazňování i skrývání lze v konfiguraci zapnout i vypnout, aniž by byly uložené seznamy přezdívek/výrazů
dotčeny. Vypnutím zároveň zmizí u rozhřešení/vzkazů ovládací prvky.

- na hlavní straně se **neskrývají** témata, pokud jsou slova určená ke skrývání v těle textu tématu,
  zpracovává se pouze nadpis (jen co je zobrazeno na stránce)
- v detailu tématu skrytá slova nezmizí úplně, pouze se znevýrazní

### Skrývání smazaných komentářů a neregistrovaných uživatelů

Pozůstatky po smazaných komentářích jsou vizuálně obtěžující, zvláště pokud je jich v jednom vlákně mnoho -
lze je tedy plošně skrývat.

Taktéž je možné kompletně vypnout zobrazování komentářů a vzkazů od neregistrovaných uživatelů - což ale
technicky nelze zabezpečit i v přehledu témat, pouze v diskuzích a uživatelských profilech.

### Youtube odkazy, náhledy a inline videa

Obsah umístěný na *Zpovědnici* **stálými uživateli** ("domečkáři" a členy klubu *Zpovědnice*) **je
zvýhodněn**:

1. **Odkazy v textu tématu** - adresy *Youtube* videí v textu tématu jsou transformovány na "klikací" odkazy
2. **Náhledy videí** - na konec tématu nebo rozhřešení s video odkazem se po zapnutí příslušné volby v
   konfiguraci umístí obrázek/obrázky náhledu - po kliknutí se pak nahradí inline přehrávačem videa.

Zobrazení náhledů a přehrávače funguje pro všechny uživatele - ale obsah vkládaný neregistrovanými nebo pod
novým či málo aktivními profily se nijak nemění.

### Používaná doména Zpovědnice

V temných koutech kódu *Zpovědnice* je mix odkazů na EU/CZ domény, což má někdy nepříjemný efekt - pokud je
například uživatel přihlášen ke svému profilu na doméně *www.zpovednice.eu* a klikne v seznamu administrátorů
na odkaz profilu aby do něj napsal zprávu, ocitne se na doméně *www.zpovednice.cz* na které nebude přihlášen.
Taktéž odkazy na jiná témata v diskuzích někdy zavedou na jinou doménu na které není registrovaný uživatel
aktuálně přihlášen.

Stejným způsobem fungují uložené seznamy přezdívek/výrazů pro zvýrazňování nebo skrývání - skripty z "jiných
serverů" na svá data vzájemně "nevidí", což je zároveň:

- **výhoda** - lze tak mít tak na každé doméně *Zpovědnice* jiné seznamy a nastavení
- **nevýhoda** - pro uživatele je snadné zadat omylem např. skrývání nějaké přezdívky na EU doméně, ačkoliv
  běžně používá CZ

Tento problém řeší konfigurační položka **vynutit doménu** - za všech okolností udrží uživatele pouze na
vybraném "serveru", pokud o to stojí a pro per-server nastavení nemá využití.

### Konfigurace a zálohování dat

Konfigurační okno lze vyvolat z menu *Zpovědnice* na hlavní straně, anebo odkudkoli v submenu rozšíření
*Tampermonkey*. Některé prohlížeče nabízejí položku *Tampermonkey* také v kontextovém menu stránky (kliknutí
pravým tlačítkem, nebo dvěmi prsty na touchpadu).

**Všechny změny** v konfiguraci i v seznamech ke zvýrazňování/skrývání **se projeví okamžitě**, aneb:

- v konfiguračním okně není žádné tlačítko "uložit změny"
- cokoli uživatel nastaví v konfiguračním okně anebo v diskuzích/profilech se ihned propaguje na všechny
  stránky *Zpovědnice*, které má na stejné doméně otevřené v jiných záložkách anebo oknech - není tedy třeba
  již otevřené stránky načítat znovu, aby z nich například zmizely komentáře návštěvníka, kterého se uživatel
  rozhodl přestat na *Zpovědnici* vídat

Zálohy jsou primárně určeny pro přenos uložených seznamů mezi vícero počítači, a dále najdou využití pokud se
uživatel rozhodne provést úplný výmaz cache a jiných dat uložených v prohlížeči. Soubory se zálohou jsou
chráněny heslem, které se nikde neukládá. Zálohuje se pouze databáze (uložené přezdívky a výrazy, určené ke
zvýrazňování/skrývání), nikoli ostatní nastavení.

## Licenční ujednání

Projekt je vydán pod nejsvobodnější softwarovou licencí vůbec, [WTFPL](http://www.wtfpl.net/) - nezakládá
žádné povinnosti ani pro koncové uživatele, ani pro případné zájemce o úpravy kódu, a to ať už pro potřebu
vlastní či ve prospěch třetí osoby. Lze ji shrnout jako **dělejte si s tím co chcete**.

## Další vývoj a spolupráce

Blízká budoucnost TODO

- hlášení chyb a nedostatků
- nápady na další rozšíření
- nabídky na spolupráci

**jsou VELMI vítány**.

TODO

## Odkazy

Použité knihovny a technologie, abecedně:

- [Coloris](https://github.com/mdbassit/Coloris)
- [Daypilot Modal](https://modal.daypilot.org/)
- [Dexie](https://dexie.org/)
- [FileSaver](https://github.com/eligrey/FileSaver.js)
- [Papa Parse](https://www.papaparse.com/)
- [Tabby](https://github.com/cferdinandi/tabby/)
- [Tampermonkey](https://www.tampermonkey.net/)
- [Tingle](https://tingle.robinparisi.com/)
