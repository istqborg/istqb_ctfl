## Plánovanie testovania {#planning-testing}

### Účel a obsah plánu testovania

Plán testovania popisuje ciele, zdroje a procesy testovania v rámci projektu. Plán testovania:

* dokumentuje spôsob dosiahnutia cieľov testovania a harmonogram testovania,
* pomáha zabezpečiť, aby vykonávané testovacie činnosti spĺňali stanovené kritériá,
* slúži ako spôsob komunikácie s členmi tímu a ďalšími zainteresovanými stranami,
* preukazuje, že testovanie je v súlade s existujúcou politikou a stratégiou testovania (prípadne vysvetľuje, prečo sa od nich testovanie odchyľuje).

Plánovanie testovania je vodítkom pri uvažovaní testerov a núti ich zamyslieť sa nad budúcimi výzvami súvisiacimi s rizikami, harmonogramami, ľuďmi, nástrojmi, nákladmi, potrebným úsilím, atď. Proces prípravy plánu testovania je užitočným nástrojom na analýzu úsilia potrebného na dosiahnutie cieľov testovania stanovených v rámci projektu.

Typický plán testovania obsahuje:

* kontext testovania (napr. rozsah, ciele testovania, obmedzenia, testovacia báza),
* predpoklady a obmedzenia testovacieho projektu,
* zainteresované strany (napr. roly, zodpovednosti, relevantnosť pre testovanie, potreby náboru a školenia),
* plán komunikácie (napr. spôsoby a frekvenciu komunikácie, šablóny pre dokumentáciu),
* register rizík (napr. produktové a projektové riziká),
* prístup k testovaniu (napr. úrovne testovania, typy testovania, techniky testovania, výstupy z testovania, vstupné a výstupné kritériá, nezávislosť testovania, požadované metriky, požiadavky na testovacie dáta, požiadavky na testovacie prostredie, odchýlky od politiky a stratégie testovania),
* rozpočet a harmonogram.

Ďalšie podrobnosti o pláne testovania a jeho obsahu je možné nájsť v norme ISO/IEC/IEEE 29119-3 [@ISO29119-3].

### Prínos testerov pri plánovaní iterácií a vydaní

V iteratívnych SDLC sa obvykle vyskytujú dva druhy plánovania: plánovanie vydania a plánovanie iterácie.

