## Testování v kontextu životního cyklu vývoje softwaru {#testing-in-context-of-software-development-life-cycle}
Model životního cyklu vývoje softwaru (SDLC) je zobecněný proces vývoje softwaru. Určuje, jak spolu logicky
i chronologicky souvisí různé fáze vývoje a typy činností prováděných v rámci tohoto procesu. Mezi kategorie modelů SDLC patří sekvenční modely vývoje (např. vodopádový model, V-model), iterativní modely vývoje (např. spirálový model, prototypování) a inkrementální vývojové modely (např. Rational Unified Process).
Některé činnosti v rámci procesů vývoje softwaru lze také popsat podrobnějšími metodami vývoje softwaru
a agilními postupy. Mezi takové metody patří vývoj řízený akceptačními testy (ATDD – acceptance test driven development), vývoj řízený chováním (BDD – behavior driven development), návrh řízený doménou (DDD – domain driven development), extrémní programování (XP – extreme programming), vývoj řízený užitnými vlastnostmi (FDD – feature driven development), Kanban, Lean IT, Scrum a vývoj řízený testováním (TDD – test driven development).

### Vliv životního cyklu vývoje softwaru na testování
Aby bylo testování úspěšné, musí být přizpůsobeno SDLC. Volba SDLC má dopad na:
* rozsah a načasování testovacích činností (např. úrovně testování a typy testů),
* úroveň detailu testovací dokumentace,
* volba technik testování a přístupu k testování,
* rozsah automatizace testů,
* role a zodpovědnosti testerů.
V sekvenčních modelech vývoje se testeři v počátečních fázích obvykle účastní revizí požadavků, testovací analýzy a návrhu testů. Jelikož je spustitelný kód obvykle vytvořen až v pozdějších fázích SDLC, nelze v těchto počátečních fázích používat techniky dynamického testování.
V některých iterativních a inkrementálních vývojových modelech se předpokládá, že výsledkem každé iterace je funkční prototyp nebo přírůstek produktu. To znamená, že v každé iteraci může být provedeno statické
i dynamické testování, a to ve všech úrovních testování. Časté dodávání takových přírůstků vyžaduje rychlou zpětnou vazbu a rozsáhlé regresní testování.
Agilní vývoj softwaru (s využitím iterativních a inkrementálních modelů) předpokládá, že v průběhu projektu může dojít ke změně. Proto je v agilních projektech upřednostňována spíše stručnější dokumentace pracovních produktů, a naopak rozsáhlá automatizace testů, která usnadňuje regresní testování. Většina manuálních testů je často prováděna pomocí testovacích technik založených na zkušenostech (viz <#section:experience-based-testing-techniques>), u kterých není vyžadováno provedení rozsáhlé testovací analýzy a návrhu testů.

### Životní cyklus vývoje softwaru a osvědčené testovací postupy
Mezi osvědčené testovací postupy, nezávisle na zvoleném modelu SDLC, patří:
* Ke každé vývojové činnosti existuje odpovídající testovací činnost, takže všechny vývojové činnosti podléhají řízení kvality.
* Existují různé úrovně testování (viz <#section:testing-levels>) a každá má své specifické (a někdy i odlišné) cíle. Tím je testování přiměřeně detailní a zároveň nedochází k nadbytečnostem.
* Testovací analýza a návrh testů pro danou úroveň začíná během odpovídající vývojové fáze SDLC, takže je splněn princip včasného testování (viz <#section:testing-principles>)
* V okamžiku, kdy je k dispozici pracovní verze (draft) libovolného pracovního produktu, jsou do jeho revize zapojeni testeři, což (jako forma včasného testování a včasné detekce defektů) podporuje přístup shift-left (viz <#section:shift-left-approach>).

## Vývoj softwaru řízený testováním {#test-driven-software-development}

TDD, ATDD a BDD jsou podobné přístupy k vývoji, kdy jsou testy definovány jako prostředek pro řízení vývoje. Každý z těchto přístupů je aplikací principu včasného testování (viz <#section:testing-principles>) a uplatňuje přístup shift-left (viz <#section:shift-left-approach>) – testy jsou definovány před tvorbou samotného kódu. Všechny podporují iterativní model vývoje a jsou charakterizovány následovně:

**Vývoj řízený testy (TDD)**

* Psaní kódu je řízeno pomocí testovacích případů (místo rozsáhlého návrhu softwaru) (@beck2003test).
* Nejprve jsou sepsány testy a až následně kód a to tak, aby těmto testům vyhovoval. Následně mohou (ale nemusí) být testy a kód refaktorovány.

**Vývoj řízený akceptačními testy (ATDD)**

* Odvozuje testy z akceptačních kritérií jako součást procesu návrhu systému (@gartner2012atdd).
* Daná část aplikace je vytvořena tak, aby vyhovovala testům napsaným před samotným vývojem.

Více informací o ATDD lze nalézt v [kapitola 4.5.3](#section:{#atdd}).

**Vývoj řízený chováním (BDD)**

* Požadované chování aplikace je popsáno testovacími případy napsanými v jednoduché formě přirozeného jazyka srozumitelného pro zúčastněné strany. Obvykle je využit formát Given/When/Then (Vstup/Podmínka/Akce) (@chelimsky2010rspec).
* Testovací případy jsou následně automaticky přeloženy do spustitelných testů.

Pro všechny výše uvedené přístupy mohou být testy automatizovány (ale nemusí) s cílem podpořit kvalitu při budoucích úpravách nebo refaktoringu.

### DevOps a testování {#devops-and-testing}

DevOps je přístup k vývoji softwaru, který je postaven na synergii mezi odděleními vývoje (včetně testování) a provozu s cílem dosahovat definovaných společných cílů. DevOps vyžaduje změnu kultury v rámci organizace tak, aby se mezi těmito dvěma organizačními jednotkami překlenuly mezery a zároveň se k nim přistupovalo se stejnou důležitostí. DevOps podporuje autonomii týmu, rychlou zpětnou vazbu, integrované sady nástrojů a užití technických přístupů jako je průběžná integrace (CI – continuous integration) a průběžné nasazovaní (CD – continuous deployment). To umožňuje týmům vytvářet, testovat a vydávat kvalitní kód rychleji prostřednictvím definované DevOps pipeline (@kim2016devops).

Z pohledu testování má DevOps tyto výhody:

* Poskytuje rychlou zpětnou vazbu o kvalitě (nového) kódu a o nepříznivém vlivu na dosavadní funkčnost systému/komponenty.
* Díky CI podporuje přístup shift-left při testování (viz <#section:shift-left-approach>) tím, že motivuje vývojáře k psaní kvalitního kódu podporovaného testováním komponent a statickou analýzou.
* Propaguje automatizované zpracování (např. CI/CD), které usnadňuje vytváření stabilních testovacích prostředí.
* Zvyšuje důraz na nefunkcionální charakteristiky kvality (např. výkon nebo spolehlivost).
* Automatizací prostřednictvím pipeline snižuje potřebu opakovaného manuálního testování.
* Minimalizuje riziko regrese díky rozsahu a míře automatizovaných regresních testů.

DevOps má také některá rizika a nevýhody:

* Musí být definovány a zavedeny DevOps pipeline.
* Musí být zavedeny a udržovány nástroje CI/CD.
* Automatizované testy vyžadují dodatečné investice a může být obtížné je vytvořit a udržovat.
* Přestože DevOps předpokládá vyšší rozsah automatizovaného testování, nelze opomíjet ani manuální testování, a to zejména z pohledu koncového uživatele.

###  Přístup shift-left {#shift-left-approach}
Princip včasného testování (viz <#section:testing-principles>) je někdy označován jako shift-left (posun doleva ve smyslu časové osy), kdy je testování prováděno v dřívějších fázích SDLC. Shift-left doporučuje začít s testováním dříve (např. nečekat na implementaci kódu nebo na integraci komponent), ale neznamená to, že by testování v pozdějších fázích mělo být zanedbáváno.

Existují některé osvědčené postupy, na kterých lze demonstrovat aplikaci tohoto přístupu:

* Revidování specifikací z pohledu testování, které nachází potenciální defekty jako jsou nejednoznačnosti, neúplnosti a nesrovnalosti.
* Psaní testovacích případů před napsáním kódu a spuštění kódu v sadě testovacího vybavení (test harness) během vývoje kódu.
* Používání CI anebo lépe CD, protože přichází s rychlou zpětnou vazbou a automatizovanými testy komponent, které jsou společně s kódem uloženy do repozitáře.
* Spouštění statické analýzy zdrojového kódu před dynamickým testováním nebo jako součást daného automatizovaného procesu.

Provádění nefunkcionálních testů hned v úrovni testování komponent (pokud je to možné). Jedná se také o formu shift-left principu, jelikož obvykle jsou tyto typy testů prováděny v pozdějších fázích SDLC, kdy je k dispozici kompletní systém a odpovídající testovací prostředí.

Zavedení shift-left přístupu může v počátečních fázích znamenat riziko navýšení nákladů ve formě víceprací nebo nutnosti proškolení týmu, ale v pozdějších fázích naopak šetří pracnost a/nebo náklady.

Je důležité, aby byly zúčastněné strany přesvědčeny o užitečnosti tohoto konceptu a podporovaly jej.

### Retrospektivy a zlepšování procesů {#retrospectives-and-process-improvement}

Retrospektivy (známé také jako po-projektové schůzky nebo projektové retrospektivy) se často konají na konci projektu nebo iterace, při dosažení milníku nebo dle potřeby (ad-hoc). Načasování a organizace retrospektiv závisí na konkrétním modelu SDLC. Účastníci těchto schůzek (nejen testeři, ale také např. vývojáři, architekti, vlastníci produktů, byznysoví analytici) obvykle probírají:

* Co bylo úspěšné a mělo by být zachováno?
* Co se nepovedlo a dalo by se zlepšit?
* Jak implementovat návrhy na zlepšení a zajistit v budoucnu trvalou úspěšnost?

Výstupy z retrospektiv by měly být zaznamenány, obvykle jsou součástí souhrnného reportu z testování (viz <#section:purpose-content-target-of-test-reports>). Retrospektivy jsou z hlediska nastavení procesu kontinuálního zlepšování kritické a je důležité, aby byla všechna doporučená opatření sledována (a dodržována).

Mezi typické výhody retrospektiv z pohledu testování patří:

* Zvyšování efektivity / účinnosti testů (např. z důvodu implementace návrhů na zlepšení procesů).
* Zvyšování kvality testwaru (např. společnou revizí testovacích procesů).
* Stmelování týmu a vzájemné učení (např. jako výsledek možnosti hlásit problémy a navrhovat zlepšení).
* Zlepšování kvality testovací báze (např. vyřešením nedostatků v rozsahu a kvalitě požadavků).
* Zlepšování spolupráce mezi vývojem a testováním (např. díky pravidelným revizím a optimalizaci vzájemné spolupráce).

## Úrovně testování a typy testů

Úrovně testování jsou skupiny testovacích činností, které jsou organizovány a řízeny společně. Každá úroveň testování je instancí procesu testování tvořenou činnostmi prováděnými ve vztahu k softwaru v dané fázi vývoje, od jednotlivých komponent až po celé systémy, nebo případně i systémy systémů.

Úrovně testování souvisí s dalšími činnostmi v rámci životního cyklu vývoje softwaru. V sekvenčních modelech SDLC jsou úrovně testování často definovány tak, že výstupní kritéria jedné úrovně jsou součástí vstupních kritérií další úrovně. To ale nemusí platit v některých iterativních modelech, kde se úrovně testování mohou v čase překrývat a vývojové činnosti mohou překlenout více úrovní testování.

Typy testů jsou skupiny testovacích činností související se specifickými kvalitativními charakteristikami, kdy většinu těchto činností lze provádět v libovolné úrovni testování.

### Úrovně testování {#testing-levels}

V těchto učebních osnovách je popsáno následujících pět úrovní testování:

* **Testování komponent** (označované také jako jednotkové testování, unit testing) se zaměřuje na testování izolovaných komponent. Pro jejich provádění je často potřebný speciální software, např. různé sady testovacího vybavení (test harness) nebo frameworky pro jednotkové testování. Testování komponent obvykle provádějí vývojáři ve svých vývojových prostředích.
* **Integrační testování komponent** (označované také jako integrační testování jednotek) se zaměřuje na testování rozhraní a interakcí mezi komponentami. Toto testování je silně závislé na zvolené integrační strategii (např. zdola-nahoru, shora-dolů nebo tzv. velký třesk).
* **Systémové testování** se zaměřuje na celkové chování a schopnosti celého systému nebo produktu, často včetně funkcionálního testování komplexních (end-to-end) úkolů a nefunkcionálního testování kvalitativních charakteristik. Některé z nich (např. použitelnost) je vhodnější testovat na úplném systému ve vhodném testovacím prostředí. Kromě jiného lze využívat simulace subsystémů. Systémové testování vychází ze specifikací systému a může být prováděno nezávislým testovacím týmem.
* **Systémové integrační testování** se zaměřuje na testování rozhraní mezi testovaným systémem a dalšími systémy nebo externími službami. Pro systémové integrační testování je potřebné mít vhodné testovací prostředí, pokud možno podobné provoznímu.
* **Akceptační testování** se zaměřuje na prokázání připravenosti systému k nasazení do produkčního prostředí a validuje, že systém splňuje byznysové potřeby uživatele. V ideálním případě by akceptační testování měli provádět koncoví uživatelé. Nejčastější formy akceptačního testování jsou: uživatelské akceptační testování (UAT), provozní akceptační testování, smluvní a regulatorní akceptační testování, alfa testování a beta testování.

Aby nedocházelo k překrývání činností při testování v jednotlivých úrovních, dílčí úrovně testování se odlišují specifickou definicí různých atributů. Mezi nejdůležitější atributy patří:

* testovaný objekt,
* cíle testování,
* testovací báze,
* defekty a selhání,
* přístup a zodpovědnosti.

### Typy testů

Existuje mnoho typů testů, které lze na projektech použít. Tyto učební osnovy se zabývají čtyřmi typy testů.

**Funkcionální testování** ověřuje funkcionality, které by komponenta nebo systém měl vykonávat. Funkcionality představují to, „co" by systém měl dělat. Hlavním cílem funkcionálního testování je kontrola funkcionální úplnosti, funkcionální správnosti a funkcionální vhodnosti.

**Nefunkcionální testování** vyhodnocuje nefunkcionální charakteristiky komponenty nebo systému a dává tak odpověď na otázku „jak dobře se systém chová". Seznam nefunkcionálních charakteristik kvality softwaru lze nalézt v normě ISO/IEC 25010 (@ISO25010):

* výkonnostní efektivita,
* kompatibilita,
* použitelnost,
* bezporuchovost (spolehlivost),
* bezpečnost,
* udržovatelnost,
* přenositelnost.

Mnoho nefunkcionálních testů je odvozeno z funkcionálních. Oba typy používají stejné testovací případy, ale nefunkcionální kontrolují, zda je při dané funkcionalitě splněno také nějaké nefunkcionální omezení (např. že je vše vykonáno v určeném čase nebo zda může být daná funkčnost přenesena na novou platformu). Pozdní odhalení nefunkcionálního defektu může představovat vážnou hrozbu pro úspěch projektu.

Někdy je vhodné, aby nefunkcionální testování začalo už v rané fázi SDLC (např. jako součást revizí a při testování komponent nebo systémovém testování) a někdy je nutné využít velmi specifické testovací prostředí jako je například laboratoř pro testování použitelnosti.

**Testování černé skříňky** (viz <#section:black-box-testing-techniques>) je založeno na specifikaci a odvozuje testy z dokumentace testovaného objektu (tedy ne z chování samotného objektu). Hlavním cílem testování černé skříňky je kontrola chování systému podle jeho specifikace.

**Testování bílé skříňky** (viz <#section:white-box-testing-techniques>) je založeno na struktuře a odvozuje testy z implementace systému nebo z jeho vnitřní struktury, což je např. kód, architektura, pracovní toky (workflows) nebo datové toky. Hlavním cílem testování bílé skříňky je dosahovat dostatečného pokrytí testované struktury (např. kódu).

Všechny čtyři výše uvedené typy testů lze aplikovat ve všech úrovních testů, i když konkrétní implementace bude v každé úrovni odlišná. K odvození testovacích podmínek a testovacích případů pro všechny uvedené typy testů lze použít různé techniky testování.

### Konfirmační a regresní testování {#confirmation-and-regression-testing}

Pokud se v komponentě nebo systému provádějí změny, je obvykle jejich cílem rozšíření (přidáním nové funkcionality) nebo oprava (odstraněním defektu). Následné testování by poté mělo zahrnovat jak konfirmační testování, tak regresní testování.

**Konfirmační testování** ověřuje, zda byl původní defekt úspěšně opraven. V závislosti na riziku lze otestovat opravenou verzi softwaru několika různými způsoby, např.:

* Provedením všech testovacích případů, které dříve selhaly kvůli defektu.
* Přidáním nových testů s cílem pokrývat všechny změny potřebné k opravě defektu.

V případech, kdy je na opravu defektu málo času nebo finančních prostředků, může být konfirmační testování omezeno na pouhé provedení kroků, které by měly reprodukovat původní selhání způsobené defektem a zkontrolovat, zda k selhání nedochází.

**Regresní testování** ověřuje, zda nedošlo k žádným nežádoucím dopadům po realizovaných změnách, včetně oprav, které již byly potvrzeny konfirmačním testováním. Tyto nežádoucí dopady by mohly ovlivnit jak komponentu, kde byla změna provedena, tak i jiné komponenty ve stejném systému nebo dokonce jiné propojené systémy. Regresní testování nemusí být omezeno na samotný testovaný objekt, ale může také souviset s prostředím. Doporučuje se proto před testováním nejprve provést tzv. analýzu dopadu s cílem optimalizovat rozsah regresního testování. Analýza dopadu ukazuje, které části softwaru by mohly být ovlivněny.

Sady regresních testů se spouštějí mnohokrát a obvykle se jejich počet zvyšuje s každou novou iterací nebo vydáním, proto jsou vhodným kandidátem na automatizaci testování. Automatizace těchto testů by měla začít už v raných fázích projektu (viz <#section:testTools>). Automatizované regresní testy je vhodné zařadit do CI pipeline (např. DevOps pipeline, viz <#section:devops-and-testing>). Regresní testy mohou být dle situace vykonávány v různých úrovních testování.

Konfirmační a/nebo regresní testování testovaného objektu je nutno použít v těch úrovních testování, kde došlo k opravám defektů a/nebo jsou v nich provedeny změny.

## Testování údržby

Existují různé druhy údržby s různými cíli, např oprava, adaptace na změnu prostředí, zlepšení výkonu nebo zlepšení udržovatelnosti (viz norma ISO/IEC 14764 (@ISO14764)). Údržba může být jak plánovaná, tak neplánovaná (hotfix). Před provedením změny lze taktéž provést analýzu dopadu, která pomůže při rozhodování, zda by změna měla být provedena, a to na základě potenciálních důsledků v jiných oblastech systému. Testování změn systému, který je již v produkci zahrnuje jak vyhodnocení úspěšnosti implementace změny, tak kontrolu možné regrese v nezměněných částech systému (což je obvykle většina systému).

Rozsah testování údržby závisí na těchto faktorech:

* míra rizika změny,
* velikost stávajícího systému,
* rozsah změny.

Spouštěče (aktivační události) údržby a testování údržby lze rozdělit takto:

* Úpravy jako jsou plánovaná vylepšení (např. v celém vydání), opravné změny nebo hotfixy.
* Aktualizace nebo migrace provozního prostředí (například z jedné platformy na jinou), kdy je nutné provést testy spojené s novým prostředím a změněným softwarem, případně testy konverze dat, kdy jsou data z jiné aplikace migrována do systému, který je udržován.
* Vyřazení aplikace z provozu na konci její životnosti. Při vyřazení aplikace nebo systému může být vhodné provést testování archivace dat, a to zejména pro taková data, pro která jsou požadována dlouhé lhůty archivace. Pro případ, kdy by bylo během doby archivace nutné načíst některá archivovaná data, je možné otestovat také procesy obnovení a načtení (po archivaci).
