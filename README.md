# Tvořím web A–Z: lekce 2

jaro 2021, Praha

<small>23. března 2021</small>

note:

- **dotaz**: Jak vyhovovalo tempo minule?
- **dotaz**: Vše jasno, nebyly problémy (technické) při práci na DÚ?
- pokud bezradnost: neupejpete se napsat na FB

---

## Postřehy z úkolů

<span class="fragment fade-in">Moc hezké vizitky! Děkuji!</span>

---

### Git: repozitář v repozitáři

![](https://i.imgur.com/SdHIQ26.jpg)

note:

- perfektní, že jste k dotazům na FB připojily screenshoty
- číst výpis v terminálu (i když mu třeba nerozumíme na 100 %)
- ukázat lepší postup při klonování: ponechat VS Code v režimu bez projektu (fialová lišta), terminálem se přesunout do správné složky příkzem `cd` a tam klonovat a následně otevřít adresář jako projekt

---

### Velikost obrázků

- 1 MB je strop, ale lépe spodní stovky kilobytů
- resize × resample


note:

- velmi stručné tipy, je to komplexní problematika (viz Tvořím web 2)
- dvojnásob velký obrázek, je čtyřnásobně velký datově
- Ideální velikost? Jako vždy, _to záleží…_
- ideálně pokud vám je připraví už grafik (od klienta to nečekejte), ale měly byste to umět
- neberte to jako poučku, je to jen orientační

---

### Optimalizace obrázků pro web: **resize**

- změna velikosti => vodítkem velikost monitorů

![](https://i.imgur.com/UWPKubA.png)

note:

- resize: určujeme výslednou velikost fotky bez ořezu, tj. 1200×900 (pozor na správný poměr stran)

---

### Optimalizace obrázků pro web: **resample**

- snížení hustoty pixelů, max dvojnásobek velikosti obrázku

![](https://miro.medium.com/max/700/1*_aLloRR5kmLPvHZGeaDFoA.png)


note:
- resample: velikost stran zůstává, snižuje se počet obrazových bodů (pixelů)
- některé nástroje ke zmenšování: [Squoosh](https://squoosh.app/), [ImageOptim](https://imageoptim.com/), [TinyPNG](https://tinypng.com/), [PicResize](https://picresize.com/)
- příklad s obrázkem Alex na houpačce

---

### Názvy souborů

- názvy souborů (obrázky aj.): bez mezer a diakritik, víceslovné spojit spojovníky `tomas-kout.jpg` nebo podtržítky `tomas_kout.jpg`, případně _camel case_ `tomasKout.jpg`
- na velikosti písmen záleží `obr1.jpg` je jiný soubor než `obr1.JPG`

note:

- `alt`: věčný problém, co tam mám napsat? Záleží na kontextu, ve kterém se obrázek zobrazuje. Když nedává smysl ho popisovat slovně, nechejte atribut prázdný. Video: https://www.youtube.com/watch?v=flf2vS0IoRs

---

### Jazyk dokumentu

```htmlmixed
<p lang="en">English</p>
```
<!-- .element: class="c-text-sm fragment fade-in" -->

```htmlmixed
<p lang="cs">česky</p>
```
<!-- .element: class="c-text-sm fragment fade-in" -->

```htmlmixed
<p lang="sk">slovensky</p>
```
<!-- .element: class="c-text-sm fragment fade-in" -->

```css
:lang(cs) {
    color: crimson;
}
```
<!-- .element: class="c-text-sm fragment fade-in" -->

note:
- komentář se zadáním: je pravda, že se ignoruje, ale měl by být přinejmenším až za `<!DOCTYPE html>` a pokud už není třeba, smazat
- zůstává výchozí `lang="en"`; **dotaz**: jaký je kód pro češtinu?
- úprava a odsazení, středníky za posledním pravidlem

---

## VS Code: užitečná nastavení

Zjednodušíme si život.

<span class="fragment fade-in">Nebo aspoň psaní kódu.</span>

<span class="fragment fade-in">Možná…</span>

---

### VS Code: nastavení

**úkol**: Otevřete si VS Code a v něm nastavení (_File | Preferences_ nebo <kbd>Ctrl/Cmd+,</kbd>)
- zadejte postupně do vyhledávacího pole
    1. Wrap line length: `0`
    2. Format on save: ☑
    3. Render whitespace: `all`
    4. Trim auto whitespace: ☑

note:

- ukázat, vysvětlit
- pokud ti to nebude vyhovovat, vypni si to


---

# A nyní…

## <span class="fragment fade-in">…budeme kódovat<span class="fragment fade-in">

---

## Cvičení 01

1. Forkni si a naklonuj cvičení.
1. Vytvoř z hlavního nadpisu a navigace záhlaví.
1. Obal vše mimo záhlaví prvkem `main`.
1. Rozděl text do sekcí (každá začíná nadpisem 3. úrovně).
1. Obrázkům přidej atributy `width` a `height`.
**Bonus**: Rozchoď navigaci, aby odkazy vedly na jednotlivé sekce.


note:

- **ukázat**: fork a klon přes GitHub Desktop
- Zdroj textu: [Blábot](https://www.blabot.cz/cs/capek)
- **ukázat**: <kbd>Ctrl+Shift+P</kbd> a příkaz Emmet: wrap => obalování
- **ukázat**: <kbd>Ctrl+D</kbd> => atributy `width` a `height`
- Bonus: kdo má hotovo.
- Ukázat rozdíl, když atributy `width` a `height` chybí, a když jsou.

---

# Box model

note:

- **dotaz**: Co to znamená box model?

---

<iframe width="1905" height="959" src="https://www.youtube.com/embed/ZTnIxIA5KGw" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

---

# Vlastnost `display`

<span class="fragment fade-in">`block`</span>
<span class="fragment fade-in">`inline`</span>
<span class="fragment fade-in">`inline-block`</span>
<span class="fragment fade-in">`none`</span>

note:

- **dotaz**: Jaké znáte hodnoty pro `display`.
- každý element má výchozí typ
- pomocí CSS lze ale změnit chování prvku na jiný typ
- tyto 4 hodnoty určují jak se bude prvek chovat navenek

---

## Blokové elementy

<div style="color:black;background-color:orange;">každý zabere</div>
<div style="color:black;background-color:cyan;">celou dostupnou šířku</div>
<div style="color:black;background-color:yellow;">řadí se pod sebe</div>

note:
- nadpisy, seznamy, odstavce, divy, strukturální prvky (header, footer, section)

---

## Řádkové elementy

Zaberou <span style="color:black;background-color:orange;">jen tolik </span><span style="color:black;background-color:cyan;padding:1em 0;">místa</span>, <span style="color:black;background-color:yellow;">kolik potřebují pro svůj obsah</span> a víc nic.

note:
- nejsou samostatně na řádku => řadí se za sebou jako slova ve větě
- nejde jim nastavit některé vlastnosti z box modelu (šířka, výška, horní/dolní margin)
- odkazy, nebo důležitý text (`strong`)
- ony jim ty vlastnosti nastavit jdou, ale neprojeví se očekávaným způsobem
- lze ale například úspěšně nastavit pravý/levý margin

---

## Řádkově-blokové elementy

Řádkový <span style="display:inline-block; color:black;background-color:orange;">hybrid </span><span style="display:inline-block; color:black;background-color:cyan;padding:1em 0;">s některými</span> vlastnostmi blokového: <span style="display:inline-block; color:black;background-color:yellow;">řadí se za sebou</span>, ale lze mu nastavit šířku, výšku a okraje.

note:
- na naší stránce se tak chovají obrázky

---

## Cvičení 02

1. Vytvoř horizontální navigaci (odkazy do jednoho řádku) a vycentruj ji.
1. Odkazy podbarvi průsvitnou barvou.
1. Do záhlaví přidej obrázek na pozadí (URL v komentáři v CSS).
1. Aby byl obrázek vidět, nastav záhlaví minimální výšku.
1. Záhlaví nastav rozdílný horizontální a vertikální padding.
1. Zvětši a vycentruj hlavní nadpis stránky.
<!-- .element: class="c-text-xs"-->

**Bonus**: Záhlaví není do kraje => zjisti v devTools proč a oprav
<!-- .element: class="c-text-xs"-->
**Bonus 2**: Odkazy v navigaci mění po najetí myši pobarvení na plnou (neprůsvitnou barvu).
<!-- .element: class="c-text-xs"-->


note:

- v CSS využívám emmet, šetří psaní!

---

# Vlastnosti box modelu

---

## Rozměry

- `width`, `height`
- `min-width`, `min-height`
- `max-width`, `max-height`

<div class="fragment fade-in">

```css
img {
    width: 300px;
    max-width: 100%;
}
```

</div>

note:

- vyhýbáme se omezování výšky, stránka je z principu na výšku nekonečná
- responzivní/pružný obrázek
    - využíváme procenta v kombinaci s explicitní hodnotou

---

## Odsazení

- vnitřní: `padding`
- vnější: `margin`

<code class="css hljs">
p {
    margin: 1rem<span class="fragment fade-out">;</span><span class="fragment fade-in"> 2rem<span class="fragment fade-out">;</span></span><span class="fragment fade-in"> 0.5rem<span class="fragment fade-out">;</span></span><span class="fragment fade-in">1.25rem;</span>
}
</code>


note:

- `margin` může nabývat i záporných hodnot
- lze psát jednotlivě pro strany boxu (top, right, bottom, left)
- zkrácené vlastnosti:
    - 1 hodnota: všecky 4 strany shodně
    - 2 hodnoty: první nastavuje vertikální odszení, druhá horizontální
    - 3 hodnoty: totéž co 2 hodnoty, třetí hodnota je spodní odsazení
    - 4 hodnoty: nastaví všecky strany po směru hodinových ručiček, počínaje top

---

## Ohraničení

- `border-width`
- `border-style`
- `border-color`
- `border: 1px dashed aqua;`
- `border-radius`

note:

- lze nastavit jednotlivé strany: `border-left: 3px solid silver;`
- lze i nastavit konkrétní vlatnost ohraničení pro jednotlivou stranu: `border-right-width: 0;`
- i `border-radius` s jednou hodnotou je zkratka pro všecky rohy, lze je rozepsat
- `border-radius: 50%;` vytvoří vizuální kruh, ale prvek zůstává obdélníkem (čtvercem)!
- více o `border-radius`: [Jak vytvořit ovál/elipsu](https://jecas.cz/oval), [oblé rohy na steriodech](https://jecas.cz/border-radius)

---

## Cvičení 03

1. Omez šířku stránky a stránku vycentruj (zarovnej na střed).
1. Prvek `main` podbarvi shodnou barvou jako odkazy v navigaci. Nastav mu padding.
1. Podbarvi všechny `section` primární barvou. Přidej jim padding.
1. Přidej `section` spodní ohrančení, které bude tečkované a v tmavé primární barvě.

note:
- skok na konec souboru <kbd>Ctrl+End</kbd>, označit: <kbd>Ctrl+Shift+End</kbd>
- skok na začátek souboru <kbd>Ctrl+Home</kbd>, označit: <kbd>Ctrl+Shift+Home</kbd>
- jak roztáhnout `section` až do kraje
- obrázky zabírají moc místa, můžeme je zmenšit, ale můžeme je taky nechat plavat (ale nikoli nechat být!)

---

## Box sizing

- vlastnost, která určuje, jak se budou počítat rozměry prvku
- chceme `box-sizing: border-box;`, viz začátek našeho CSS
- [příklad na CodePen](https://cdpn.io/Kout/debug/WNRNGgX)

---

# Float

```css

img {
    float: right; /* nebo left */
}
```

---

## Cvičení 04

1. Zuž obrázky v sekcích na 175 pixelů.
1. Nastav jim plavání (vlevo nebo vpravo).

note:

- omezím-li jeden rozměr obrázku, druhý nastavím na `auto`, aby se zachoval poměr stran
- Máme problém plavání pokračuje do dalších sekcí.

---

## Čistíme float

```css
h2 {
    clear: left; /* nebo right nebo both  */
}
```

note:

- tím přerušíme navazující plavání
- ještě zbývá udržet obrázky uvnitř rodičovské sekce

---

## Clearfix

```css
div {
    display: flow-root;
}
```

note:

- historicky se vyvinula řada triků/hacků (clearfix pomocí pseudoelementů, nebo `overflow: auto`)
- naštěstí dnes už máme v CSS vlastnost, která tento (a jiné) řeší
- pozor, `display` zde ovlivňuje chování prvků uvnitř, nikoli prvku samotného; lze číst jako `display: block flow-root;` chovej se jako blok a uvnitř si drž plovoucí prvky
- takto dvouhodnotově se nově bude psát vlastnost `display`, ale zatím to podporuje jen FF
- pro zajímavost: [historie clearfixu na CSS tricks.com](https://css-tricks.com/clearfix-a-lesson-in-web-development-evolution/)

---

# Proměnné vlastnosti <br> (CSS custom properties)

note:

- mají mnohem širší použití, ale nám zatím postačí využít je jako prosté proměnné
- vytvoříme si barevné schéma

---

## Proměnné vlastnosti

```css
:root {
    --primary: #40bf95;
}

h1 {
    color: var(--primary);
}

```

- `:root` ~ root element => prvek `html`

note:

- jsou to vlastnosti, definovat je musíme pro nějaký prvek
- obvykle je to prvek `html`
- lze je i zanořovat, čehož využijeme k vytvoření barevného schématu, ale k tomu je třeba se seznámit s zápisem barev HSLA

---

## Cvičení 05 (nepovinné)

Použij proměnné vlastnosti, abys barvy mohla měnit na jednom místě (v prvku `:root`).

Takové úloze se říká _refactoring_ nebo _refaktor_ kódu. Vylepšujeme kód, aby se lépe udržoval a rozšiřoval, ale na výsledku v prohlížeči se nic nemění.

---

# HSLA barvy

- **H**ue <small>~ odstín</small> <span class="fragment fade-in">0–360</span>
- **S**aturation <small>~ sytost</small> <span class="fragment fade-in">0%–100%</span>
- **L**ightness <small>~ tmavost</small> <span class="fragment fade-in">0%–100%</span>
- **A**lpha channel <small>~ průsvitnost</small> <span class="fragment fade-in">0–1</span>

<span class="fragment fade-in">`background-color: hsla(120, 50%, 50%, 0.5)`</span>

note:

- obdobně RGBA barvy s alfa kanálem

---

## Odstín (hue)
<style>.reveal section img { width: auto; }</style>
![](https://ishadeed.com/assets/color-css/color-wheel-1.jpg)

<small>zdroj: https://ishadeed.com/article/css-color/</small>

---

## Sytost, tmavost, alfa kanál

- sytost: 0% => šedá, 100% plná barva
- tmavost: 0% => černá, 100% => bílá
- průsvitnost: 0 => zcela průhledná, 1 => neprůsvitná

note:

- průsvitnost: desetinná tečka
- popis barev lidským jazykem (oproti RGBA)
- **ukázat**: vytvořit barevné schéma => výhoda HSLA zápisu barev

---

### Cvičení 06

Vytvoř si varianty tzv. primární barvy.

1. Odkazy v navigaci podbarvi průsvitnější variantou.
1. Odkazům v navigaci přidej orámování. Použij tmavou variantu primární barvy.
1. Tutéž barvu použij na písmo odkazů.
1. Písmo nadpisů bude primární barvou.

**Bonus**: Změň odkazům v navigaci podbarvení a barvu písma při přejetí myší.

note:

- podbarvení odkazů: bude to chtít přidat padding
- primární barva je v komentáři
- Trochu se nám ty barvy opakují. Hodilo by se je hodit do proměnné, ne?

---

---

## Cvičení 07 (nepovinné)

Chtělo by to dotáhnout pár věcí:

1. Čitelnost hlavního nadpisu pomocí `text-shadow`, [nastuduj si](https://www.vzhurudolu.cz/prirucka/css3-text-shadow).
1. Odstranit spodní padding prvku `main`.
1. Odstranit ohraničení poslední `section`, pseudotřída `:last-child`.
1. Vycentrovat a odsadit obrázek nad první `section`, pseudotřída `first-child`.
**Bonus**: Nechat plavat obrázy cik-cak (liché vlevo, sudé vpravo).

---

## Užitečné zkratky pro práci s prohlížečem

---

### Prohlížeč: zkratky


- <kbd>F5</kbd>
    - <span class="fragment fade-in">obnovení stránky (refresh, reload)</span>
- <kbd>F6</kbd>
    - <span class="fragment fade-in">skok do adresního řádku</span>
- <kbd>Ctrl+T</kbd>
    - <span class="fragment fade-in">otevře novou záložku</span>
- <kbd>Ctrl+Shift+T</kbd>
    - <span class="fragment fade-in">otevře poslední zavřenou záložku</span>
- <kbd>F12</kbd> nebo <kbd>Ctrl+Shift+I</kbd> nebo kliknu pravým tlačítkem na prvek
    - <span class="fragment fade-in">otevře nástroje pro vývojáře (devTools)</span>


---

### Prohlížeč: zkratky

- otevřít odkaz do nové záložky (tabu)
    - na pozadí
        - <span class="fragment fade-in"><kbd>Ctrl+click</kbd></span>
        - <span class="fragment fade-in"><kbd>klik kolečkem myši</kbd></span>
    - s focusem
        - <span class="fragment fade-in"><kbd>Ctrl+Shift+click</kbd></span>
- otevřít odkaz do nového okna
    - <span class="fragment fade-in"><kbd>Shift+click</kbd></span>

---