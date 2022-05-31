# Zpovědničář

> Doplňková funkcionalita stránek [Zpovědnice](https://www.zpovednice.eu/), pro všechny smutné lidičky a pro
> ty, kdo jim chtějí pomoci.

Po [jednoduché instalaci](INSTALL.md) jsou uživateli k dispozici rozšiřující možnosti ovládání co a jak
*Zpovědnice* (ne)zobrazuje. Konfigurační nastavení se ukládají pouze v prohlížeči a skripty na jiných
stránkách k nim nemají přístup. V tuto chvíli (viz
[další vývoj](https://zpovednicar.github.io/#dal%C5%A1%C3%AD-v%C3%BDvoj-a-spolupr%C3%A1ce)) se neodesílají
žádné doplňkové síťové požadavky, ani na *Zpovědnici* ani nikam jinam, pracuje se výhradně s informacemi
zobrazenými na aktuálně zobrazených stránkách *Zpovědnice*, konkrétně na/v:

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
    <li><strong>Přezdívky</strong> lze vybrat ke zvýrazňování/skrývání v detailu každého tématu, u
        rozhřešení, v profilu či ve vzkazu, anebo pomocí formuláře v konfiguraci. Ignoruje se velikost písmen,
        diakritika a mezery - tzn. zadáním např. `To mÁŠ JE dno` se budou zvýrazňovat/skrývat i přezdívky
        `tomasjedno` atd.</li>
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

<details><summary><strong>Odkazy otevírané v nových oknech nebo záložkách</strong></summary>
<p>
Řada odkazů na jiné stránky <i>Zpovědnice</i> se otevírá v nových oknech nebo záložkách, pro uživatele kterým
to nevyhovuje a chtějí se k tomu případně rozhodnout příležitostně a pomoci si klávesou CTRL je to zbytečně
obtěžující. V konfiguraci je tedy možné nastavit, aby se všechny odkazy otevíraly ve stejném okně.
</p>
</details>

<details><summary><strong>Profilové obrázky z jiného serveru, včetně animovaných</strong></summary>
<p>
Profilové obrázky jsou omezeny typem souboru (JPEG) takže nelze použí ani průhlednost, ani animaci. Pokud si
uživatel zapne volbu <i>Nahrazovat obrázek v profilu</i> a navštíví profil, ve kterém jeho majitel v položce
<i>Oblíbené WWW</i> zadal plnou internetovou adresu k obrázku v podporovaném formátu (apng, gif, jpg, jpeg,
jfif, pjpeg, pjp, png, svg, webp), profilový obrázek se jím nahradí a bude na něj lze kliknout (pro zobrazení
jeho cílové adresy), přičemž se při tvorbě odkazu automaticky zohlední výše popsané nastavení <i>Odkazy otevřít
ve stejném okně</i>.
</p>
</details>

<details><summary><strong>Youtube odkazy, náhledy a inline videa</strong></summary>
<p>
<ol>
    <li><strong>Odkazy v textu tématu</strong> - adresy <i>Youtube</i> videí v textu tématu jsou transformovány
        na "klikací" odkazy</li>
    <li><strong>Náhledy videí</strong> - na konec tématu nebo rozhřešení s video odkazem se po zapnutí příslušné
        volby v konfiguraci umístí obrázek/obrázky náhledu - po kliknutí se pak nahradí inline přehrávačem videa.</li>
</ol>
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

Všechny nově přidané funkce s potenciálem skrývat obsah *Zpovědnice* budou po aktualizaci skriptu ve stavu
**vypnuto**. Do budoucna se počítá i s realtime vlastnostmi, ale uživatel je **vždy** bude muset
nejdříve zapnout v konfiguraci a/nebo odsouhlasit. Plánované  funkcionality, dosud neopravené chyby atd. jsou
k nalezení [zde](https://github.com/zpovednicar/zpovednicar/issues), přičemž veškerá hlášení chyb a nedostatků,
nápady na další rozšíření, nabídky na spolupráci či rovnou pull requesty s doplněními a změnami <strong>jsou
VELMI vítány</strong>, stejně jako zájem a schopnosti zapojit se do projektu s plnými právy k vydávání nových
verzí, aktualizacím produkčního serveru a podobně.

**Cílem tohoto projektu NENÍ:**

- měnit zásadním způsobem design <i>Zpovědnice</i>, blokovat zobrazování reklam a podobně
- aktualizovat v prohlížeči/databázi data ze <i>Zpovědnice</i> na pozadí (a tím plýtvat jejími zdroji a
  výkonem)
- provádět pod pokličkou jakékoli operace s uživatelskými daty ani sbírat informace o jejich činnosti -
  serverový kód budoucí realtime funkcionality bude mít soukromí a bezpečnost na prvním místě  a bude taktéž
  veřejný

## Licenční ujednání

Projekt je vydán pod nejsvobodnější softwarovou licencí vůbec, [WTFPL](http://www.wtfpl.net/) - nezakládá
žádné povinnosti ani pro koncové uživatele, ani pro případné zájemce o úpravy kódu, a to ať už pro potřebu
vlastní či ve prospěch třetí osoby. Lze ji shrnout jako <strong>dělejte si s tím co chcete</strong>.

## Odkazy

Použité knihovny a technologie, abecedně:

- [Coloris](https://github.com/mdbassit/Coloris)
- [Daypilot Modal](https://modal.daypilot.org/)
- [Dexie.js](https://dexie.org/)
- [DOMPurify](https://github.com/cure53/DOMPurify)
- [EasyMDE](https://github.com/Ionaru/easy-markdown-editor)
- [FileSaver.js](https://github.com/eligrey/FileSaver.js)
- [gettext.js](https://github.com/guillaumepotier/gettext.js)
- [js-emoji](https://github.com/iamcal/js-emoji)
- [Marked](https://github.com/markedjs/marked)
- [Mermaid](https://github.com/mermaid-js/mermaid)
- [Papa Parse](https://www.papaparse.com/)
- [Tabby](https://github.com/cferdinandi/tabby)
- [Tampermonkey](https://www.tampermonkey.net/)
- [Tingle](https://tingle.robinparisi.com/)
