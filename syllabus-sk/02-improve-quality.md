## Testovanie v kontexte životného cyklu vývoja softvéru {#testing-in-context-of-software-development-life-cycle}

Model životného cyklu vývoja softvéru (SDLC) je zovšeobecnený proces vývoja softvéru. Určuje, ako spolu logicky  
I chronologicky súvisia rôzne fázy vývoja a typy činností vykonávaných v rámci tohto procesu. Medzi kategórie modelov SDLC patria sekvenčné modely vývoja (napr. vodopádový model, V-model), iteratívne modely vývoja (napr. špirálový model, prototypovanie) a inkrementálne vývojové modely (napr. Rational Unified Process).

Niektoré činnosti v rámci procesov vývoja softvéru je možné tiež popísať podrobnejšími metódami vývoja softvéru  
a agilnými postupmi. Medzi takéto metódy patrí vývoj riadený akceptačnými testami (ATDD – acceptance test-driven development), vývoj riadený správaním (BDD – behavior-driven development), návrh riadený doménou (DDD – domain-driven design), extrémne programovanie (XP – extreme programming), vývoj riadený funkcionalitou (FDD - feature-driven development), Kanban, Lean IT, Scrum a vývoj riadený testovaním (TDD – test-driven development).

### Vplyv životného cyklu vývoja softvéru na testovanie


Aby bolo testovanie úspešné, musí byť prispôsobené SDLC. Voľba SDLC má vplyv na:

* rozsah a načasovanie testovacích činností (napr. úrovne testovania a typy testovania),
* úroveň detailu testovacej dokumentácie,
* voľbu techník testovania a prístupu k testovaniu,
* rozsah automatizácie testov,
* roly a zodpovednosti testerov.

V sekvenčných modeloch vývoja sa testeri v počiatočných fázach obvykle zúčastňujú revízií požiadaviek, testovacej analýzy a návrhu testov. Keďže je spustiteľný kód obvykle vytvorený až v neskorších fázach SDLC, nemožno v týchto počiatočných fázach používať techniky dynamického testovania.

V niektorých iteratívnych a inkrementálnych vývojových modeloch sa predpokladá, že výsledkom každej iterácie je funkčný prototyp alebo prírastok produktu. To znamená, že v každej iterácii môže byť vykonané statické  
aj dynamické testovanie, a to vo všetkých úrovniach testovania. Časté dodávanie takýchto prírastkov vyžaduje rýchlu spätnú väzbu a rozsiahle regresné testovanie.

