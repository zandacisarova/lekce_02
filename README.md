# Tvořím web A–Z: lekce 2

podzim 2020, Praha

<small>22. září 2019</small>

---

## Postřehy z úkolů

<span class="fragment fade-in">Jste šikuly!</span>

note: 

- poznámky k úkolům:
    - pokud ukončíte práci, dejte do commit message _hotovo_, abychom věděli, že můžeme připomínkovat
    - zůstává výchozí `lang="en"`; **dotaz**: jaký je kód pro češtinu?
    - komentář se zadáním: je pravda, že se ignoruje, ale měl by být přinejmenším až za `<!DOCTYPE html>`
    - desetinná tečka!
    - názvy souborů (obrázky aj.): bez mezer, víceslovné spojit spojovníky `tomas-kout.jpg` nebo podtržítky `tomas_kout.jpg`, případně _camel case_ `tomasKout.jpg`
    - velikost písma v `px`: zbavujeme se tím možnosti tvořit opavdu responzivní, pružný web. Místo pixelů raději `rem` či `em`, ukážeme si dnes. Totéž pro odsazování textu. Pixely na obrázky, případně ohraničení.
    - odkaz na e-mail: nespoléhejme, že se všem otevře e-mailový program. Vždy je třeba dát možnost dobrat se e-mailu i jinak, buď ho ukázat rovnou, nebo třeba v atribut `title` (nefunguje na dotykovém zařízení).
    - podtrhávání odkazů: držme se konvence, že co je podtržené, je odkazem a naopak, co je odkazem, nechť je podtržené (s výjimkou např. navigace a tlačítek)

---

## VS Code: užitečná nastavení

Zjednodušíme si život.

<span class="fragment fade-in">Nebo aspoň psaní kódu.</span>

---

### VS Code: nastavení

**úkol**: Otevřete si VS Code a v něm nastavení (_File | Preferences_ nebo <kbd>Ctrl/Cmd+,</kbd>)
- zadejte postupně do vyhledávacího pole
    1. Wrap line length: `0`
    2. Format on save: ☑
    3. Render whitespace: `all`
    4. Trim auto whitespace: ☑

note:

- pokud ti to nebude vyhovovat, vypni si to


---

# A nyní…

## <span class="fragment fade-in">…budeme kódovat<span class="fragment fade-in">

---

## Cvičení 01

1. Forkni si a naklonuj cvičení.
1. Vytvoř z hlavního nadpisu a navigace záhlaví.
1. Obal vše mimo záhlaví do prvku `main`.
1. Rozděl text do sekcí (každá začíná nadpisem 3. úrovně).
1. Obrázkům přidej atributy `width` a `height`.
**Bonus**: Rozchoď navigaci.


note:

- **ukázat**: fork a klon přes GitHub Desktop
- Zdroj textu: [Blábot](https://www.blabot.cz/cs/capek)
- **ukázat**: <kbd>Ctrl+Shift+P</kbd> a příkaz Emmet: wrap => obalování
- **ukázat**: <kbd>Ctrl+D</kbd> => atributy `width` a `height`
- Ukázat rozdíl při načítání stránky, když atributy `width` a `height` chybí, a když jsou.

---

# Box model

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
1. Do záhlaví přidej obrázek na pozadí (URL v komentáři v CSS).
1. Aby byl obrázek pěkně vidět, nastav záhlaví minimální výšku.
1. Záhlaví nastav rozdílný horizontální a vertikální padding.
1. Zvětši a vycentruj hlavní nadpis stránky.
**Bonus**: Záhlaví není do kraje => zjistit v devTools proč a opravit

note:

- v CSS využívám emmet, šetří psaní!

---

# HSLA barvy

- **h**ue <small>~ odstín</small> <span class="fragment fade-in">0–360</span>
- **s**aturation <small>~ sytost</small> <span class="fragment fade-in">0%–100%</span>
- **l**ightness <small>~ tmavost</small> <span class="fragment fade-in">0%–100%</span>
- **a**lpha channel <small>~ průsvitnost</small> <span class="fragment fade-in">0–1</span>

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
- hned si ukážeme další výhodu tohoto zápisu

---

### Cvičení 03

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

# CSS proměnné (CSS custom properties)

note:

- mají mnohem širší použití, ale nám zatím postačí využít je jako prosté proměnné
- vytvoříme si barevné schéma

---

## CSS proměnné

```css
:root {
    --primary: hsla(160, 50%, 50%, 1);
}

h1 {
    color: var(--primary);
}

```

note: 

- lze je i zanořovat, čehož využijeme k vytvoření barevného schématu 
- **ukázat**: vytvořit barevné schéma => výhoda HSLA zápisu barev

---

## Cvičení 04 (nepovinné)

Použij CSS proměnné a vytvoř si své barevné schéma.


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
- využíváme procenta v kombinaci s explicitní hodnotou
- responzivní/pružný obrázek

---

## Odsazení

- vnitřní: `padding`
- vnější: `margin`

```css
p {
    margin: 1rem 2rem 0.5rem 1.25rem;   
}
```

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
- `border: 1px dashed aqua`
- `border-radius`

note: 

- lze nastavit jednotlivé strany: `border-left: 3px solid silver;`
- lze i nastavit konkrétní vlatnost ohraničení pro jednotlivou stranu: `border-right-width: 0;`
- i `border-radius` s jednou hodnotou je zkratka pro všecky rohy, lze je rozepsat
- `border-radius: 50%;` vytvoří vizuální kruh, ale prvek zůstává obdélníkem (čtvercem)!
- více o `border-radius`: [Jak vytvořit ovál/elipsu](https://jecas.cz/oval), [oblé rohy na steriodech](https://jecas.cz/border-radius)


---

## Cvičení 04

1. Omez šířku stránky a vycentruj ji.
1. Prvek `main` podbarvi stenou barvou jako odkazy v navigaci. Nastav mu padding.
1. Podbarvi všechny `section` primární barvou. Přidej jim padding.
1. Přidej `section` spodní ohrančení, které bude tečkované a v tmavé primární barvě.

note:
- Linux/Windows:
    - skok na konec souboru <kbd>Ctrl+End</kbd>, označit: <kbd>Ctrl+Shift+End</kbd>
    - skok na začátek souboru <kbd>Ctrl+Home</kbd>, označit: <kbd>Ctrl+Shift+Home</kbd>
- Mac:
    - skok na konec souboru <kbd>Cmd+šipka dolů</kbd> 
    - skok na začátek souboru <kbd>Cmd+šipka nahoru</kbd> 
- jak roztáhnout `section` až do kraje => záporný margin!
- obrázky zabírají moc místa, můžeme je zmenšit, ale můžeme je taky nechat plavat (ale nikoli nechat být!)

---

# Float

```css

img {
    float: right; /* nebo left */
}
```

---

## Cvičení 05

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

## Cvičení 06

Chtělo by to dotáhnout pár věcí:

1. Čitelnost hlavního nadpisu pomocí `text-shadow`.
1. Odstranit spodní padding prvku `main`.
1. Odstranit ohraničení poslední `section`.
1. Vycentrovat a odsadit obrázek nad první `section`.
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