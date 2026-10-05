# Rovnice na vahách

Výuková webová aplikace pro 9. ročník. Vede žáky od pákových vah k řešení
lineárních rovnic ekvivalentními úpravami. Je stavěná na samostatnou práci
doma, tedy i na situaci, kdy u toho učitel není. Celá aplikace je jediný
soubor `index.html`. Nic se neinstaluje, nic se neposílá po síti.

## Co aplikace dělá

- Žák staví na vahách, tipuje, co se stane, a váhy pustí. Následek ukážou váhy,
  ne chybová hláška.
- Vedle vah běží Zápisník. Každý krok na vahách se v něm objeví jako řádek
  rovnice s úpravou za svislou čarou.
- Opora se ubírá: UKÁZKA (aplikace dělá, žák vysvětluje) ; SPOLU (aplikace
  začne, žák dokončí) ; SÁM / SAMA (otázky jen na vyžádání).
- Průvodce se ptá a neradí. Má čtyři stupně otázek a nikdy neřekne výsledek.
- Nikdo neuvízne. Když nestačí ani poslední otázka, nabídne se podobná úloha
  s větší oporou, nejvýš dvakrát. Potom žák postoupí s označením „s oporou“.
- Tlačítko „Export“ vytvoří PDF se záznamem práce, které žák nahraje do
  MS Teams.

Etapy 1 až 6 jsou jádro pro všechny. Etapy 7 až 10 jsou rozšíření pro rychlé
žáky.

| Etapa | Co se v ní děje |
|---|---|
| 1 Háček | ověření tipu z papírového listu: stejný účinek na obě strany |
| 2 Účinek | účinek = pozice · závaží, tři správné tipy po sobě |
| 3 Stejně na obě strany | přidat, ubrat, posunout ; past se stejným závažím na jiné pozici |
| 4 Kolik váží L | L jen na jedné straně, zkouška na původních vahách |
| 5 L na obou stranách | hlavní etapa, čtyři kroky ubírání opory |
| 6 Od vah k zápisu | váhy schované, úprava za čarou, zkouška dosazením |
| 7 Záporné pozice | střední: zadní rameno, záporný účinek |
| 8 Závorka na háčku | střední: 3 · (x + 2), 4 · (x − 3) |
| 9 Zvláštní váhy | těžké: žádné řešení a nekonečně mnoho řešení |
| 10 Bez vah | těžké: záporná a zlomková čísla, závorka |

## Jak to zadat na doma v pěti větách

1. V MS Teams vytvoř zadání s odkazem na aplikaci a s místem pro odevzdání
   souboru.
2. Napiš, kam až se mají žáci dostat (obvykle etapa 6) a že stačí zhruba
   30 až 45 minut.
3. Žák pracuje sám, aplikace si pamatuje, kde skončil, a může pokračovat
   jindy na stejném zařízení.
4. Na konci klikne na „Export“, napíše jméno, zvolí na škále 1 až 10, jak mu
   to šlo, a stáhne PDF.
5. PDF nahraje do zadání v Teams a ty z něj vyčteš, kam došel a kde to drhlo.

Nejlépe se pracuje na počítači nebo tabletu. Na telefonu to jde, ale jen
s displejem na šířku. Aplikace to žákovi sama připomene.

Když ji chceš použít ve škole, funguje stejně. Volné váhy se hodí na projektor.

## Export pro učitele

Žák klikne na „Export“ (nahoře vpravo, nebo v závěru pod kolečkem „Z“).
Aplikace se zeptá na jméno a na sebehodnocení a stáhne soubor
`rovnice-na-vahach-jmeno-prijmeni.pdf`. Je to jedna stránka A4.

Co v PDF je:

- jméno, datum a čas exportu, sebehodnocení 1 až 10 ;
- kolik etap je hotových a kolik času žák aktivně pracoval ;
- tabulka etap: výsledek (samostatně ; s otázkami ; s oporou ; rozpracováno ;
  nezačato), čas, počet otázek průvodce a nejvyšší použitý stupeň, počet
  dvojčat, počet chyb ;
- „Co šlo“: etapy zvládnuté samostatně a úspěšnost tipů ;
- „Kde to drhlo“: chyby podle druhu, seřazené od nejčastější, s čísly etap ;
- věty, které žák napsal vlastními slovy.

Chyby, které aplikace poznává:

| V PDF | Jak se pozná |
|---|---|
| úprava jen na jedné straně | žák změnil jen jednu stranu a váhy pustil, nebo tak zapsal řádek |
| stejné závaží na jiné pozici bráno jako stejný účinek | na obě strany stejné závaží, ale jiný účinek |
| účinek počítaný sčítáním místo násobením | v etapě 2 zapsal pozice + závaží |
| 2x chápané jako 2 + x | z a · x = c vyšlo c − a |
| sloučení čísla s neznámou | z x + 2 udělal 2x nebo 3x |
| znaménko při roznásobení závorky | 4 · (x − 3) zapsal jako 4x + 12 |
| špatný výsledek ve zkoušce na vahách | váhy se s jeho číslem naklonily |
| zapsaný řádek nebyl ekvivalentní s předchozím | jiná chyba v zápisu |

Na co si dát pozor:

- Záznam vzniká v prohlížeči, kde žák pracoval. Exportovat musí na stejném
  zařízení. „Začít znovu“ záznam smaže.
- Jméno si žák píše sám a aplikace ho nikam neukládá, je jen v PDF.
- Čas je jen aktivní práce. Mezera delší než 90 sekund se nepočítá.
  V aplikaci se čas neukazuje. Když ho v PDF nechceš, nastav v `KONF`
  `exportCas: false`.
