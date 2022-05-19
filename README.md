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

1. **Přezdívky** lze vybrat ke zvýrazňování u každého rozhřešení nebo vzkazu v profilu, anebo pomocí formuláře v konfiguraci. Ignoruje se velikost písmen, diakritika a mezery - tzn. zadáním např. `To mÁŠ JE dno` se budou zvýrazňovat/skrývat i přezdívky `tomasjedno` atd.
2. **Klíčová slova** lze zadat jen v konfiguraci a ignoruje se pouze velikost písmen (ignorací diakritiky a mezer by docházelo k příliš mnoha falešným shodám).

Zvýrazňování i skrývání lze v konfiguraci zapnout i vypnout, aniž by byly uložené seznamy přezdívek/výrazů dotčeny. Vypnutím zároveň zmizí u rozhřešení/vzkazů ovládací prvky.

- na hlavní straně se **neskrývají** témata, pokud jsou slova určená ke skrývání v těle textu, zpracovává se pouze nadpis (jen co je zobrazeno na stránce)
- v detailu tématu skrytá slova nezmizí úplně, pouze se znevýrazní

### Skrývání smazaných komentářů a neregistrovaných uživatelů

TODO

### Youtube odkazy, náhledy a inline videa

1. **Odkazy v textu tématu** TODO
2. **Náhledy videí** TODO

### Používaná doména Zpovědnice

TODO

### Konfigurace

TODO

## Licenční ujednání

Projekt je vydán pod nejsvobodnější softwarovou licencí vůbec, [WTFPL](http://www.wtfpl.net/) - nezakládá
žádné povinnosti ani pro koncové uživatele, ani pro případné zájemce o úpravy kódu, a to ať už pro potřebu
vlastní či ve prospěch třetí osoby. Lze ji shrnout jako **dělejte si s tím co chcete**.

## Další vývoj a spolupráce

TODO

## Odkazy

Použité knihovny a technologie, abecedně:

- [Coloris](https://github.com/mdbassit/Coloris)
- [Daypilot Modal](https://modal.daypilot.org/)
- [Dexie](https://dexie.org/)
- [FileSaver](https://github.com/eligrey/FileSaver.js)
- [Papa Parse](https://www.papaparse.com/)
- [Tabby](https://github.com/cferdinandi/tabby/)
- [Tingle](https://tingle.robinparisi.com/)
- [Tampermonkey](https://www.tampermonkey.net/)
- Vanilla JS