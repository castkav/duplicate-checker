# Duplicate Checker

Online nástroj pro seznam e-mailových adres oddělených středníkem. Po vložení textu vrátí seznam seřazený od A do Z bez duplicit, připravený ke zkopírování, a upozorní na možné chyby a překlepy.

Nahrazuje postup Word (`;` → `^p`) → Excel (bez duplicitních záznamů, seřadit) → Word (`^p` → `;`).

## Co dělá

**Seřazeno, bez duplicit**
- adresy se dají oddělit středníkem, novým řádkem, nebo i čárkou či mezerou,
- z tvaru `Jan Novák <jan.novak@firma.cz>` se vezme jen adresa,
- duplicity se poznají i při jiné velikosti písmen (`Jan.Novak@Firma.cz` = `jan.novak@firma.cz`) nebo s mezerami kolem,
- neviditelné znaky (mezera nulové šířky, BOM…) se odstraní a nástroj na ně upozorní,
- výsledek je malými písmeny, seřazený podle abecedy, s volbou oddělovače (středník, středník a mezera, nový řádek),
- volitelně české řazení, kde „ch“ je až za „h“.

Řazení a odstranění duplicit je přesné. Výsledek obsahuje všechny vložené adresy, každou jen jednou, i ty chybné (ty jsou vypsané v sekci Chyby).

**Chyby** – adresa nebude fungovat: chybí zavináč, mezera uvnitř, diakritika, znaky z cyrilice, tečky na špatném místě, chybná koncovka…

**Možné překlepy** – jen odhad, nic se samo neopravuje:
- jméno, které se o písmeno liší od běžného jména: `ja.novak` → `jan.novak`?,
- překlep v koncovce -ová: `anna.novakov`, `jana.novakvoa` → `novakova`?,
- jméno nesedí k příjmení: `martin.novakova` → `martina.novakova` nebo `martin.novak`?,
- překlep v doméně: `sezman.cz` → `seznam.cz`?, `gmail.cz` → `gmail.com`?,
- doména, která se o písmeno liší od domény ostatních adres v seznamu: `crestcon.cz`, když zbytek má `crestcom.cz`,
- dvě adresy v seznamu, které se liší jediným znakem.

U navržené opravy je vidět, jestli taková adresa už v seznamu je.

**Odstraněné duplicity** – které adresy byly v seznamu vícekrát a v jaké podobě.

## Soukromí

Vše běží jen v prohlížeči. Text se nikam neodesílá.

## Spuštění

Jde o jediný soubor `index.html` bez závislostí. Stačí ho otevřít v prohlížeči, nebo zapnout GitHub Pages (Settings → Pages → Deploy from a branch → `main` / root) a aplikace poběží na `https://castkav.github.io/duplicate-checker/`.