Agilný vývoj softvéru (s využitím iteratívnych a inkrementálnych modelov) predpokladá, že v priebehu projektu môže dôjsť k zmene. Preto je v agilných projektoch uprednostňovaná skôr stručnejšia dokumentácia pracovných produktov, a naopak rozsiahla automatizácia testov, ktorá uľahčuje regresné testovanie. Väčšina manuálnych testov sa často vykonáva pomocou testovacích techník založených na skúsenostiach (pozri <#section:experience-based-testing-techniques>), pri ktorých sa nevyžaduje vykonanie rozsiahlej testovacej analýzy a návrhu testov.

### Životný cyklus vývoja softvéru a osvedčené testovacie postupy

Medzi osvedčené testovacie postupy, nezávisle na zvolenom modeli SDLC, patria:

* Ku každej vývojovej činnosti existuje zodpovedajúca testovacia činnosť, takže všetky vývojové činnosti podliehajú riadeniu kvality.
* Existujú rôzne úrovne testovania (pozri <#section:testing-levels>) a každá má svoje špecifické (a niekedy aj odlišné) ciele. Tým je testovanie primerane detailné a zároveň nedochádza k nadbytočnostiam.
* Testovacia analýza a návrh testov pre danú úroveň začína počas zodpovedajúcej vývojovej fázy SDLC, takže je splnený princíp včasného testovania (pozri <#section:testing-principles>)
* V okamihu, kedy je k dispozícii pracovná verzia (draft) ľubovoľného pracovného produktu, sú do jeho revízie zapojení testeri, čo (ako forma včasného testovania a včasnej detekcie defektov) podporuje prístup shift-left (pozri <#section:shift-left-approach>).

## Vývoj softvéru riadený testovaním {#test-driven-software-development}

TDD, ATDD a BDD sú podobné prístupy k vývoju, keď sú testy definované ako prostriedok na riadenie vývoja. Každý z týchto prístupov je aplikáciou princípu včasného testovania (pozri <#section:testing-principles>) a uplatňuje prístup shift-left (pozri <#section:shift-left-approach>) – testy sú definované pred tvorbou samotného kódu. Všetky podporujú iteratívny model vývoja a sú charakterizované nasledovne:


**Vývoj riadený testami (TDD)**

* Písanie kódu je riadené pomocou testovacích prípadov (namiesto rozsiahleho návrhu softvéru) [@beck2003test].
* Najprv sú spísané testy a až následne kód, a ten tak, aby týmto testom vyhovoval. Následne môžu (ale nemusia) byť testy a kód refaktorované.

**Vývoj riadený akceptačnými testami (ATDD)**

* Odvodzuje testy z akceptačných kritérií ako súčasť procesu návrhu systému [@gartner2012atdd].
* Daná časť aplikácie je vytvorená tak, aby vyhovovala testom napísaným pred samotným vývojom.

Viac informácií o ATDD možno nájsť v kapitole <#section:atdd>.

**Vývoj riadený správaním (BDD)**

* Požadované správanie aplikácie je popísané testovacími prípadmi napísanými v jednoduchej forme prirodzeného jazyka zrozumiteľného pre zainteresované strany. Obvykle je využitý formát Given/When/Then (Daná podmienka/Podmienka/Akcia) [@chelimsky2010rspec].
* Testovacie prípady sú následne automaticky preložené do spustiteľných testov.

Pre všetky vyššie uvedené prístupy môžu byť testy automatizované (ale nemusia) s cieľom podporiť kvalitu pri budúcich úpravách alebo refaktoringu.

### DevOps a testovanie {#devops-and-testing}

DevOps je prístup k vývoju softvéru, ktorý je postavený na synergii medzi oddeleniami vývoja (vrátane testovania) a prevádzky s cieľom dosahovania definovaných spoločných cieľov. DevOps vyžaduje zmenu kultúry v rámci organizácie tak, aby sa medzi týmito dvoma organizačnými jednotkami preklenuli medzery a zároveň sa k nim pristupovalo s rovnakou dôležitosťou. DevOps podporuje autonómiu tímu, rýchlu spätnú väzbu, integrované sady nástrojov a použitie technických prístupov ako je kontinuálna integrácia (CI – continuous integration) a kontinuálne nasadzovanie (CD – continuous delivery). To umožňuje tímom vytvárať, testovať a vydávať kvalitný kód rýchlejšie prostredníctvom definovanej DevOps pipeline [@kim2016devops].

Z pohľadu testovania má DevOps tieto výhody:

* Poskytuje rýchlu spätnú väzbu o kvalite (nového) kódu a o nepriaznivom vplyve na doterajšiu funkčnosť systému/komponenty.
* Vďaka CI podporuje prístup shift-left pri testovaní (pozri <#section:shift-left-approach>) tým, že motivuje vývojárov k písaniu kvalitného kódu podporovaného testovaním komponentov a statickou analýzou.
* Propaguje automatizované spracovanie (napr. CI/CD), ktoré uľahčuje vytváranie stabilných testovacích prostredí.
* Zvyšuje dôraz na nefunkcionálne charakteristiky kvality (napr. výkon alebo spoľahlivosť).
* Automatizáciou prostredníctvom pipeline znižuje potrebu opakovaného manuálneho testovania.
* Minimalizuje riziko regresie vďaka rozsahu a miere automatizovaných regresných testov.

DevOps má aj niektoré riziká a nevýhody:

* Musí byť definovaná a zavedená DevOps pipeline.
* Musia byť zavedené a udržiavané nástroje CI/CD.
* Automatizované testy vyžadujú dodatočné investície a môže byť ťažké ich vytvoriť a udržiavať.
* Hoci DevOps predpokladá vyšší rozsah automatizovaného testovania, nemožno zabúdať ani na manuálne testovanie, a to najmä z pohľadu koncového užívateľa

###  Prístup shift-left {#shift-left-approach}

Princíp včasného testovania (pozri <#section:testing-principles>) je niekedy označovaný ako shift-left (posun doľava v zmysle časovej osi), kde je testovanie vykonávané v skorších fázach SDLC. Shift-left odporúča začať s testovacími činnosťami skôr (napr. nečakať na implementáciu kódu alebo na integráciu komponentov), ​​ale neznamená to, že by testovanie v neskorších fázach malo byť zanedbávané.

Existujú niektoré osvedčené postupy, na ktorých je možné demonštrovať aplikáciu tohto prístupu:

* Revidovanie špecifikácií z pohľadu testovania, ktoré nachádza potenciálne defekty ako sú nejednoznačnosti, neúplnosti a nezrovnalosti.
* Písanie testovacích prípadov pred napísaním kódu a spustenie kódu v sade testovacieho vybavenia (test harness) počas vývoja kódu.
* Používanie CI alebo lepšie CD, pretože prichádza s rýchlou spätnou väzbou a automatizovanými testami komponentov, ktoré sú spoločne s kódom uložené do repozitára.
* Spúšťanie statickej analýzy zdrojového kódu pred dynamickým testovaním, alebo ako súčasť daného automatizovaného procesu.
* Vykonávanie nefunkcionálnych testov hneď v úrovni testovania komponentov (pokiaľ je to možné). Ide tiež o formu shift-left princípu, pretože obvykle sú tieto typy testovania vykonávané v neskorších fázach SDLC, keď je k dispozícii kompletný systém a zodpovedajúce testovacie prostredie.

Zavedenie shift-left prístupu môže v počiatočných fázach znamenať potrebu preškolenia tímu, zvýšenia prácnosti a/alebo nákladov, ale v neskorších fázach naopak šetrí vynaložené úsilie a/alebo náklady.

Je dôležité, aby boli zainteresované strany presvedčené o užitočnosti tohto konceptu a podporovali ho.

### Retrospektívy a zlepšovanie procesov {#retrospectives-and-process-improvement}

Retrospektívy (známe tiež ako po-projektové schôdzky alebo projektové retrospektívy) sa často konajú na konci projektu alebo iterácie, pri dosiahnutí míľnika alebo podľa potreby (ad-hoc). Načasovanie a organizácia retrospektív závisí od konkrétneho modelu SDLC. Účastníci týchto schôdzok (nielen testeri, ale aj napr. vývojári, architekti, vlastníci produktov, biznisoví analytici) obvykle preberajú:

* Čo bolo úspešné a malo by sa zachovať?
* Čo sa nepodarilo a dalo by sa zlepšiť?
* Ako implementovať návrhy na zlepšenie a zabezpečiť v budúcnosti trvalú úspešnosť?

Výstupy z retrospektív by mali byť zaznamenané, zvyčajne sú súčasťou súhrnnej správa z testovania (pozri <#section:purpose-content-target-of-test-reports>). Retrospektívy sú z hľadiska nastavenia procesu kontinuálneho zlepšovania kritické a je dôležité, aby boli všetky odporúčané opatrenia sledované (a dodržiavané).

Medzi typické prínosy retrospektív z pohľadu testovania patria:

* Zvyšovanie efektivity / účinnosti testov (napr. z dôvodu implementácie návrhov na zlepšenie procesov).
* Zvyšovanie kvality testwaru (napr. spoločnou revíziou testovacích procesov).
* Stmeľovanie tímu a vzájomné učenie (napr. ako výsledok možnosti hlásiť problémy a navrhovať zlepšenie).
* Zlepšovanie kvality testovacej bázy (napr. vyriešením nedostatkov v rozsahu a kvalite požiadaviek).
* Zlepšovanie spolupráce medzi vývojom a testovaním (napr. vďaka pravidelným revíziám a optimalizácii vzájomnej spolupráce).

## Úrovne testovania a typy testovania

Úrovne testovania sú skupiny testovacích činností, ktoré sú organizované a riadené spoločne. Každá úroveň testovania je inštanciou procesu testovania tvorenou činnosťami vykonávanými vo vzťahu k softvéru v danej fáze vývoja, od jednotlivých komponentov až po celé systémy, alebo prípadne aj systémy systémov.

Úrovne testovania súvisia s ďalšími činnosťami v rámci životného cyklu vývoja softvéru. V sekvenčných modeloch SDLC sú úrovne testovania často definované tak, že výstupné kritériá jednej úrovne sú súčasťou vstupných kritérií ďalšej úrovne. To ale nemusí platiť v niektorých iteratívnych modeloch, kde sa úrovne testovania môžu v čase prekrývať a vývojové činnosti môžu preklenúť viac úrovní testovania.

Typy testovania sú skupiny testovacích činností súvisiace so špecifickými kvalitatívnymi charakteristikami a väčšinu týchto činností možno vykonávať v ľubovoľnej úrovni testovania

### Úrovne testovania {#testing-levels}

V týchto učebných osnovách je popísaných nasledujúcich päť úrovní testovania:

* **Testovanie komponentov** (označované aj ako jednotkové testovanie, unit testing) sa zameriava na testovanie izolovaných komponentov. Na ich vykonávanie je často potrebný špeciálny softvér, napr. rôzne sady testovacieho vybavenia (test harness) alebo frameworky pre jednotkové testovanie. Testovanie komponentov obvykle vykonávajú vývojári vo svojich vývojových prostrediach.
* **Integračné testovanie komponentov** (označované tiež ako integračné testovanie jednotiek) sa zameriava na testovanie rozhrania a interakcií medzi komponentmi. Toto testovanie je silne závislé na zvolenej integračnej stratégii (napr. zdola-hore, zhora-dole alebo tzv. veľký tresk).
* **Systémové testovanie** sa zameriava na celkové správanie a schopnosti celého systému alebo produktu, často vrátane funkcionálneho testovania komplexných (end-to-end) úloh a nefunkcionálneho testovania kvalitatívnych charakteristík. Niektoré z nich (napr. použiteľnosť) je vhodnejšie testovať na úplnom systéme vo vhodnom testovacom prostredí. Okrem iného je možné využívať aj simulácie subsystémov. Systémové testovanie vychádza zo špecifikácií systému a môže byť vykonávané nezávislým testovacím tímom.
* **Systémové integračné testovanie** sa zameriava na testovanie rozhrania medzi testovaným systémom a ďalšími systémami alebo externými službami. Pre systémové integračné testovanie je potrebné mať vhodné testovacie prostredie, pokiaľ možno podobné prevádzkovému.
* **Akceptačné testovanie** sa zameriava na preukázanie pripravenosti systému na nasadenie do produkčného prostredia a validuje, že systém spĺňa biznisové potreby užívateľa. V ideálnom prípade by akceptačné testovanie mali vykonávať koncoví používatelia. Najčastejšie formy akceptačného testovania sú: užívateľské akceptačné testovanie (UAT), prevádzkové akceptačné testovanie, zmluvné a regulačné akceptačné testovanie, alfa testovanie a beta testovanie.

Aby nedochádzalo k prekrývaniu činností pri testovaní v jednotlivých úrovniach, čiastkové úrovne testovania sa odlišujú špecifickou definíciou rôznych atribútov. Medzi najdôležitejšie atribúty patria:

* testovaný objekt,
* ciele testovania,
* testovacia báza,
* defekty a zlyhania,
* prístup a zodpovednosti.

### Typy testovania

Existuje mnoho typov testovania, ktoré je možné na projektoch použiť. Tieto učebné osnovy sa zaoberajú štyrmi typmi testovania.

**Funkcionálne testovanie** overuje funkcionality, ktoré by komponent alebo systém mal vykonávať. Funkcionality predstavujú to, „čo“ by mal systém robiť. Hlavným cieľom funkcionálneho testovania je kontrola funkcionálnej úplnosti, funkcionálnej správnosti a funkcionálnej vhodnosti.

**Nefunkcionálne testovanie** vyhodnocuje nefunkcionálne charakteristiky komponentu alebo systému a dáva tak odpoveď na otázku „ako dobre sa systém chová“. Zoznam nefunkcionálnych charakteristík kvality softvéru možno nájsť v norme ISO/IEC 25010 [@ISO25010]:

- výkonnostná efektivita,
- kompatibilita,
- použiteľnosť,
- spoľahlivosť,
- bezpečnosť,
- udržovateľnosť,
- prenositeľnosť.

Veľa nefunkcionálnych testov je odvodených z funkcionálnych. Oba typy používajú rovnaké testovacie prípady, ale nefunkcionálne kontrolujú, či je pri danej funkcionalite splnené aj nejaké nefunkcionálne obmedzenie (napr. že je všetko vykonané v určenom čase alebo či môže byť daná funkčnosť prenesená na novú platformu). Neskoré odhalenie nefunkcionálneho defektu môže predstavovať vážnu hrozbu pre úspech projektu.

Niekedy je vhodné, aby nefunkcionálne testovanie začalo už v ranej fáze SDLC (napr. ako súčasť revízií a pri testovaní komponentov alebo systémovom testovaní) a niekedy je nutné využiť veľmi špecifické testovacie prostredie ako je napríklad laboratórium na testovanie použiteľnosti.

**Testovanie čiernej skrinky** (pozri <#section:black-box-testing-techniques>) je založené na špecifikácii a odvodzuje testy z dokumentácie testovaného objektu (teda nie zo správania samotného objektu). Hlavným cieľom testovania čiernej skrinky je kontrola správania systému podľa jeho špecifikácie.

**Testovanie bielej skrinky** (pozri <#section:white-box-testing-techniques>) je založené na štruktúre a odvodzuje testy z implementácie systému alebo z jeho vnútornej štruktúry, čo je napr. kód, architektúra, pracovné toky (workflows) alebo dátové toky. Hlavným cieľom testovania bielej skrinky je dosahovať dostatočné pokrytie testovanej štruktúry (napr. kódu).

Všetky štyri vyššie uvedené typy testovania je možné aplikovať vo všetkých úrovniach testovania, aj keď konkrétna implementácia bude v každej úrovni odlišná. Na odvodenie testovacích podmienok a testovacích prípadov pre všetky uvedené typy testovania je možné použiť rôzne techniky testovania.

### Konfirmačné a regresné testovanie {#confirmation-and-regression-testing}


Pokiaľ sa v komponente alebo systéme vykonávajú zmeny, je obvykle ich cieľom vylepšenie (pridaním novej funkcionality) alebo oprava (odstránením defektu). Následné testovanie by potom malo zahŕňať konfirmačné testovanie aj regresné testovanie.

**Konfirmačné testovanie** overuje, či bol pôvodný defekt úspešne opravený. V závislosti na riziku je možné otestovať opravenú verziu softvéru niekoľkými rôznymi spôsobmi, napr.

* Vykonaním všetkých testovacích prípadov, ktoré predtým zlyhali kvôli defektu.
* Pridaním nových testov s cieľom pokrývať všetky zmeny potrebné na opravu defektu.

V prípadoch, keď je na opravu defektu málo času alebo finančných prostriedkov, môže byť konfirmačné testovanie obmedzené na jednoduché vykonanie krokov, ktoré by mali reprodukovať pôvodné zlyhanie spôsobené defektom a skontrolovať, či k zlyhaniu nedochádza.

**Regresné testovanie** overuje, či nedošlo k žiadnym nežiadúcim dopadom po realizovaných zmenách, vrátane opráv, ktoré už boli potvrdené konfirmačným testovaním. Tieto nežiadúce dopady by mohli ovplyvniť ako komponent, kde bola zmena vykonaná, tak aj iné komponenty v rovnakom systéme alebo dokonca iné prepojené systémy. Regresné testovanie nemusí byť obmedzené na samotný testovaný objekt, ale môže tiež súvisieť s prostredím. Odporúča sa preto pred testovaním najskôr vykonať tzv. analýzu dopadu s cieľom optimalizovať rozsah regresného testovania. Analýza dopadu ukazuje, ktoré časti softvéru by mohli byť ovplyvnené.

Sady regresných testov sa spúšťajú mnohokrát a obvykle sa ich počet zvyšuje s každou novou iteráciou alebo vydaním, preto sú vhodným kandidátom na automatizáciu testovania. Automatizácia týchto testov by mala začať už v raných fázach projektu (pozri <#section:test-tools>). Automatizované regresné testy je vhodné zaradiť do CI pipeline (napr. DevOps pipeline, pozri <#section:devops-and-testing>). Regresné testy môžu byť podľa situácie vykonávané v rôznych úrovniach testovania.

Konfirmačné a/alebo regresné testovanie testovaného objektu je nutné použiť v tých úrovniach testovania, kde došlo k opravám defektov a/alebo sú v nich vykonané zmeny.

## Testovanie počas údržby

Existujú rôzne druhy údržby s rôznymi cieľmi, napr. oprava, adaptácia na zmenu prostredia, zlepšenie výkonu alebo zlepšenie udržovateľnosti (pozri normu ISO/IEC 14764 [@ISO14764]). Údržba môže byť ako plánovaná, tak neplánovaná (hotfix). Pred vykonaním zmeny je možné taktiež vykonať analýzu dopadu, ktorá pomôže pri rozhodovaní, či by zmena mala byť vykonaná, a to na základe potenciálnych dôsledkov v iných oblastiach systému. Testovanie zmien systému, ktorý je už v produkcii zahŕňa vyhodnotenie úspešnosti implementácie zmeny, ako aj kontrolu možnej regresie  
v nezmenených častiach systému (čo je obvykle väčšina systému).

Rozsah testovania počas údržby závisí od týchto faktorov:

* miera rizika zmeny,
* veľkosť existujúceho systému,
* rozsah zmeny.

Spúšťače (aktivačné udalosti) údržby a testovania údržby možno rozdeliť takto:

* Úpravy ako sú plánované vylepšenia (napr. v celom vydaní), opravné zmeny alebo hotfixy.
* Aktualizácia alebo migrácia prevádzkového prostredia (napríklad z jednej platformy na inú), kedy je nutné vykonať testy spojené s novým prostredím a zmeneným softvérom, prípadne testy konverzie dát, kedy sú dáta z inej aplikácie migrované do systému, ktorý je udržiavaný.
* Vyradenie aplikácie z prevádzky na konci jej životnosti. Pri vyradení aplikácie alebo systému môže byť vhodné vykonať testovanie archivácie dát, a to najmä pre také dáta, pre ktoré sú požadované dlhé lehoty archivácie. Pre prípad, kedy by bolo počas doby archivácie nutné načítať niektoré archivované dáta, je možné otestovať aj procesy obnovenia a načítania (po archivácii).*
