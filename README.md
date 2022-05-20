# Zpovědničář

> Doplňková funkcionalita stránek [Zpovědnice](https://www.zpovednice.eu/), pro všechny smutné lidičky a pro
> ty, kdo jim chtějí pomoci.

Po [jednoduché instalaci](INSTALL.md) jsou uživateli k dispozici rozšiřující možnosti ovládání co a jak
*Zpovědnice* (ne)zobrazuje. Konfigurační nastavení se ukládají pouze v prohlížeči a skripty na jiných
stránkách k nim nemají přístup. Neodesílají se žádné doplňkové síťové požadavky, ani na *Zpovědnici* ani nikam
jinam, pracuje se výhradně s informacemi zobrazenými na aktuálně zobrazených stránkách *Zpovědnice*, konkrétně na/v:

- hlavní straně (přehledu témat)
- detailu tématu
- uživatelském profilu
- návštěvní knize
- perličkách
- statistikách

| Zvýrazňování                                      | Skrývání                                     | Nastavení                                        |
|---------------------------------------------------|----------------------------------------------|--------------------------------------------------|
| ![Highlight](/assets/images/config-highlight.png) | ![Highlight](/assets/images/config-hide.png) | ![Highlight](/assets/images/config-settings.png) |

<details><summary><strong>Zvýrazňování/skrývání přezdívek a klíčových slov</strong></summary>
<ol>
    <li><strong>Přezdívky</strong> lze vybrat ke zvýrazňování/skrývání u každého rozhřešení nebo vzkazu v profilu,
        anebo pomocí formuláře v konfiguraci. Ignoruje se velikost písmen, diakritika a mezery - tzn. zadáním
        např. `To mÁŠ JE dno` se budou zvýrazňovat/skrývat i přezdívky `tomasjedno` atd.</li>
    <li><strong>Klíčová slova</strong> lze zadat jen v konfiguraci a ignoruje se pouze velikost písmen (ignorací
        diakritiky a mezer by docházelo k příliš mnoha falešným shodám).</li>
</ol>

<p>
Zvýrazňování i skrývání lze v konfiguraci zapnout i vypnout, aniž by byly uložené seznamy přezdívek/výrazů
dotčeny. Vypnutím zároveň zmizí u rozhřešení/vzkazů ovládací prvky.
</p>

<ul>
    <li>na hlavní straně se <strong>neskrývají</strong> témata, pokud jsou slova určená ke skrývání v těle textu
        tématu, zpracovává se pouze nadpis (jen co je zobrazeno na stránce)</li>
    <li>v detailu tématu skrytá slova nezmizí úplně, pouze se znevýrazní</li>
</ul>
</details>

<details><summary><strong>Skrývání smazaných komentářů a neregistrovaných uživatelů</strong></summary>
<p>
Pozůstatky po smazaných komentářích jsou vizuálně obtěžující, zvláště pokud je jich v jednom vlákně mnoho -
lze je tedy plošně skrývat.
</p>

<p>
Taktéž je možné kompletně vypnout zobrazování komentářů a vzkazů od neregistrovaných uživatelů - což ale
technicky nelze zabezpečit i v přehledu témat, pouze v diskuzích a uživatelských profilech.
</p>
</details>

<details><summary><strong>Youtube odkazy, náhledy a inline videa</strong></summary>
<p>
Obsah umístěný na <i>Zpovědnici</i> <strong>stálými uživateli</strong> ("domečkáři" a členy klubu
<i>Zpovědnice</i>) <strong>je zvýhodněn</strong>:
</p>

<ol>
    <li><strong>Odkazy v textu tématu</strong> - adresy <i>Youtube</i> videí v textu tématu jsou transformovány
        na "klikací" odkazy</li>
    <li><strong>Náhledy videí</strong> - na konec tématu nebo rozhřešení s video odkazem se po zapnutí příslušné
        volby v konfiguraci umístí obrázek/obrázky náhledu - po kliknutí se pak nahradí inline přehrávačem videa.</li>
</ol>

<p>
Zobrazení náhledů a přehrávače funguje pro všechny uživatele - ale obsah vkládaný neregistrovanými nebo pod
novým či málo aktivními profily se nijak nemění.
</p>
</details>

<details><summary><strong>Používaná doména Zpovědnice</strong></summary>
<p>
V temných koutech kódu <i>Zpovědnice</i> je mix odkazů na EU/CZ domény, což má někdy nepříjemný efekt - pokud
je například uživatel přihlášen ke svému profilu na doméně <i>www.zpovednice.eu</i> a klikne v seznamu
administrátorů na odkaz profilu aby do něj napsal zprávu, ocitne se na doméně <i>www.zpovednice.cz</i> na které
nebude  přihlášen. Taktéž odkazy na jiná témata v diskuzích někdy zavedou na jinou doménu na které není
registrovaný uživatel aktuálně přihlášen.
</p>

<p>
Stejným způsobem fungují uložené seznamy přezdívek/výrazů pro zvýrazňování nebo skrývání - skripty z "jiných
serverů" na svá data vzájemně "nevidí", což je zároveň:
</p>

<ul>
    <li><strong>výhoda</strong> - lze tak mít tak na každé doméně <i>Zpovědnice</i> jiné seznamy a nastavení</li>
    <li><strong>nevýhoda</strong> - pro uživatele je snadné zadat omylem např. skrývání nějaké přezdívky na EU
        doméně, ačkoliv
        běžně používá CZ</li>
</ul>

<p>
Tento problém řeší konfigurační položka <strong>vynutit doménu</strong> - za všech okolností udrží uživatele
pouze na vybraném "serveru", pokud o to stojí a pro per-server nastavení nemá využití.
</p>
</details>

<details><summary><strong>Konfigurace a zálohování dat</strong></summary>
<p>
<strong>Všechny změny</strong> v konfiguraci i v seznamech ke zvýrazňování/skrývání <strong>se projeví
okamžitě</strong>, aneb:
</p>

<ul>
    <li>v konfiguračním okně není žádné tlačítko "uložit změny"</li>
    <li>cokoli uživatel nastaví v konfiguračním okně anebo v diskuzích/profilech se ihned propaguje na všechny
        stránky <i>Zpovědnice</i>, které má na stejné doméně otevřené v jiných záložkách anebo oknech - není tedy
        třeba již otevřené stránky načítat znovu, aby z nich například zmizely komentáře návštěvníka, kterého
        se uživatel rozhodl přestat na <i>Zpovědnici</i> vídat</li>
</ul>

<p>
Zálohy jsou primárně určeny pro přenos uložených seznamů mezi vícero počítači, a dále najdou využití pokud se
uživatel rozhodne provést úplný výmaz cache a jiných dat uložených v prohlížeči. Soubory se zálohou jsou
chráněny heslem, které se nikde neukládá. Zálohuje se pouze databáze (uložené přezdívky a výrazy, určené ke
zvýrazňování/skrývání), nikoli ostatní nastavení.
</p>
</details>

## Další vývoj a spolupráce

Všechny nově přidané funkce budou po aktualizaci skriptu ve stavu <strong>vypnuto</strong>. Plánované
funkcionality, dosud
neopravené chyby atd. jsou k nalezení [zde](https://github.com/zpovednicar/zpovednicar/issues) přičemž veškerá
hlášení chyb a nedostatků, nápady na další rozšíření, nabídky na spolupráci či rovnou pull requesty s
doplněními a změnami <strong>jsou VELMI vítány</strong>, stejně jako zájem a schopnosti zapojit se do projektu
s plnými
právy k vydávání nových verzí, aktualizacím produkčního serveru a podobně.

<strong>Cílem tohoto projektu NENÍ:</strong>

- měnit zásadním způsobem design <i>Zpovědnice</i>, blokovat zobrazování reklam a podobně
- aktualizovat v prohlížeči/databázi data ze <i>Zpovědnice</i> na pozadí (a tím plýtvat jejími zdroji a
  výkonem)
- provádět pod pokličkou jakékoli operace s uživatelskými daty ani sbírat informace o jejich činnosti

## Licenční ujednání

Projekt je vydán pod nejsvobodnější softwarovou licencí vůbec, [WTFPL](http://www.wtfpl.net/) - nezakládá
žádné povinnosti ani pro koncové uživatele, ani pro případné zájemce o úpravy kódu, a to ať už pro potřebu
vlastní či ve prospěch třetí osoby. Lze ji shrnout jako <strong>dělejte si s tím co chcete</strong>.

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