- PDF je obrázek stránky, text v něm nejde označit ani prohledat.
- Je to záznam pro tebe, ne doklad. Kdo chce, může si úložiště prohlížeče
  upravit.

## Nasazení na GitHub Pages krok za krokem

1. Přihlas se na github.com a vpravo nahoře zvol „New repository“.
2. Zadej název, třeba `rovnice-na-vahach`, nech „Public“ a potvrď „Create
   repository“.
3. Klikni na „uploading an existing file“, přetáhni `index.html` a `README.md`
   a potvrď „Commit changes“.
4. Otevři „Settings“, vlevo „Pages“. U „Source“ zvol „Deploy from a branch“,
   větev `main`, složku `/ (root)` a ulož.
5. Za minutu až dvě je stránka na adrese
   `https://tadeasfirich.github.io/vahy/`.
6. Tuhle adresu vlož do zadání v Teams.

Aplikace funguje i bez internetu. Stačí soubor `index.html` zkopírovat do
počítače a otevřít ho v Chromu nebo Edgi.

## Adresy pro učitele

- `…/?ucitel=1` – odemčené všechny etapy, volné váhy už na úvodní obrazovce,
  tlačítka „Zobrazit řešení“, „Přeskočit úlohu“ a „Smazat postup“.
- `…/?test=1` – spustí vestavěné testy modelu. Výsledek je v konzoli
  prohlížeče (klávesa F12, záložka „Console“). Správně je „0 chyb“.

Volné váhy jsou pískoviště bez úloh. Jdou zapnout účinky, zápis a záporné
rameno a nastavit, kolik váží L.

## Co se ukládá

Postup a záznam práce se ukládají jen do prohlížeče na daném zařízení
(localStorage, klíč `rovnice-na-vahach-v1`). Neukládají se žádná jména a nic
se neodesílá. Na sdíleném počítači má úvodní obrazovka při návratu tlačítka
„Pokračovat“ a „Začít znovu“.

## Jak upravit úlohy a texty

Otevři `index.html` v textovém editoru. Kód je rozdělený na části
KONFIGURACE ; DATA ; MODEL ; ZOBRAZENÍ ; PRŮVODCE ; EXPORT ; ÚLOŽIŠTĚ.
Upravuješ jen první dvě.

**Úlohy** jsou v poli `ULOHY`. Jedna úloha vypadá takhle:

```js
{ id: 'e5c', etapa: 'e5', obtiznost: 'základní', typ: 'res', opora: 'sam', x: 4,
  leva:  [{ p: 3, t: 'L', n: 1 }, { p: 2, t: 'd', n: 1 }],
  prava: [{ p: 1, t: 'L', n: 1 }, { p: 1, t: 'h', n: 1 }, { p: 4, t: 'd', n: 1 }],
  text: 'Zjisti, kolik váží L. …' }
```

- `p` je pozice (1 až 5, v rozšíření i −1 až −5), `n` počet kusů.
- `t` je závaží: `d` disk (1) ; `t` trojúhelník (3) ; `h` šestiúhelník (6) ;
  `L` záhadné závaží.
- `x` je skrytá hmotnost L. Váhy musí pro tohle `x` stát rovně.
- `opora` je `ukazka`, `spolu`, nebo `sam`.
- `typ`: `pokus` (tip a puštění) ; `veta` (doplnění věty) ; `res` (řešení na
  vahách) ; `zapis` (řešení zápisem, rovnice je v klíči `rovnice`) ;
  `zvlastni` (etapa 9).
- `zasobnik` říká, která závaží jsou k dispozici. `zamceno: true` znamená, že
  se na vahách nestaví.
- `brana: true` má poslední úloha etapy. Podle ní se rozhoduje o dvojčatech.
  `vzor` říká, jak se dvojčata generují.

**Texty** jsou v objektu `T`. Otázky průvodce najdeš v `T.pr` a `T.nap`,
u jednotlivých úloh v klíčích `napovedy`, `nesplneno`, `poSpatne`. Texty
exportu a názvy chyb v PDF jsou v `T.exp`. Kroky předváděné „na jiných vahách“
jsou v `UKAZKY`.

**Nastavení** je v `KONF`. Znak před úpravou změníš v `KONF.oddelovac`
(třeba na `/`). Je tam i doba nečinnosti, po které se průvodce nabídne, a počet
správných tipů v etapě 2.

Po každé úpravě otevři stránku s `?test=1`. Testy ověří, že všechny úlohy
vycházejí, že váhy stojí rovně a že zprávy průvodce mají nejvýš dvě věty.

## Co aplikace neumí

- Věty psané vlastními slovy (etapa 9 a závěr) nehodnotí. Jsou pro tebe.
- Sama nic neodesílá. Do Teams musí žák PDF nahrát ručně.
- V etapě 10 mají dvě ze čtyř zadaných rovnic kladné celé řešení
  (5 − x = 2x − 4 má x = 3 ; 2 · (x − 1) = x + 7 má x = 9). Za hranice vah
  jdou tím, že se x odčítá a že je v nich závorka.

## Poděkování

Fyzickou váhu se dvěma rameny navrhl a ověřil **Ing. Štěpán Dvořáček**
(závěrečná práce, Pedagogická fakulta Masarykovy univerzity, Brno 2024).
Aplikace z jeho pomůcky a z jeho ověřování vychází: malé kroky, samostatné
úlohy, přesné váhy, žádný dlouhý úvod. Děkujeme.
