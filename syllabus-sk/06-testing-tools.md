## Nástroje na podporu testovania

Testovacie nástroje podporujú a uľahčujú mnoho testovacích aktivít. Príklady okrem iného zahŕňajú:

* nástrojov pre manažment testovania – zvyšujú efektivitu testovacieho procesu uľahčením správy SDLC, požiadaviek, testov, defektov, konfigurácií,
* nástroje na statické testovanie – podporujú testera pri vykonávaní revízií a statickej analýzy,
* nástroje na návrh a implementáciu testov – uľahčujú vytváranie testovacích prípadov, testovacích dát a testovacích procedúr,
* nástroje na vykonávanie testov a meranie ich pokrytia – uľahčujú automatizované vykonávanie testov a meranie pokrytia,
* nástroje pre nefunkcionálne testovanie – umožňujú testerovi vykonávať nefunkcionálne testovanie, ktoré je ťažké alebo nemožné vykonať manuálne,
* nástroje DevOps – podporujú pipeline v DevOps, sledovanie pracovných tokov, procesy automatizovaného zostavovania, CI/CD,
* nástroje pre spoluprácu – uľahčujú komunikáciu,
* nástroje podporujúce škálovateľnosť a štandardizáciu nasadenia (napr. virtuálne počítače, nástroje pre prácu s kontajnermi),
* akýkoľvek iný nástroj, ktorý pomáha pri testovaní (napr. tabuľkový procesor je v kontexte testovania testovacím nástrojom).

## Prínosy a riziká automatizácie testov

Samotné obstaranie nástroja nezaručuje úspech. Každý nový nástroj si bude vyžadovať úsilie na dosiahnutie skutočných a trvalých prínosov (napr. na zavedenie nástroja, údržbu a školenie). Existujú aj určité riziká, ktoré je potrebné analyzovať a zmierniť.

Medzi potenciálne prínosy použitia automatizácie testov patria:

* Úspora času znížením opakovanej manuálnej práce (napr. vykonávanie regresných testov, opätovné zadávanie rovnakých testovacích dát, porovnávanie očakávaných výsledkov so skutočnými výsledkami a kontrola kódu oproti štandardom kódovania).
* Predchádzanie jednoduchým ľudským chybám vďaka väčšej konzistentnosti a opakovateľnosti (napr. testy sú dôsledne odvodené z požiadaviek, testovacie dáta sú vytvorené systematickým spôsobom a testy sú vykonávané nástrojom v rovnakom poradí s rovnakou frekvenciou).
* Objektívnejšie hodnotenie (napr. pokrytie) a vykonávanie opatrení, ktoré sú pre človeka príliš komplikované na odvodenie.
* Jednoduchší prístup k informáciám o testovaní pre podporu manažmentu testovania a podávanie správ o testovaní (napr. štatistiky, grafy a súhrnné dáta o priebehu testov, počte defektov a dĺžke vykonávania testov).
* Skrátenie času vykonávania testov na zabezpečenie skoršiemu odhaleniu defektov, rýchlejšej spätnej väzby a rýchlejšieho uvedenia na trh.
* Viac času pre testerov na navrhovanie nových, dôkladnejších a efektívnejších testov.

Potenciálne riziká používania automatizácie testov zahŕňajú:

* Nerealistické očakávania týkajúce sa prínosov nástroja (vrátane funkčnosti a jednoduchosti používania).
* Nepresné odhady času, nákladov a úsilia potrebného na zavedenie nástroja, udržiavanie testovacích skriptov a zmenu existujúceho procesu manuálneho testovania.
* Používanie testovacieho nástroja, keď je vhodnejšie manuálne testovanie.
* Prílišné spoliehanie sa na nástroj, napr. v zmysle ignorovania potreby ľudského kritického myslenia.
* Závislosť od dodávateľa nástroja, ktorý môže ukončiť svoju činnosť, prestať nástroj vyvíjať, predať nástroj inému dodávateľovi alebo poskytovať nedostatočnú podporu (napr. odpovede na otázky, aktualizácie a opravy chýb).
* Používanie open-source nástroja, ktorého vývoj môže byť zastavený, čo znamená nedostupnosť ďalších aktualizácií, alebo jeho vnútorné komponenty môžu vyžadovať pomerne časté aktualizácie v rámci ďalšieho vývoja.
* Automatizačný nástroj nie je kompatibilný s vývojovou platformou.
* Výber nevhodného nástroja, ktorý nespĺňa regulatórne požiadavky a/alebo bezpečnostné normy.