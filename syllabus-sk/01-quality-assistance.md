## Čo je testovanie?

Softvérové systémy sú neoddeliteľnou súčasťou nášho každodenného života. Väčšina ľudí má skúsenosti so softvérom, ktorý fungoval inak, než očakávali. Softvér, ktorý nefunguje správne, môže viesť k mnohým problémom, napr. strate peňazí, času alebo obchodnej povesti a v extrémnych prípadoch dokonca k zraneniu alebo smrti. Testovanie softvéru hodnotí kvalitu softvéru a pomáha znižovať riziko zlyhania softvéru v prevádzke.

Testovanie softvéru je sada činností, ktorých cieľom je odhaľovanie defektov a vyhodnocovanie kvality softvérových artefaktov, ktoré sa pri testovaní označujú ako testované objekty. Bežná (a bohužiaľ mylná) predstava o testovaní je, že ide len o vykonávanie testov (t. j. spustenie softvéru a kontrola výsledkov testov). Testovanie softvéru ale zahŕňa aj ďalšie činnosti a musí byť v súlade so životným cyklom vývoja softvéru (pozri <#section:improve-quality-and-flow-in-a-value-driven-organization>).

Ďalšou bežnou mylnou predstavou o testovaní je, že testovanie sa zameriava výhradne na verifikáciu testovaného objektu. Testovanie ale zahŕňa nielen verifikáciu (t. j. kontrolu, či systém spĺňa špecifikované požiadavky), ale aj validáciu (teda kontrolu, či systém spĺňa potreby používateľov a ďalších zainteresovaných strán v ich prevádzkovom prostredí).

Testovanie môže byť dynamické alebo statické. Dynamické testovanie vyžaduje spustenie testovaného softvéru, zatiaľ čo statické testovanie spustenie nevyžaduje. Statické testovanie zahŕňa revízie (pozri <#section:static-testing>) a statickú analýzu. Dynamické testovanie používa rôzne techniky testovania a prístupy k testovaniu s cieľom definovať testovacie prípady (pozri <#section:organizational-test-strategy-in-a-value-driven-organization>).

Testovanie nie je len technická činnosť. Rovnako je potrebné ho riadne plánovať, riadiť, odhadovať, monitorovať a kontrolovať (pozri <#section:test-processes-strategy-in-a-value-driven-organization>).

Testeri síce používajú pri testovaní nástroje (pozri <#section:test-tools>), ale je dôležité si uvedomiť, že testovanie je hlavne intelektuálna činnosť. Pri nej je potrebné, aby testeri mali špecializované znalosti, používali analytické zručnosti a aplikovali kritické a systémové myslenie ([@myers2011art],[@roman2018thinking]).

Ďalšie informácie o konceptoch testovania softvéru možno nájsť v norme ČSN ISO/IEC/IEEE 29119-1 [@ISO29119-1].

### Typické ciele testovania {#typical-testing-objectives}

Typické ciele testovania sú:

* ohodnotenie pracovných produktov ako sú požiadavky, používateľské scenáre, návrhy a kód,
* vyvolanie zlyhania a nájdenie defektov,
* zabezpečenie požadovaného pokrytia testovaného objektu,
* zníženie úrovne rizika plynúce z nedostatočnej kvality softvéru,
* verifikácia, či boli splnené stanovené požiadavky,
* verifikácia, že testovaný objekt vyhovuje zmluvným, právnym a regulatórnym požiadavkám,
* poskytnutie informácií zainteresovaným stranám tak, ako základ pre kvalifikované rozhodnutia,
* vytvorenie dôvery v danú úroveň kvality testovaného objektu,
* kontrola, či je testovaný objekt kompletný a funguje podľa očakávania všetkých zainteresovaných strán.

Ciele testovania sa môžu líšiť v závislosti od kontextu, ktorý zahŕňa faktory ako je charakteristika testovaného pracovného produktu, úroveň testovania, rizík, zvoleného životného cyklu vývoja softvéru (SDLC). Okrem toho ale závisí aj od biznisového kontextu s faktormi ako štruktúra spoločnosti, konkurenčné hľadiská alebo doba uvedenia na trh (time to market). 

### Testovanie a ladenie

Testovanie a ladenie (debugging) sú samostatné činnosti. Testovanie môže vyvolať zlyhania, ktoré sú spôsobené defektmi v softvéri (dynamické testovanie), alebo môže priamo odhaliť defekty v testovanom objekte (statické testovanie).

Zatiaľ čo dynamické testovanie (pozri <#section:organizational-test-strategy-in-a-value-driven-organization>) sa snaží vyvolať zlyhanie, ladenie sa zaoberá hľadaním príčin takých zlyhaní (t. j. defektov), ich analýzou a ich odstránením. Typický proces ladenia v tomto prípade zahŕňa:

* reprodukovanie zlyhania,
* diagnostika (nájdenie koreňovej príčiny),
* oprava príčiny.

Následné tzv. konfirmačné testovanie overuje, či došlo v dôsledku týchto opráv k vyriešeniu problému. Vykonáva ho ideálne rovnaká osoba, ktorá vykonala prvotný test. Okrem toho je následne tiež možné vykonať tzv. regresné testovanie s cieľom overiť, či opravy nespôsobujú zlyhanie v iných častiach testovaného objektu. Viac informácií o konfirmačnom a regresnom testovaní pozri <#section:confirmation-and-regression-testing>.

Statické testovanie priamo identifikuje defekt, ladenie sa zaoberá jeho odstránením. Obvykle pri ňom nie je nutné vykonávať reprodukovanie a diagnostiku, pretože statické testovanie nachádza priamo defekty a nemôže spôsobiť zlyhanie (pozri <#section:static-testing>).

## Prečo je testovanie nevyhnutné?

Testovanie ako jeden zo spôsobov riadenia kvality pomáha pri dosiahnutí dohodnutých cieľov v rámci stanoveného rozsahu, času, kvality a rozpočtových obmedzení. K úspechu projektu neprispievajú nutne iba činnosti zaistené testovacím tímom – ktokoľvek zo zainteresovaných strán môže využiť svoje testovacie zručnosti na to, aby sa projekt úspešne priblížil k svojmu cieľu. Testovanie komponentov, systémov a súvisiacej dokumentácie pomáha identifikovať defekty v softvéri.

### Ako testovanie prispieva k úspechu

Testovanie poskytuje nákladovo efektívny spôsob detekcie defektov. Tieto defekty je možné odstrániť (ladením, teda aktivitou, ktorá nespadá pod oblasť testovania), takže testovanie vlastne nepriamo prispieva ku kvalitnejším testovaným objektom.

Testovanie poskytuje prostriedky na priame hodnotenie kvality testovaného objektu v rôznych fázach SDLC. Tieto hodnotenia sa používajú ako súčasť širších aktivít manažmentu projektov a prispievajú tak k rozhodnutiu o prechode do ďalšej fázy SDLC, napríklad k rozhodnutiu o vydaní. 

Testeri sú zárukou toho, že ich pochopenie potrieb používateľov je zohľadnené v priebehu celého životného cyklu vývoja. Alternatívou k využitiu testerov je zapojenie reprezentatívnej skupiny používateľov do projektu, čo ale obvykle nie je možné kvôli vysokým nákladom a nedostatočnej dostupnosti vhodných používateľov.

Okrem hodnotenia kvality testovaného objektu môže byť testovanie softvéru vyžadované aj z dôvodu splnenia zmluvných alebo zákonných požiadaviek či noriem.

### Testovanie a zabezpečenie kvality

Ľudia často zamieňajú pojmy testovania a zabezpečenie kvality (QA – quality assurance), ale nie je to to isté.

Testovanie je forma riadenia kvality (QC – quality control). QC je produktovo orientovaný, nápravný prístup, ktorý sa zameriava na tie činnosti, ktoré podporujú dosiahnutie primeranej úrovne kvality. Testovanie je síce hlavnou formou QC, ale nie je jedinou. Možno využiť aj iné formálne metódy (napr. overenie modelu alebo dôkazy správnosti), prípadne simuláciu alebo prototypovanie.

QA je preventívny prístup orientovaný na procesy, ktorý sa zameriava na ich zavádzanie a zlepšovanie. Je založený na predpoklade, že pokiaľ je dodržiavaný správny proces, potom je jeho výsledkom správny produkt. QA sa vzťahuje na procesy vývoja i testovania a je zodpovednosťou všetkých osôb v projekte.

Výsledky testov sú využívané v QA aj v QC. V QC sa používajú na opravu defektov, zatiaľ čo v QA poskytujú spätnú väzbu o tom, ako dobre fungujú procesy vývoja a testovania.

### Chyby, defekty, zlyhania a koreňové príčiny

Ľudia robia chyby (omyly), v dôsledku ktorých vznikajú defekty (vady, bugy), ktoré môžu viesť k zlyhaniu. Ľudské chyby vznikajú z rôznych dôvodov ako sú časová tieseň alebo zložitosť pracovných produktov, procesov, infraštruktúry a interakcií. Chyby môžu tiež vzniknúť jednoducho preto, že sú ľudia unavení alebo im chýbajú zodpovedajúce školenia.

Defekty možno nájsť v dokumentácii (napr. v špecifikácii požiadaviek alebo testovacom skripte), v zdrojovom kóde alebo v akomkoľvek podpornom artefakte, napr. v súbore zostavení (buildu). Pokiaľ nie sú zistené defekty artefaktov vzniknutých v skorších fázach SDLC, vedú často k vzniku defektných artefaktov v jeho nadväzujúcich fázach.

Ak je spustený defekt v kóde, systém nemusí robiť to, čo by mal robiť alebo môže urobiť niečo, čo by nemal. To môže (ale nemusí) spôsobiť zlyhanie. Niektoré defekty môžu viesť pri spustení k zlyhaniu vždy, iné iba za určitých okolností, niektoré dokonca nemusia zlyhanie spôsobiť nikdy.

Chyby a defekty nie sú jedinou príčinou zlyhania. Zlyhania môžu byť spôsobené aj podmienkami prostredia, príkladom môže byť defekt vo firmvéri spôsobený žiarením alebo pôsobením elektromagnetického poľa.

Koreňová príčina je primárnym dôvodom vzniku problému (napr. situácia, ktorá vedie k chybe). Koreňové príčiny možno identifikovať pomocou ich analýzy, ktorá sa obvykle vykonáva po výskyte zlyhania alebo identifikácii defektu. Predpokladá sa, že riešením koreňovej príčiny (najlepšie jej odstránením) možno zabrániť podobným zlyhaniam alebo defektom (popr. aspoň znížiť ich početnosť).

## Princípy testovania {#testing-principles}

Počas posledných rokov bol zdokumentovaný rad princípov, ktoré poskytujú všeobecný návod aplikovateľný pre všetky druhy testovania. Tieto učebné osnovy popisujú sedem takýchto princípov.

**1. Testovanie preukazuje prítomnosť defektov, nie ich neprítomnosť.** Testovanie môže preukázať, že defekty sú v testovanom objekte prítomné, ale nemôže preukázať, že v ňom žiadne nie sú [@buxton1970software]. Testovanie znižuje pravdepodobnosť, že v testovanom objekte zostali neodhalené defekty, avšak pokiaľ nie sú žiadne defekty nájdené, nie je tým preukázaná jeho správnosť.

**2. Vyčerpávajúce testovanie nie je možné.** Testovanie všetkého (napr. všetkých kombinácií vstupov) nie je možné s výnimkou triviálnych prípadov [@manna1978logic]. Namiesto snahy o vyčerpávajúce testovanie je lepšie sa zamerať na vhodné techniky testovania (pozri <#section:organizational-test-strategy-in-a-value-driven-organization>), stanovenie priorít testovacích prípadov (pozri <#section:test-cases-prioritization>) a testovanie založené na rizikách (pozri <#section:risk-management>).

**3. Včasné testovanie šetrí čas a peniaze.** Defekty, ktoré sú odstránené v ranej fáze procesu, nespôsobia následne iné defekty v odvodených (následných) pracovných produktoch. Náklady na kvalitu budú navyše znížené, pretože neskôr v SDLC dôjde k menšiemu počtu zlyhaní [@boehm1981software]. Na včasné odhalenie defektov by sa malo čo najskôr začať statické testovanie (pozri <#section:static-testing>) aj dynamické testovanie (pozri <#section:organizational-test-strategy-in-a-value-driven-organization>).

**4. Zhlukovanie defektov.** Väčšinu zistených defektov obsahuje obvykle malé množstvo systémových komponentov, prípadne je malé množstvo systémových komponentov zodpovedných za väčšinu prevádzkových zlyhaní [@endres1975analysis]. Tento jav je ilustráciou tzv. Paretovho pravidla. Predpokladané a skutočne pozorované zhluky defektov počas testovania alebo v prevádzke sú významným vstupom pre testovanie založené na rizikách (pozri <#section:risk-management>).

**5. Testy sa opotrebovávajú.** Pokiaľ sa rovnaké testy opakujú neustále dookola, stávajú sa stále menej účinnými a nedochádza k odhaľovaniu nových defektov [@beizer1990software]. Aby sme sa vysporiadali s dôsledkami tohto princípu, je nutné meniť existujúce testy a testovacie dáta, príp. je potrebné vytvoriť nové testy. V niektorých prípadoch má však opakovanie rovnakých testov význam, napr. pri automatizovanom regresnom testovaní (pozri <#section:confirmation-and-regression-testing>).

**6. Testovanie je závislé od kontextu.** Neexistuje jediný univerzálne použiteľný prístup k testovaniu, testovanie sa vykonáva odlišne v rôznych kontextoch [@kaner1999testing].

**7. Neprítomnosť defektov je klam.** Je mylnou predstavou očakávať, že obyčajná verifikácia softvéru zaistí jeho úspech. Aj pri dôkladnom testovaní všetkých špecifikovaných požiadaviek a odstránení všetkých zistených defektov môže vzniknúť systém, ktorý nespĺňa potreby a očakávania používateľov, ktorý nepomáha dosahovať biznisové ciele zákazníka a ktorý je horší v porovnaní s inými konkurenčnými systémami. Okrem verifikácie by mala byť vykonaná aj validácia [@boehm1981software].

## Testovacie činnosti, testvér a roly v testovaní

Testovanie je síce závislé od kontextu, avšak existujú testovacie činnosti, bez ktorých je menej pravdepodobné, že sa dosiahnu vytýčené ciele. Skupiny takýchto činností nazývame proces testovania. Proces testovania môže byť prispôsobený danej situácii na základe rôznych faktorov. O tom, ktoré testovacie činnosti sú zahrnuté do procesu testovania, ako sú implementované a kedy k nim dôjde, sa obvykle rozhoduje v rámci plánovania testovania pre konkrétnu situáciu (pozri <#section:planning-testing>).

Nasledujúci text popisuje všeobecné aspekty tohto procesu z hľadiska testovacích činností a úloh, vplyvu kontextu, testvéru, sledovateľnosti medzi testovacou bázou a testvérom a tiež rolami v testovaní.

Ďalšie informácie o procesoch testovania je možné nájsť v norme ČSN ISO/IEC/IEEE 29119-2 [@ISO29119-2].

### Testovacie činnosti a úlohy {#test-activities-and-tasks}



Proces testovania sa obvykle skladá z hlavných skupín činností (pozri ďalej), ktoré je obvykle nutné prispôsobiť systému a projektu. Aj keď sa mnohé z týchto hlavných skupín činností môžu javiť ako logicky zoradené za sebou, často sa vykonávajú iteratívne alebo paralelne. 

**Plánovanie testovania** sa skladá z definovania cieľov testovania a následného výberu takého prístupu, ktorý najlepšie dosahuje definované ciele v rámci obmedzení daných celkovým kontextom. Plánovanie testovania je ďalej vysvetlené v kapitole <#section:planning-testing>.

**Monitorovanie a riadenie testovania**. Monitorovanie testovania zahŕňa priebežnú kontrolu všetkých testovacích činností
a porovnávanie skutočného stavu proti plánu, riadenie testovania sa zaoberá prijatím opatrení potrebných na dosiahnutie cieľov testovania. Monitorovanie a riadenie testovania sú ďalej vysvetlené v kapitole <#section:monitoring-management-completion-of-testing>.

**Testovacia analýza** zahŕňa analýzu testovacej bázy za účelom identifikácie testovateľných funkcionalít (features) a definovania príslušných testovacích podmienok vrátane stanovenia ich priorít a súvisiacich rizík spolu s ich úrovňami (pozri <#section:risk-management>). Testovacia báza a testované objekty sú tiež hodnotené za účelom posúdenia ich testovateľnosti a identifikácie prípadných defektov v nich obsiahnutých. Pri testovacej analýze sú často používané techniky testovania (pozri <#section:organizational-test-strategy-in-a-value-driven-organization>). Testovacia analýza určuje „Čo sa má testovať?“ v zmysle merateľných kritérií pokrytia. 

**Návrh testov** zahŕňa rozpracovanie testovacích podmienok do testovacích prípadov a ďalšieho testvéru (napr. testovacích listín). Často obsahuje aj identifikáciu položiek pokrytia slúžiacich ako vodítko pre stanovenie vstupov testovacích prípadov. Pri tejto činnosti je možné použiť taktiež vhodné techniky testovania (pozri <#section:organizational-test-strategy-in-a-value-driven-organization>). Návrh testov tiež zahŕňa stanovenie požiadaviek na testovacie dáta, návrh testovacieho prostredia a identifikáciu ďalšej potrebnej infraštruktúry alebo nástrojov. Návrh testov dáva odpoveď na otázku „Ako testovať?“.

**Implementácia testovania** zahŕňa vytvorenie alebo získanie testvéru nevyhnutného na vykonanie testov (napr. testovacie dáta). Testovacie prípady môžu byť usporiadané do testovacích procedúr a sú často zoskupené do testovacích sád. Okrem iného sú v rámci tejto činnosti vytvárané manuálne a automatizované testovacie skripty. Z dôvodu efektívneho vykonania testov (pozri <#section:test-cases-prioritization>) sú testovacie procedúry prioritizované a usporiadané v harmonograme vykonania testov. Súčasťou činností implementácie testovania je zostavenie testovacieho prostredia a overenie jeho správneho nastavenia.

**Vykonanie testov** zahŕňa spustenie testov v súlade s harmonogramom vykonania testov (ako čiastkových behov testov, test runs). Vykonanie testov môže byť manuálne alebo automatizované a môže mať mnoho foriem vrátane tzv. kontinuálneho alebo párového testovania. V rámci tejto činnosti sú porovnané skutočné výsledky testov s očakávanými a zaznamenané ich výsledky. Anomálie sú analyzované s cieľom identifikácie ich pravdepodobnej príčiny. Táto analýza umožňuje reportovať anomálie na základe pozorovaných zlyhaní (pozri <#section:defects-management>).

K činnostiam **dokončenia testovania** obvykle dochádza pri dosiahnutí míľnikov projektu (napr. vydanie, koniec iterácie, dokončenie úrovne testovania) a vykonáva sa pre všetky nevyriešené defekty, požiadavky na zmeny alebo vytvorené položky produktového backlogu. Akýkoľvek testvér, ktorý môže byť v budúcnosti užitočný, je identifikovaný
a archivovaný, prípadne je odovzdaný príslušným tímom. Testovacie prostredie sa uvedie do dohodnutého stavu (napr. je vypnuté). Testovacie činnosti sú analyzované s cieľom identifikácie získaných poznatkov a vylepšení pre prípadné budúce iterácie, vydania alebo aj iné projekty (pozri <#section:retrospectives-and-process-improvement>). Je vytvorená správa o dokončení testovania, ktorá je komunikovaná príslušným zainteresovaným stranám.

### Proces testovania v súvislostiach

Testovanie neprebieha izolovane. Testovacie činnosti sú neoddeliteľnou súčasťou procesov vývoja vykonávaných v rámci organizácie. Finálnym cieľom testovania je (okrem iného) pomôcť splniť biznisové potreby zainteresovaných strán, ktoré tiež proces testovania financujú. Spôsob, akým sa testovanie vykonáva, bude preto závisieť od mnohých faktorov, napríklad:

* zainteresované strany (ich potreby, očakávania, požiadavky, ochota spolupracovať),
* členovia tímu (ich zručnosti, znalosti, úroveň skúseností, dostupnosť, potreby školenia),
* sféra biznisu (kritickosť testovaného objektu, identifikované riziká, potreby trhu, konkrétne právne predpisy),
* technické faktory (typ softvéru, architektúra produktu, použité technológie),
* obmedzenie projektu (rozsah, čas, rozpočet, zdroje),
* organizačné faktory (organizačná štruktúra, existujúce politiky, používané postupy),
* životný cyklus vývoja softvéru (technické postupy, metódy vývoja atď.),
* nástroje (dostupnosť, použiteľnosť, zhoda s predpismi).

Tieto faktory budú mať vplyv na mnoho aspektov súvisiacich s testovaním vrátane stratégie testovania, použitých techník testovania, stupňa automatizácie testovania, požadovanej úrovne pokrytia, úrovne podrobnosti dokumentácie testovania, reportovania, atď.

### Testvér 

Testvér je definovaný ako výstupný pracovný produkt z testovacích činností popísaných v kapitole <#section:test-activities-and-tasks>. V tom, ako rôzne organizácie vytvárajú, pomenovávajú, organizujú a spravujú také pracovné produkty, existujú však značné rozdiely. Pre podporu konzistencie a integrity testvéru je dôležité zaistenie dobrého konfiguračného manažmentu (pozri <#section:configuration-management>). 

Nasledujúci zoznam uvádza niektoré (ale nie všetky) také typické výstupné pracovné produkty (testvér):

* **Pracovné produkty z plánovania testovania:** plán testovania, harmonogram testovania, register rizík a vstupné a výstupné kritériá (pozri <#section:planning-testing>). Register rizík je zoznam rizík spolu s ich pravdepodobnosťou, dopadom a informáciami o ich možnom zmiernení (risk mitigation), pozri kapitolu <#section:risk-management>. Harmonogram testovania, register rizík, vstupné a výstupné kritériá sú často súčasťou plánu testovania.
* **Pracovné produkty z monitorovania a riadenia testovania:** správy o postupe testovania (pozri <#section:purpose-content-target-of-test-reports>), pokyny a nevyhnutné nápravné opatrenia (pozri <#section:monitoring-management-completion-of-testing>) a informácie o rizikách (pozri <#section:risk-management>).
* **Pracovné produkty z testovacej analýzy:** (prioritizované) testovacie podmienky (napr. akceptačné kritériá, pozri <#section:acceptance-criteria>) a defekty v testovacej báze (pokiaľ ešte neboli opravené).
* **Pracovné produkty z návrhu testov:** (prioritizované) testovacie prípady, testovacie listiny, položky pokrytia, požiadavky na testovacie dáta a požiadavky na testovacie prostredie.
* **Pracovné produkty z implementácie testovania:** testovacie procedúry, automatizované testovacie skripty, testovacie sady, testovacie dáta, harmonogram prevedenia testov a prvky testovacieho prostredia. Medzi príklady položiek testovacieho prostredia patria nástavce, ovládače, simulátory a virtualizácia služieb.
* **Pracovné produkty z vykonania testov:** protokoly testov (test logs) a reporty defektov (pozri <#section:defects-management>).
* **Pracovné produkty z dokončenia testovania:** správa o dokončení testovania (pozri <#section:purpose-content-target-of-test-reports>), akčné body pre zlepšenie budúcich projektov alebo iterácií, zdokumentované získané poznatky (lessons learned) a zmenové požiadavky (napr. ako položky produktového backlogu).


### Sledovateľnosť medzi testovacou bázou a pracovnými produktmi z testovania


Aby bolo možné efektívne monitorovať a riadiť testovanie, je dôležité vytvoriť a následne udržiavať v priebehu celého procesu testovania sledovateľnosť medzi každou položkou testovacej bázy, výstupnými pracovnými produktmi vztiahnutými k tejto položke (testvérom − napr. testovacie podmienky, riziká alebo testovacie prípady), výsledky testov a nájdenými defektmi.

Presná sledovateľnosť umožňuje vyhodnocovať pokrytie, takže je veľmi užitočné, pokiaľ sú v testovacej báze pre toto pokrytie definované jeho merateľné kritériá. Kritériá pokrytia môžu predstavovať jeden z kľúčových ukazovateľov výkonnosti (KPI – key performance indicator) pre riadenie testovacích činností, ktoré ukazujú na mieru dosiahnutia cieľov testovania (pozri <#section:typical-testing-objectives>). Napríklad:

* Sledovateľnosť medzi testovacími prípadmi a požiadavkami pomôže overiť, či sú požiadavky pokryté testovacími prípadmi.
* Sledovateľnosť medzi výsledkami testov a rizikami možno použiť na vyhodnotenie úrovne zvyškového rizika testovaného objektu.

Okrem vyhodnotenia pokrytia umožňuje dobrá sledovateľnosť určiť vplyv zmien, uľahčuje vykonávanie auditov testovania a pomáha plniť kritériá zásad správneho riadenia v IT. Dobrá sledovateľnosť tiež zlepšuje zrozumiteľnosť správ o postupe testovania a správ o dokončení testovania tým, že ukazuje stav položiek testovacej bázy. To môže tiež prispieť k zrozumiteľnej komunikácii so zainteresovanými stranami o technických aspektoch testovania. Sledovateľnosť poskytuje informácie pre posúdenie kvality produktu, spôsobilosti procesov a postupe prác v projekte vzhľadom na biznisové ciele. 

### Roly v testovaní

V týchto učebných osnovách sú definované dve hlavné roly pri testovaní: rola manažéra testovania a rola testera. Činnosti a úlohy vykonávané týmito dvoma rolami závisia od kontextu projektu a produktu, od zručností ľudí v daných rolách a od danej organizácie.

**Manažér testovania** má celkovú zodpovednosť za proces testovania, testovací tím a úspešné riadenie testovacích činností. Zameriava sa predovšetkým na činnosti plánovania testovania, monitorovania a riadenia testovania a dokončenia testovania. Spôsob, akým sa táto rola vykonáva, sa líši v závislosti na životnom cykle vývoja softvéru, napríklad
v agilnom vývoji sú niektoré úlohy manažéra testovania vykonávané celým agilným tímom. Úlohy, ktoré zahŕňajú viac tímov alebo celú organizáciu, môžu byť vykonávané manažérmi testovania mimo vývojový tím.

**Tester** preberá celkovú zodpovednosť za inžiniersky (technický) aspekt testovania. Zameriava sa predovšetkým na činnosti testovacej analýzy, návrhu testov, implementácie testovania a vykonania testov.

Obe roly môžu byť vykonávané v rôznych obdobiach rôznymi ľuďmi, napríklad rola manažéra testovania môže byť vykonávaná vedúcim tímu, samotným manažérom testovania alebo manažérom vývoja. Je tiež možné, aby jedna osoba prevzala rolu testera aj rolu manažéra testovania súčasne.

## Základné zručnosti a osvedčené postupy pri testovaní

Zručnosť je schopnosť robiť niečo dobre a vychádza z niečích znalostí, praxe a schopností. Aby mohli testeri dobre vykonávať svoju prácu, potrebujú mať určité základné zručnosti, okrem iného by mali byť dobrými tímovými hráčmi a mali by byť schopní pracovať na rôznych úrovniach nezávislosti testovania.

### Všeobecné zručnosti potrebné na testovanie {#general-skills-needed-for-testing}

Nasledujúce zručnosti sú síce všeobecné, ale pre testerov obzvlášť dôležité:

* Znalosť testovania (s cieľom zvyšovania efektivity testovania, napr. pomocou techník testovania).
* Dôkladnosť, starostlivosť, zvedavosť, dôraz na detail, schopnosť pracovať metodicky (s cieľom identifikácie defektov, a to najmä tých, ktoré sa dajú len ťažko nájsť).
* Dobré komunikačné zručnosti, aktívne počúvanie, schopnosť byť tímovým hráčom (s cieľom efektívne komunikovať so všetkými zainteresovanými stranami, odovzdávať informácie ostatným, byť pochopený, reportovať defekty a diskutovať o nich).
* Analytické myslenie, kritické myslenie, kreativita (s cieľom zvyšovania efektivity testovania).
* Technické znalosti (s cieľom zvyšovania efektivity testovania, napr. použitím vhodných testovacích nástrojov).
* Znalosť domény (s cieľom mať schopnosť porozumieť koncovým používateľom alebo obchodným zástupcom a komunikovať s nimi).

Bežnou ľudskou vlastnosťou je obviňovanie nositeľov zlých správ a testeri sú často nositeľmi takých zlých správ. Z tohto dôvodu sú pre testerov kľúčové komunikačné schopnosti – oznamovanie výsledkov testov môže byť totiž vnímané ako kritika produktu a jeho autora. 

Termín konfirmačné skreslenie (confirmation bias) popisuje tendenciu človeka ťažko prijímať informácie, ktoré sú v rozpore s jeho súčasnými názormi. Ide o psychologický faktor, v dôsledku ktorého môžu niektorí ľudia vnímať testovanie ako deštruktívnu aktivitu, hoci významne prispieva k úspechu projektu a kvalite produktu. Pri snahe znížiť tieto vnímania by informácie o defektoch a zlyhaniach mali byť komunikované konštruktívne a bez emócií.

### Tímový prístup {#team-approach}

Jednou z dôležitých zručností testerov je schopnosť efektívne pracovať v tíme a pozitívne prispievať k tímovým cieľom. Tzv. tímový prístup (whole team approach, technika vychádzajúca z extrémneho programovania, pozri <#section:testing-in-context-of-software-development-life-cycle>) je postavený na tejto zručnosti. 

Pri tímovom prístupe môže každý člen tímu s potrebnými znalosťami a zručnosťami vykonávať akúkoľvek úlohu a každý člen tímu je zodpovedný za kvalitu. Členovia tímu zdieľajú rovnaký pracovný priestor, pretože spoločné umiestnenie v jednom fyzickom alebo virtuálnom priestore uľahčuje vzájomnú komunikáciu a interakciu. Tímový prístup zvyšuje tímovú dynamiku, zlepšuje komunikáciu a spoluprácu v rámci tímu a vytvára synergiu tým, že umožňuje využitie rôznych zručností v tíme v prospech projektu.

Ak má byť dosiahnutá požadovaná úroveň kvality, musia testeri úzko spolupracovať s ostatnými členmi tímu. To zahŕňa (okrem iného) spoluprácu s obchodnými zástupcami (ktorí môžu napr. pomôcť s vytvorením vhodných akceptačných testov) alebo s vývojármi (napr. s cieľom dosahovať spoločné dohody o stratégii testovania a o prístupoch k automatizácii testov). Testeri môžu tiež odovzdávať znalosť testovania ostatným členom tímu a ovplyvňovať vývoj produktu.

Tímový prístup nemusí byť v kontexte projektu vždy vhodnou metodikou. Typickým príkladom je testovanie bezpečnostne kritických scenárov, kedy je nutné zachovať vysokú úroveň nezávislosti testovania.

### Nezávislosť testovania

Určitá miera nezávislosti robí testerov efektívnejšími pri hľadaní defektov, čo je spôsobené rozdielmi medzi kognitívnym skreslením autorov (vývojárov) a testerov [@salman2016cognitive]. Nezávislosť však nie je náhrada za dobrú znalosť systému – aj vývojári môžu efektívne nájsť mnoho defektov vo svojom vlastnom kóde.

Pracovné produkty môžu byť testované ich autorom (nulová nezávislosť), kolegami autora z rovnakého tímu (malá nezávislosť), testermi mimo tímu autora, ale v rámci organizácie (vysoká nezávislosť) alebo testermi mimo organizácie (veľmi vysoká nezávislosť). Vo väčšine projektov je zvyčajne najlepšie vykonávať testovanie s viacerými úrovňami nezávislosti (napr. vývojári vykonávajúci testovanie komponentov a integračné testovanie komponentov, testovací tím vykonávajúci systémové testovanie a systémové integračné testovanie a obchodní zástupcovia vykonávajúci akceptačné testovanie).

Hlavným prínosom nezávislosti testovania je to, že nezávislí testeri dokážu pravdepodobnejšie rozpoznať rôzne druhy zlyhaní a defektov v porovnaní s vývojármi, a to z dôvodu ich odlišného zázemia, technického nadhľadu a predsudkov. Nezávislí testeri môžu navyše verifikovať, napadnúť či vyvrátiť predpoklady, ktoré mali zainteresované strany v čase prípravy špecifikácie či implementácie systému. 

Existujú však aj niektoré nevýhody. Nezávislí testeri môžu byť izolovaní od vývojového tímu, čo môže viesť
k nedostatočnej spolupráci, problémom v komunikácii alebo nepriateľskému vzťahu s vývojovým tímom. Vývojári môžu stratiť pocit zodpovednosti za kvalitu. Nezávislí testeri môžu byť úzkym miestom vo vývojovom procese alebo môžu byť vinení za oneskorenie pri vydávaní produktu.