**Plánovanie vydania** pozerá vpred smerom k vydaniu produktu, definuje a upravuje produktový backlog a môže zahŕňať rozpracovanie väčších používateľských scenárov do sady menších. Zároveň slúži ako základ pre definíciu prístupu k testovaniu a plánu testovania naprieč všetkými iteráciami. Testeri zapojení do plánovania vydania sa podieľajú na špecifikácii testovateľných používateľských scenárov a akceptačných kritérií (pozri <#section:collaborative-testing-approaches>), podieľajú sa na analýzach projektových a produktových rizík (pozri <#section:risk-management>), odhadujú potrebné úsilie na testovanie používateľských scenárov (pozri <#section:estimation-techniques>), stanovujú prístup k testovaniu a plánujú testovanie súvisiace s vydaním.

**Plánovanie iterácie** pozerá smerom ku koncu jednej iterácie a pracuje s backlogom iterácie. Testeri zapojení do plánovania iterácií sa podieľajú na podrobnej analýze rizík používateľských scenárov, stanovujú ich testovateľnosť, podieľajú sa na ich rozklade do úloh (najmä pre testovacie činnosti), odhadujú potrebné úsilie na testovanie pre všetky testovacie činnosti a prispievajú k identifikácii a spresňovaniu funkcionálnych a nefunkcionálnych aspektov testovaného objektu.

### Vstupné kritériá a výstupné kritériá {#entry-and-exit-criteria}

Vstupné kritériá určujú predpoklady pre realizáciu danej činnosti. Pokiaľ nie sú splnené vstupné kritériá, bude vykonanie testovacej činnosti pravdepodobne ťažšie, časovo náročnejšie, nákladnejšie a viac rizikové. Medzi typické vstupné kritériá patrí dostupnosť zdrojov (napr. ľudia, nástroje, prostredie, testovacie dáta, rozpočet, čas), dostupnosť testvéru (napr. testovacia báza, testovateľné požiadavky, používateľské scenáre, testovacie prípady) a počiatočná úroveň kvality testovaného objektu (napr. úspešnosť všetkých smoke testov).

Výstupné kritériá určujú podmienky, ktoré sa musia dosiahnuť, aby bolo možné vyhlásiť činnosť za dokončenú. Medzi typické výstupné kritériá patrí miera dôkladnosti (napr. dosiahnutá úroveň pokrytia, počet nevyriešených defektov, hustota defektov, počet neúspešných testovacích prípadov) a kritériá dokončenia (napr. vykonanie plánovaných testov, vykonanie statického testovania, zaznamenanie všetkých zistených defektov, automatizácia všetkých regresných testov).

Za platné výstupné kritériá možno tiež považovať vyčerpanie času alebo finančných prostriedkov. Za týchto okolností, je možné ukončiť testovanie aj v prípade nesplnenia ostatných výstupných kritérií, ak zainteresované strany preskúmali a akceptovali riziko nasadenia produktu do produkcie bez ďalšieho testovania.

V agilnom vývoji softvéru sa výstupné kritériá často nazývajú definícia hotového (Definition of Done - DoD) a určujú projektovú objektívnu metriku pre položky pripravené na vydanie. Vstupné kritériá, ktoré musí používateľský scenár spĺňať, aby sa mohli začať vývojové a/alebo testovacie činnosti, sa nazývajú definícia pripravenosti (Definition of Ready).

Vstupné a výstupné kritériá by mali byť definované pre každú úroveň testov a môžu sa líšiť v závislosti od stanovených cieľov testovania.

### Techniky na odhadovanie {#estimation-techniques}

Odhad potrebného úsilia na testovanie reprezentuje očakávané množstvo práce, ktoré bude potrebné na dosiahnutie cieľov testovania v projekte. Je dôležité zainteresovaným stranám objasniť, že odhad vychádza z momentálnych predpokladov a vždy v sebe nesie aj určitú mieru chybovosti, pričom platí, že odhad pre malé úlohy je obvykle presnejší ako pre veľké úlohy. Preto je pri odhadovaní vhodné rozložiť rozsiahlu úlohu na sadu menších a tie následne odhadnúť. Tieto učebné osnovy popisujú štyri techniky odhadovania.

**Odhad na základe pomerov**. Pri tejto technike založenej na metrikách sa zhromažďujú údaje z predchádzajúcich projektov v rámci organizácie, čo umožňuje odvodiť „štandardizované“ pomerové metriky (vzorce) pre podobné projekty. Takéto metriky odvodené z projektov v rámci organizácie (napr. prevzaté z historických údajov) sú vo všeobecnosti najlepším zdrojom, ktorý možno v procese odhadovania použiť na odhad potrebného úsilia na testovanie nového projektu. Ak bola napríklad v predchádzajúcom projekte úsilie vynaložené na vývoj a úsilie vynaložené na testovania v pomere 3:2 a v súčasnom projekte sa očakáva, že úsilie potrebné na vývoj bude predstavovať 600 človeko-dní, dá sa úsilie potrebné na testovania odhadnúť na 400 človeko-dní.

**Extrapolácia**. Pri tejto technike založenej na metrikách sa v aktuálnom projekte vykonáva čo najskôr meranie s cieľom zhromažďovať dáta. S dostatočným počtom pozorovaní (dát) možno potrebné zostávajúce úsilie aproximovať extrapoláciou týchto dát (obvykle použitím matematického modelu). Táto metóda je veľmi vhodná pre iteratívne modely SDLC, pretože tím môže napríklad extrapolovať úsilie potrebné na testovanie v nadchádzajúcej iterácii ako priemerne vynaložené úsilie z posledných troch iterácií.

**Wideband Delphi**. Pri tejto iteratívnej technike založenej na expertoch vykonávajú experti odhady založené na skúsenostiach. Každý taký expert (odborník) samostatne odhadne potrebné úsilie. Výsledky odhadov sú zhromaždené a pokiaľ sa objavia odchýlky mimo rozsahu dohodnutých hraníc, diskutujú experti o svojich aktuálnych odhadoch. Každý je potom požiadaný, aby na základe tejto spätnej väzby vykonal nový odhad, a to opäť samostatne. Tento proces sa opakuje, kým sa nedosiahne zhoda. Variantom Wideband Delphi, ktorá sa bežne používa pri agilnom vývoji softvéru je tzv. plánovací poker. Pri ňom sa odhady obvykle tvoria pomocou kariet s číslami, ktoré predstavujú mieru potrebného úsilia.

**Trojbodový odhad**. Pri tejto technike založenej na expertoch vykonávajú experti tri odhady: najoptimistickejší odhad (a), najpravdepodobnejší odhad (m) a najpesimistickejší odhad (b). Výsledný odhad (E) je ich vážený aritmetický priemer. V najpoužívanejšej verzii tejto techniky sa odhad vypočíta ako E = (a + 4 \* m + b) / 6. Výhodou tejto techniky je, že umožňuje expertom vypočítať chybu merania, obvykle vo forme smerodajnej odchýlky: SD = (b - a) / 6. Ak sú odhady (v človeko-hodinách) napr.: a = 6, m = 9 a b = 18, potom je výsledný odhad 10 ± 2 človeko-hodín (t. j. 8 - 12 človeko-hodín), pretože E = (6 + 4 \* 9 + 18) / 6 = 10 a SD = (18 - 6) / 6 = 2.

Viac informácií o týchto a mnohých ďalších technikách odhadovania úsilia potrebného na testovanie možno nájsť v [@kan2003metrics], [@vroon2013tmap] a [@westfall2016certified].


### Prioritizácia testovacích prípadov {#test-cases-prioritization}


Akonáhle sú testovacie prípady a testovacie procedúry vytvorené a zostavené do testovacích sád, je možné tieto testovacie sady radiť do harmonogramu vykonávania definujúceho poradie spúšťania.

Pri stanovení priorít testovacích prípadov je možné zohľadniť rôzne faktory. Najčastejšie používané stratégie prioritizácie testovacích prípadov sú nasledujúce:

* **Prioritizácia na základe rizík**, kedy poradie vykonávania testov vychádza z výsledkov analýzy rizík (pozri <#section:product-risks-analysis>). Najprv sa vykonajú testovacie prípady pokrývajúce najdôležitejšie riziká.
* **Prioritizácia na základe pokrytia**, kedy je poradie vykonávania testov založené na určitom pokrytí (napr. pokrytie príkazov). Testovacie prípady dosahujúce najvyššie pokrytie sú vykonávané ako prvé. V inom variante (nazývanom prioritizácia dodatočného pokrytia) sa najprv vykoná testovací prípad s najvyšším pokrytím. Každý nasledujúci testovací prípad je ten, ktorý dosiahne najvyššie pokrytie dodatočnej fukcionality.
* **Prioritizácia na základe požiadaviek**, kedy poradie vykonávania testov vychádza z priorít požiadaviek trasovateľných späť k zodpovedajúcim testovacím prípadom. Priority požiadaviek definujú zainteresované strany, testovacie prípady súvisiace s najdôležitejšími požiadavkami sú vykonávané ako prvé.

V ideálnom prípade by mali byť testovacie prípady zoradené na vykonávanie na základe úrovne ich priority, napríklad pomocou jednej z vyššie uvedených stratégií prioritizácie. Tento postup však nemusí fungovať, ak medzi testovacími prípadmi alebo testovanými funkcionalitami existujú závislosti. Ak testovací prípad s vyššou prioritou závisí od testovacieho prípadu s nižšou prioritou, musí byť najskôr vykonaný testovací prípad s nižšou prioritou.

Poradie vykonávania testov musí tiež zohľadňovať dostupnosť zdrojov, napr. požadovaných testovacích nástrojov, testovacieho prostredia alebo osôb, ktoré môžu byť k dispozícii iba po určitú dobu.

### Testovacia pyramída

Testovacia pyramída je model, ktorý ukazuje, že rôzne testy môžu mať rôznu granularitu. Predstavuje pomôcku pre tím pri automatizácii testov a smerovaní testovacieho úsilia poukázaním na to, ako sú rozličné ciele dosahované prostredníctvom rôznej miery automatizácie testovania.

Vrstvy pyramídy predstavujú skupiny testov. Čím vyššia vrstva, tým nižšia granularita testu, menšia izolácia testu a dlhšia doba vykonávania testu. Testy v spodnej vrstve sú malé, izolované, rýchle a overujú malú časť funkcionality, takže na dosiahnutie rozumného pokrytia je ich obvykle potrebné veľké množstvo. Horná vrstva predstavuje komplexné vysokoúrovňové E2E (end-to-end) testy. Tie sú všeobecne pomalšie ako testy z nižších vrstiev a obvykle overujú veľkú časť funkcionality, takže na dosiahnutie rozumného pokrytia je ich obvykle potrebných len niekoľko. Počet a pomenovanie jednotlivých vrstiev sa môže líšiť, napríklad pôvodný model testovacej pyramídy [@cohn2010succeeding] definuje tri vrstvy (testy komponentov, testy služieb a testy používateľského rozhrania). Iné modely definujú jednotkové testy (testy komponentov), ​​integračné testy komponentov (integračné testy komponentov) a end-to-end testy. Všeobecne možno použiť aj iné úrovne testovania (pozri <#section:testing-levels>).

### Kvadranty testovania

Kvadranty testovania definované Brianom Marickom [@marick2003survey], [@crispin2009agile], dávajú do súvislosti úrovne testovania s príslušnými typmi testovania, činnosťami, technikami testovania a pracovnými produktmi v agilnom vývoji softvéru. Model je pomôckou pre manažment testovania pri vizualizácii týchto vzťahov s cieľom zaisťovať, že všetky vhodné typy a úrovne testovania sú zahrnuté do SDLC, a pre pochopenie toho, že niektoré typy testovania sú pre určité úrovne testovania relevantnejšie ako iné. Poskytuje spôsob, ako od seba rozlíšiť a popísať typy testovania všetkým zainteresovaným stranám vrátane vývojárov, testerov a zástupcov biznisu.

V tomto modeli os Y rozlišuje testy zamerané na biznis alebo na technológiu a os X potom testy podporujúce tím (t. j. tie, ktoré pomáhajú usmerňovať vývojové aktivity) alebo revidujúce produkt (t. j. také, ktoré pomáhajú merať jeho správanie proti očakávaniam). Kombinácia týchto dvoch pohľadov (osí) určuje štyri kvadranty:

* **Kvadrant Q1 (zamerané na technológiu, podporujúce tím)**. Tento kvadrant obsahuje testy komponentov a integračné testy komponentov. Tieto testy by mali byť automatizované a zahrnuté do procesu CI.
- **Kvadrant Q2 (zamerané na biznis, podporujúci tím)**. Tento kvadrant obsahuje funkcionálne testy, príklady, testy používateľských scenárov, UX prototypy, testovanie rozhrania (API) a simulácie. Tieto testy overujú akceptačné kritériá a môžu byť manuálne aj automatizované.
- **Kvadrant Q3 (zamerané na biznis, revidujúce produkt)**. Tento kvadrant obsahuje prieskumné testovanie, testovanie použiteľnosti a používateľské akceptačné testovanie. Tieto testy sú používateľsky orientované a často manuálne.
- **Kvadrant Q4 (zamerané na technológiu, revidujúce produkt)**. Tento kvadrant obsahuje smoke testy a nefunkcionálne testy (okrem testov použiteľnosti). Tieto testy sú často automatizované.


## Manažment rizík {#risk-management}

Organizácie čelia mnohým interným a externým faktorom prinášajúcim neistotu v tom, či a kedy dosiahnu svoje ciele [@ISO31000]. Manažment rizík im umožňuje zvýšiť pravdepodobnosť dosiahnutia týchto cieľov, zlepšiť kvalitu ich produktov a zvýšiť dôveru zainteresovaných strán.

Hlavnými činnosťami v oblasti manažmentu rizík sú:

- **analýza rizík** (obsahuje identifikáciu a ohodnotenie rizík, pozri <#section:product-risks-analysis>),
- **riadenie rizík** (obsahuje zmierňovanie a monitoring rizík, pozri <#section:product-risk-management>).

Prístup k testovaniu, pri ktorom sú testovacie činnosti vyberané, prioritizované a riadené na základe analýzy rizík spoločne s riadením rizík, sa nazýva testovanie založené na rizikách.

### Definícia rizika a jeho atribúty

Riziko je možná udalosť, nebezpečenstvo, hrozba alebo situácia, ktorej výskyt má nepriaznivý vplyv. Riziko je možné charakterizovať dvoma faktormi:

* pravdepodobnosť rizika – pravdepodobnosť výskytu rizika vyjadrená v percentách alebo v intervale (0,1), t. j. hodnoty 0 a 1 nie sú súčasťou intervalu,
* vplyv rizika (škoda) – dôsledky výskytu takejto udalosti.

Tieto dva faktory vyjadrujú úroveň rizika, ktorá je jeho mierou (metrikou). Čím vyššia je úroveň rizika, tým dôležitejšie je jeho ošetrenie.

### Projektové a produktové riziká

Pri testovaní softvéru sa všeobecne zaoberáme dvoma typmi rizík – projektovými rizikami a produktovými rizikami.

**Projektové riziká** sa týkajú manažmentu a riadenia projektu. Medzi projektové riziká patria:

- organizačné problémy (napr. oneskorenie pri dodávaní pracovných produktov, nepresné odhady, znižovanie nákladov),
- problémy s ľuďmi (napr. nedostatočné zručnosti, konflikty, komunikačné problémy, nedostatok zamestnancov),
- technické problémy (napr. narastajúci rozsah projektu, zlá podpora z pohľadu nástrojov),
- problémy s dodávateľmi (napr. zlyhanie dodávky od tretej strany, krach dodávateľa).

Projektové riziká, ak sa vyskytnú, môžu mať vplyv na harmonogram, rozpočet alebo rozsah projektu, čo ovplyvňuje schopnosť projektu dosiahnuť svoje ciele.

**Produktové riziká** súvisia s kvalitatívnymi charakteristikami produktu (napr. popísanými v modeli kvality [@ISO25010]). Medzi príklady produktových rizík patria:

* chýbajúca alebo nesprávna funkcionalita,
* nesprávne výpočty,
* chyby pri behu (runtime errors),
* zlá architektúra,
* neefektívne algoritmy,
* nedostatočná doba odozvy,
* zlý používateľský zážitok,
* bezpečnostné zraniteľnosti.

Produktové riziká, ak sa vyskytnú, môžu mať rôzne negatívne dôsledky, napríklad:

* nespokojnosť používateľov,
* strata príjmov, dôvery, povesti,
* škody spôsobené tretím stranám,
* vysoké náklady na údržbu,
* preťaženie helpdesku,
* trestnoprávne postihy,
* fyzické poškodenie, zranenie, v extrémnych prípadoch smrť.

### Analýza produktových rizík {#product-risks-analysis}

 hľadiska testovania je cieľom analýzy produktových rizík poskytnúť povedomie o produktových rizikách so zámerom nasmerovať testovacie úsilie tak, aby došlo k minimalizácii miery zostávajúcich rizík. V ideálnom prípade začína analýza produktových rizík v ranej fáze SDLC. Analýza produktových rizík sa skladá z identifikácie a ohodnotenie rizík.

**Identifikácia rizík** spočíva vo vytvorení komplexného zoznamu rizík. Zainteresované strany môžu identifikovať riziká pomocou rôznych techník a nástrojov, napr. brainstormingu, workshopov, rozhovorov alebo diagramov príčin a následkov.

**Ohodnotenie rizík** zahŕňa kategorizáciu identifikovaných rizík, určenie ich pravdepodobnosti, dopadu a úrovne, stanovenie priorít a navrhnutie spôsobov ich riešenia. Kategorizácia pomáha pri priraďovaní zmierňujúcich opatrení, pretože zvyčajne možno riziká patriace do rovnakej kategórie zmierniť podobnými činnosťami.

Ohodnotenie rizík môže využívať kvantitatívny alebo kvalitatívny prístup, prípadne ich kombináciu. Pri kvantitatívnom prístupe sa úroveň rizika vypočíta ako násobok pravdepodobnosti rizika a dopadu rizika. Pri kvalitatívnom prístupe možno úroveň rizika stanoviť pomocou matice rizík.

Analýza produktových rizík môže ovplyvniť dôkladnosť a rozsah testovania. Jej výsledky sa používajú na:

* určenie rozsahu testovania, ktoré sa má vykonať,
* určenie konkrétnych úrovní testovania a návrhu typov testovania, ktoré sa majú vykonať,
* určenie techník testovania, ktoré majú byť použité,
* určenie pokrytia, ktoré sa má dosiahnuť,
* odhadu úsilia potrebného na testovanie vyžadovaného pre každú úlohu,
* stanovenie priorít testovania s cieľom čo najrýchlejšieho nachádzania kritických defektov,
* určenie, či by sa mohli na zníženie rizika použiť aj iné činnosti ako testovanie.

### Riadenie produktových rizík {#product-risk-management}

Riadenie produktových rizík zahŕňa všetky opatrenia, ktoré sú prijaté v reakcii na identifikované a ohodnotené produktové riziká. Skladá sa zo zmierňovania rizík a monitorovania rizík.

Obsahom **zmierňovania rizík** je zavedenie opatrení navrhnutých pri ohodnotení rizík s cieľom znížiť úroveň rizika. Akonáhle je riziko analyzované, je možné naň reagovať niekoľkými spôsobmi, napr. jeho zmiernením pomocou testovania, prijatím rizika, prenosom rizika alebo záložným plánom [@veenendaal2012prisma]. Opatrenia, ktoré možno prijať na zmiernenie produktových rizík prostredníctvom testovania, sú nasledujúce:

- výber testerov so skúsenosťami a zručnosťami vhodnými pre daný typ rizika,
- použitie vhodnej úrovne nezávislosti testovania,
- vykonanie revízií a statickej analýzy,
- použitie vhodných techník testovania a úrovní pokrytia,
- použitie vhodných typov testovania zameraných na dotknuté kvalitatívne charakteristiky,
- vykonanie dynamického testovania (vrátane regresného testovania).

Cieľom **monitorovania rizík** je zisťovanie či sú zmierňujúce opatrenia efektívne, získanie ďalších informácií pre zlepšenie ohodnotenia rizík a identifikácia novo vznikajúcich rizík.

## Monitorovanie, riadenie a dokončenie testovania {#monitoring-management-completion-of-testing}

**Monitorovanie testovania** sa zaoberá zhromažďovaním informácií o testovaní. Tieto informácie sa využívajú na posúdenie postupu prác pri testovaní a na stanovenie, či sú naplnené výstupné kritériá testovania alebo dokončené testovacie úlohy spojené s výstupnými kritériami (ako napr. splnenie cieľov na pokrytie produktových rizík, požiadaviek alebo akceptačných kritérií).

**Riadenie testovania** využíva informácie z monitorovania testovania na to, aby boli formou usmernenia poskytnuté pokyny a nevyhnutné nápravné opatrenia na dosiahnutie čo najúčinnejšieho a najefektívnejšieho testovania. Medzi príklady takýchto usmernení patria:

* prehodnotenie priorít testov pri výskyte identifikovaného rizika,
* prehodnotenie, či v dôsledku zmien (prepracovania) spĺňa daná položka testovania vstupné alebo výstupné kritériá,
* úprava harmonogramu testovania s ohľadom na oneskorenie v dodaní testovacieho prostredia,
* pridávanie nových zdrojov tam, kde sú potrebné a vtedy, keď sú potrebné.

**Pri dokončení testov** sa zhromažďujú dáta z dokončených testovacích činností za účelom konsolidácie skúseností, testvéru a ďalších dôležitých informácií. K činnostiam súvisiacim s dokončením testovania dochádza v rámci projektových míľnikov ako sú dokončenie úrovne testovania, dokončenie iterácie pri agilnom vývoji, dokončenie (alebo zrušenie) testovacieho projektu, vydanie softvérového systému alebo dokončenie servisného vydania (maintenance release).

### Metriky používané v testovaní {#metrics-in-testing}

Testovacie metriky sú zhromažďované s cieľom ukazovať postup voči plánovanému harmonogramu a rozpočtu, aktuálnu kvalitu testovaného objektu a efektivitu testovacích činností s ohľadom na ciele projektu alebo iterácie. Monitorovanie testovania zhromažďuje rôzne metriky na podporu riadenia a dokončenia testovania.

Medzi typické testovacie metriky patria:

* metriky o postupe projektu (napr. dokončenie úlohy, využitie zdrojov, úsilie potrebné na testovanie),
* metriky o postupe testovania (napr. postup implementácie testovacích prípadov, postup prípravy testovacích prostredí, počet spustených / nespustených testovacích prípadov, počet vykonaných testov, ktoré prešli / zlyhali, doba vykonania testu),
* metriky týkajúce sa kvality produktu (napr. dostupnosť, doba odozvy, stredná doba medzi poruchami),
* metriky nad defektmi (napr. počet a priority zistených / opravených defektov, hustota defektov - defect density , percento odhalených defektov – defect detection percentage, DPP),
* metriky nad rizikami (napr. miera zostávajúcich rizík),
* metriky pokrytia (napr. pokrytie požiadaviek, pokrytie kódu),
* metriky týkajúce sa nákladov (napr. náklady na testovanie, náklady na kvalitu v rámci organizácie).

### Účel, obsah a cieľové skupiny správ z testovania {#purpose-content-target-of-test-reports}

Cieľom podávania správ o testovaní je zhrnutie a komunikácia informácií z testovania počas jeho priebehu a po ňom. Správy o postupe testovania podporujú priebežné riadenie testovania. Musia poskytovať dostatok informácií na vykonanie zmien v harmonograme testovania, zdrojoch alebo plánu testovania, ak sú tieto zmeny potrebné z dôvodu odchýlky od plánu alebo zmeny okolností. Správy o dokončení testovania sumarizujú určitú fázu testovania (napr. úroveň testovania, testovací cyklus, iteráciu) a môžu poskytnúť informácie pre následné testovanie.

Počas monitorovania a riadenia testovania vytvára testovací tím správy o postupe testovania s cieľom poskytovať zainteresovaným stranám informácie. Správy o postupe testovania sú obvykle generované pravidelne (napr. denne, týždenne atď.) a obsahujú:

* testovacie obdobie,
* postup prác pri testovaní (napr. náskok alebo oneskorenie oproti harmonogramu) vrátane všetkých významných odchýlok,
* prekážky pri testovaní a ich riešenia,
* testovacie metriky (pozri <#section:metrics-in-testing>),
* nové a zmenené riziká počas testovacieho obdobia,
* testovanie plánované pre nasledujúce obdobie.

Správa o dokončení testovania sa pripravuje v priebehu fázy dokončenia testovania, kedy je projekt, úroveň testovania alebo typ testovania ukončený, a kedy sú (v ideálnom prípade) splnené stanovené výstupné kritériá. Táto správa využíva informácie z čiastkových správ o postupe testovania a dopĺňa ich o ďalšie dáta. Typické správy o dokončení testovania obsahujú:

* zhrnutie testov,
* vyhodnotenie testovania a kvality produktu na základe pôvodného plánu testovania (t. j. cieľov testovania a výstupných kritérií),
* odchýlky od plánu testovania (napr. rozdiely oproti plánovanému harmonogramu, trvaniu a náročnosti),
* prekážky pri testovaní a ich riešenia,
* testovacie metriky založené na správach o postupe testovania,
* neošetrené riziká, nevyriešené defekty,
* získané skúsenosti (lessons learned), ktoré sú relevantné pre testovanie.

Rôzne cieľové skupiny potrebujú v týchto správach rôzne informácie a ovplyvňujú tým mieru formálnosti a frekvenciu podávania správ. Podávanie správ o postupe prác pri testovaní ostatným členom rovnakého tímu je väčšinou časté a neformálne, zatiaľ čo podávanie správ o dokončení testovania z ukončeného projektu sa vykonáva typicky iba raz, a to podľa definovanej šablóny.

V norme ISO/IEC/IEEE 29119-3 [@ISO29119-3] možno nájsť šablóny a príklady správ o postupe testovania (nazývané správy o stave testovania) a správ o dokončení testovania.

### Komunikovanie stavu testovania

Optimálny spôsob komunikovania stavu testovania sa líši v závislosti na potrebách manažmentu testovania, stratégiách testovania v organizácii, regulatórnych normách alebo v prípade samoorganizovaných tímov (pozri <#section:team-approach>) na samotnom tíme. Medzi možnosti komunikácie patria:

* verbálna komunikácia s členmi tímu a ďalšími zainteresovanými stranami,
* dashboardy (napr. CI/CD dashboard, tabule s úlohami a grafy burn-down),
* elektronické komunikačné kanály (napr. e-mail, chat),
* online dokumentácia,
* formálne správy z testovania (pozri <#section:purpose-content-target-of-test-reports>).

Je možné použiť jednu z uvedených možností alebo ich kombináciu. Formálnejšia komunikácia môže byť vhodnejšia pre distribuované tímy, kde nie je priama osobná komunikácia vždy možná kvôli geografickej vzdialenosti alebo časovým posunom. Obvykle sa rôzne zainteresované strany zaujímajú o iný typ informácií, preto by mala byť komunikácia zodpovedajúcim spôsobom prispôsobená.

## Konfiguračný manažment {#configuration-management}

V oblasti testovania je konfiguračný manažment disciplína, ktorá slúži na identifikáciu, riadenie a sledovanie pracovných produktov. Konfiguračnými položkami môžu byť akékoľvek plány testovania, stratégie testovania, testovacie podmienky, testovacie prípady, skripty, výsledky testov, protokoly testov (test logs) a správy z testovania.

V prípade komplexnej konfiguračnej položky (napr. testovacie prostredie) je možné v rámci konfiguračného manažmentu zaznamenávať čiastkové položky, z ktorých sa táto komplexná položka skladá, ich vzťahy a verzie. V momente, keď je konfiguračná položka schválená pre testovanie, stáva sa súčasťou tzv. baseline a je možné ju meniť iba prostredníctvom formálneho procesu na riadenie zmien.

V prípade vytvorenia novej baseline je úlohou konfiguračného manažmentu uchovávať záznamy o všetkých zmenených konfiguračných položkách. Pokiaľ je napríklad nutné reprodukovať predchádzajúce výsledky testov, je možné vrátiť sa k predchádzajúcej baseline.

Konfiguračný manažment ako podporná disciplína testovania zaisťuje nasledujúce:

* Všetky konfiguračné položky vrátane položiek testovania (jednotlivých častí testovaného objektu) sú jednoznačne identifikované, ich verzie sú riadené, všetky zmeny sú evidované a vzťahy s inými konfiguračnými položkami sú zaznamenané tak, aby bolo možné zaistiť sledovateľnosť v priebehu celého procesu testovania.
* V dokumentácii testovania vedú na všetky identifikované dokumenty a softvérové ​​položky jednoznačné odkazy.

Kontinuálna integrácia, kontinuálne dodávanie, kontinuálne nasadzovanie a s týmito procesmi súvisiace testovanie sú obvykle implementované ako súčasť automatizovanej DevOps pipeline (pozri <#section:devops-and-testing>), ktorej súčasťou je obvykle aj automatizovaný konfiguračný manažment.


## Manažment defektov {#defects-management}

Keďže jedným z hlavných cieľov testovania je nájdenie defektov, zavedenie procesu manažmentu defekt je nevyhnutné. Napriek tomu, že sa hovorí o "defektoch", platí, že nahlásené anomálie môžu byť skutočné defekty alebo aj niečo iné (napr. chybné výsledky testov alebo zmenové požiadavky). Toto je vyhodnocované v rámci spracovania správy o defekte. Anomálie môžu byť hlásené v ktorejkoľvek fáze SDLC a forma ich hlásenia závisí od použitého SDLC.

Ako základné minimum musí proces manažmentu defektov obsahovať pracovný postup (workflow) pre spracovanie jednotlivých anomálií od ich odhalenia až po ich uzavretie a pravidlá pre ich klasifikáciu.
Tento pracovný postup obvykle pozostáva z činností, ktorých cieľom je zaznamenávať nahlásené anomálie, analyzovať ich a klasifikovať, rozhodnúť o vhodnej reakcii (typicky opraviť alebo neriešiť) a uzavretie správy o defekte. Tento proces musia dodržiavať všetky zúčastnené strany.

Podobným spôsobom je vhodné riešiť aj defekty zistené statickým testovaním (najmä statickou analýzou).

Platí, že nie všetky nahlásené anomálie musia byť nutne skutočné defekty (napr. falošne pozitívne výsledky testov alebo zmenové požiadavky). Toto vyhodnotenie je vykonávané v rámci spracovania reportu o defekte. Reporty o defekte majú obvykle nasledujúce ciele:

* Poskytovať osobám zodpovedným za spracovanie a riešenie hlásených defektov dostatočné informácie pre vyriešenie problému.
* Poskytovať spôsob sledovania kvality pracovného produktu.
* Navrhovať nápady na zlepšovanie procesov vývoja a testovania.

Report o defekte zaznamenaná počas dynamického testovania obvykle obsahuje:

* jedinečný identifikátor,
* názov obsahujúci krátke zhrnutie reportovanej anomálie,
* dátum zistenia anomálie, reportujúca organizácia a autor (vrátane role autora),
* identifikáciu testovaného objektu a testovacieho prostredia,
* kontext defektu (napr. vykonaný testovací prípad, vykonaná testovacia činnosť, fáza SDLC a ďalšie relevantné informácie ako napr. použitá technika testovania, použitý kontrolný zoznam alebo použité testovacie dáta),
* popis zlyhania umožňujúci reprodukciu a vyriešenie vrátane krokov, ktoré anomáliu vyvolali, všetkých relevantných protokolov testov (test logs), záloh databáz, snímok obrazovky alebo videozáznamov,
* očakávané a skutočné výsledky,
* závažnosť defektu (mieru dopadu) na záujmy zainteresovaných strán alebo na požiadavky,
* naliehavosť / prioritu opravy,
* stav defektu (napr. otvorený, odložený, duplicitný, čakajúci na opravu, čakajúci na konfirmačné testovanie, znovu otvorený, uzavretý, zamietnutý),
* odkazy (napr. na testovací prípad).

Niektoré z týchto informácií môžu byť automaticky vkladané nástrojom pre manažment defektov (napr. identifikátor, dátum, autor a počiatočný stav). Šablóny dokumentov pre report o defekte a príklady reportov o defekte možno nájsť v norme STN ISO/IEC/IEEE 29119-3 [@ISO29119-3] (norma však používa termín správa o incidente).
