## Plánování testování {#planning-testing}

### Účel a obsah plánu testování

Plán testování popisuje cíle, zdroje a procesy testování v rámci projektu. Plán testování:

* dokumentuje způsob dosažení cílů testování a harmonogram testování,
* pomáhá zajistit, aby prováděné testovací činnosti splňovaly stanovená kritéria,
* slouží jako způsob komunikace se členy týmu a dalšími zúčastněnými stranami,
* prokazuje, že testování je v souladu se stávající politikou a strategií testování (případně vysvětluje, proč se od nich testování odchyluje).

Plánování testování je průvodcem testerů ve smyslu rozvahy nad budoucími výzvami souvisejícími s riziky, harmonogramy, lidmi, nástroji, náklady, pracností atd. Proces přípravy plánu testování je užitečným nástrojem pro analýzu pracnosti potřebné k dosažení cílů testování stanovených v rámci projektu.

Typický obsah plánu testování obsahuje:

* kontext testování (např. rozsah, cíle testování, omezení, testovací báze),
* předpoklady a omezení testovacího projektu,
* definici zúčastněných stran (např. role, odpovědnosti, relevantnost pro testování, potřeby náboru a školení),
* plán komunikace (např. rozdílné způsoby a četnost komunikace, šablony dokumentace),
* registr rizik (např. produktová a projektová rizika),
* přístup k testování (např. úrovně testů, typy testů, techniky testování, výstupy z testování, vstupní a výstupní kritéria, nezávislost testování, požadované metriky, požadavky na testovací data, požadavky na testovací prostředí, odchylky od politiky a strategie testování),
* rozpočet a harmonogram.

Další podrobnosti o plánu testování a jeho obsahu lze nalézt v normě ČSN ISO/IEC/IEEE 29119-3 [@ISO29119-3].

### Přínos testerů při plánování iterací a vydání

V iterativních SDLC se obvykle vyskytují dva druhy plánování: plánování vydání a plánování iterace.

**Plánování vydání** vyhlíží vpřed směrem k vydání produktu, definuje a upravuje produktový backlog a může zahrnovat rozpracování větších uživatelských scénářů do sady menších. Zároveň slouží jako základ pro definici přístupu k testování a plánu testování napříč všemi iteracemi. Testeři zapojeni do plánování vydání se podílí na specifikaci testovatelných uživatelských scénářů a akceptačních kritérií (viz <#section:collaborative-testing-approaches>), podílí se na analýzách projektových a produktových rizik (viz <#section:risk-management>), provádí odhady pracnosti potřebné k testování uživatelských scénářů (viz <#section:estimation-techniques>), stanovují přístup k testování a plánují testování související s vydáním.

**Plánování iterace** vyhlíží směrem ke konci jedné iterace a pracuje s backlogem iterace. Testeři zapojení do plánování iterací se podílí na podrobné analýze rizik uživatelských scénářů, stanovují jejich testovatelnost, podílí se na jejich rozkladu do úkolů (zejména pro testovací činnosti), provádí odhady pracnosti testování pro všechny testovací činnosti a přispívají k identifikaci a zpřesňování funkcionálních a nefunkcionálních aspektů testovaného objektu.

### Vstupní kritéria a výstupní kritéria {#entry-and-exit-criteria}

Vstupní kritéria určují předpoklady pro realizaci dané činnosti. Pokud nejsou splněna vstupní kritéria, bude provedení testovací činnosti pravděpodobně obtížnější, časově náročnější, nákladnější a více rizikové. Mezi typická vstupní kritéria patří dostupnost zdrojů (např. lidé, nástroje, prostředí, testovací data, rozpočet, čas), dostupnost testwaru (např. testovací báze, testovatelné požadavky, uživatelské scénáře, testovací případy) a počáteční úroveň kvality testovaného objektu (např. úspěšnost všech smoke testů).

Výstupní kritéria určují podmínky, kterých musí být dosaženo, aby bylo možné prohlásit činnost za dokončenou. Mezi typická výstupní kritéria patří míra důkladnosti (např. dosažená úroveň pokrytí, počet nevyřešených defektů, hustota defektů, počet neúspěšných testovacích případů) a kritéria dokončení (např. provedení plánovaných testů, provedení statického testování, zaznamenání všech zjištěných defektů, automatizace všech regresních testů).

Za platná výstupní kritéria lze také považovat vyčerpání času nebo finančních prostředků. Pokud v takové situaci (tj. kdy nejsou ostatní výstupní kritéria naplněna) zúčastněné strany přezkoumají a přijmou rizika spojená s nasazením produktu do produkce bez dalších testů, lze akceptovat ukončení testování.

V agilním vývoji softwaru se výstupní kritéria často nazývají definice hotového (ang. definition of done) a určují projektovou objektivní metriku pro položky připravené k vydání. Vstupní kritéria, která musí uživatelský scénář splňovat, aby mohly být zahájeny vývojové a/nebo testovací činnosti, se nazývají definice připravenosti.

Vstupní a výstupní kritéria by měla být definována pro každou úroveň testů a mohou se lišit v závislosti na stanovených cílech testování.

### Techniky pro odhadování {#estimation-techniques}

Odhad pracnosti testování reprezentuje očekávané množství práce, které bude zapotřebí k dosažení cílů testování v projektu. Je důležité zúčastněným stranám objasnit, že odhad vychází z momentálních předpokladů a vždy může být zatížen chybou odhadu, přičemž platí, že odhad pro malé úkoly je obvykle přesnější než pro velké úkoly. Proto je při odhadování vhodné rozložit rozsáhlý úkol na sadu menších a ty následně odhadnout. Tyto učební osnovy popisují čtyři techniky odhadování.

**Odhad na základě poměrů**. Při této technice založené na metrikách se shromažďují údaje z předchozích projektů v rámci organizace, což umožňuje odvodit „standardizované" poměrové metriky (vzorce) pro podobné projekty. Takové metriky odvozené z vlastních projektů organizace (např. převzaté z historických dat) jsou obecně nejlepším zdrojem, který lze v procesu odhadování použít a lze je použít k odhadu pracnosti testování nového projektu. Pokud byla například v předchozím projektu pracnost vývoje a pracnost testování v poměru 3:2 a v současném projektu se očekává, že pracnost vývoje bude činit 600 člověko-dnů, lze pracnost testování odhadnout na 400 člověko-dnů.

**Extrapolace**. Při této technice založené na metrikách se v aktuálním projektu provádí co nejdříve měření s cílem shromažďovat data. S dostatečným počtem pozorování (dat) lze potřebnou zbývající pracnost aproximovat extrapolací těchto dat (obvykle použitím matematického modelu). Tato metoda je velmi vhodná pro iterativní modely SDLC, protože tým může například extrapolovat pracnost testování v nadcházející iteraci jako průměrnou pracnost z posledních tří iterací.

**Wideband Delphi**. Při této iterativní technice založené na expertech provádějí experti odhady založené na zkušenostech. Každý takový expert (odborník) samostatně odhadne pracnost. Výsledky odhadů jsou shromážděny a pokud se objeví odchylky mimo rozsah dohodnutých hranic, diskutují experti o svých aktuálních odhadech. Každý je poté požádán, aby na základě této zpětné vazby provedl nový odhad, a to opět samostatně. Tento proces se opakuje, dokud není dosaženo shody. Variantou Wideband Delphi, která se běžně používá při agilním vývoji softwaru je tzv. plánovací poker. Při něm se odhady obvykle provádějí pomocí karet s čísly, která představují rozsah pracnosti.

**Tříbodový odhad**. Při této technice založené na expertech provádějí experti tři odhady: nejoptimističtější odhad (a), nejpravděpodobnější odhad (m) a nejpesimističtější odhad (b). Výsledný odhad (E) je jejich vážený aritmetický průměr. V nejpoužívanější verzi této techniky se odhad vypočítá jako E = (a + 4 \* m + b) / 6. Výhodou této techniky je, že umožňuje expertům vypočítat chybu měření, obvykle ve formě směrodatné odchylky: SD = (b - a) / 6. Pokud jsou např. odhady (v člověko-hodinách): a = 6, m = 9 a b = 18, pak výsledný odhad je 10 ± 2 člověko-hodin (tj. mezi 8 a 12 člověko-hodinami), protože E = (6 + 4 \* 9 + 18) / 6 = 10 a SD = (18 - 6) / 6 = 2.

Více informací o těchto a mnoha dalších technikách odhadování pracnosti testování lze nalézt v [@kan2003metrics], [@vroon2013tmap] a [@westfall2016certified].

### Prioritizace testovacích případů {#test-cases-prioritization}

Jakmile jsou testovací případy a testovací procedury vytvořeny a sestaveny do testovacích sad, lze tyto testovací sady řadit do harmonogramu provádění definující pořadí spouštění.

Při stanovení priorit testovacích případů lze zohlednit různé faktory. Nejčastěji používané strategie prioritizace testovacích případů jsou následující:

* **Prioritizace na základě rizik** , kdy pořadí provádění testů vychází z výsledků analýzy rizik (viz <#section:product-risks-analysis>). Nejprve se provedou testovací případy pokrývající nejdůležitější rizika.
* **Prioritizace na základě pokrytí** , kdy je pořadí provádění testů založeno na určitém pokrytí (např. pokrytí příkazů). Testovací případy dosahující nejvyššího pokrytí jsou provedeny jako první. V jiné variantě (nazývané prioritizace dodatečného pokrytí) se nejprve provede testovací případ s nejvyšším pokrytím. Každý následující testovací případ je ten, který dosáhne nejvyššího dodatečného pokrytí.
* **Prioritizace na základě požadavků** , kdy pořadí provádění testů vychází z priorit požadavků trasovatelných zpět k odpovídajícím testovacím případům. Priority požadavků definují zúčastněné strany, testovací případy související s nejdůležitějšími požadavky jsou prováděny jako první.

V ideálním případě by měly být testovací případy seřazeny k provádění na základě úrovně jejich priority, například pomocí jedné z výše uvedených strategií prioritizace. Tento postup však nemusí fungovat, pokud mezi testovacími případy nebo testovanými užitnými vlastnostmi existují závislosti. Pokud testovací případ s vyšší prioritou závisí na testovacím případu s nižší prioritou, musí být nejdříve proveden testovací případ s nižší prioritou.

Pořadí provádění testů musí také zohledňovat dostupnost zdrojů, např. požadovaných testovacích nástrojů, testovacího prostředí nebo osob, které mohou být k dispozici pouze po určitou dobu.

### Testovací pyramida

Testovací pyramida je model, který ukazuje, že různé testy mohou mít různou granularitu. Představuje pomůcku pro automatizaci testů, protože týmu názorně znázorňuje možnosti rozložení pracnosti v různých úrovních automatizace testování, zároveň ukazuje, že různé úrovně mají různé cíle.

Vrstvy pyramidy představují skupiny testů. Čím vyšší vrstva, tím nižší granularita testu, menší izolace testu a delší doba provádění testu. Testy ve spodní vrstvě jsou malé, izolované, rychlé a ověřují malou část funkcionality, takže k dosažení rozumného pokrytí je jich obvykle potřeba velké množství. Horní vrstva představuje komplexní vysokoúrovňové E2E (end-to-end) testy. Ty jsou obecně pomalejší než testy z nižších vrstev a obvykle ověřují velkou část funkcionality, takže pro dosažení rozumného pokrytí je jich obvykle zapotřebí jen několik. Počet a pojmenování jednotlivých vrstev se může lišit, například původní model testovací pyramidy [@cohn2010succeeding] definuje tři vrstvy (testy komponent, testy služeb a testy uživatelského rozhraní). Jiné modely definují jednotkové testy (testy komponent), integrační testy komponent a end-to-end testy, obecně lze použít i jiné úrovně testování (viz <#section:testing-levels>).

### Testovací kvadranty

Testovací kvadranty definované Brianem Marickem [@marick2003survey], [@crispin2009agile], dávají do souvislosti úrovně testování s příslušnými typy testů, činnostmi, technikami testování a pracovními produkty v agilním vývoji softwaru. Model je pomůckou pro management testování při vizualizaci těchto vztahů s cílem zajišťovat, že všechny vhodné typy a úrovně testů jsou zahrnuty do SDLC, a pro pochopení toho, že některé typy testů jsou pro určité úrovně testů relevantnější než jiné. Poskytuje způsob, jak od sebe rozlišit a popsat typy testů všem zúčastněným stranám včetně vývojářů, testerů a zástupců byznysu.

V tomto modelu osa Y rozlišuje testy zaměřené na byznys nebo na technologii a osa X pak testy podporující tým (tj. ty, které pomáhají usměrňovat vývojové aktivity) nebo revidující produkt (tj. takové, které pomáhají měřit jeho chování proti očekáváním). Kombinace těchto dvou pohledů (os) určuje čtyři kvadranty:

* **Kvadrant Q1 (zaměřené na technologii, podporující tým)**. Tento kvadrant obsahuje testy komponent a integrační testy komponent. Tyto testy by měly být automatizovány a zahrnuty do procesu CI.
* **Kvadrant Q2 (zaměřené na byznys, podporující tým)**. Tento kvadrant obsahuje funkcionální testy, příklady, testy uživatelských scénářů, UX prototypy, testování rozhraní (API) a simulace. Tyto testy ověřují akceptační kritéria a mohou být manuální i automatizované.
* **Kvadrant Q3 (zaměřené na byznys, revidující produkt)**. Tento kvadrant obsahuje průzkumné testování, testování použitelnosti a uživatelské akceptační testování. Tyto testy jsou uživatelsky orientované a často manuální.
* **Kvadrant Q4 (zaměřené na technologii, revidující produkt)**. Tento kvadrant obsahuje smoke testy a nefunkcionální testy (kromě testů použitelnosti). Tyto testy jsou často automatizované.

## Management rizik {#risk-management}

Organizace čelí mnoha interním a externím faktorům přinášejícím nejistotu v tom, zda a kdy dosáhnou svých cílů [@ISO31000]. Management rizik jim umožňuje zvýšit pravděpodobnost dosažení těchto cílů, zlepšit kvalitu jejich produktů a zvýšit důvěru zúčastněných stran.

Hlavními činnostmi v oblasti managementu rizik jsou:

* **analýza rizik** (obsahuje identifikaci a ohodnocení rizik, viz <#section:product-risks-analysis>),
* **řízení rizik** (obsahuje zmírňování a monitoring rizik, viz <#section:product-risk-management>).

Přístup k testování, při kterém jsou testovací činnosti vybírány, prioritizovány a řízeny na základě analýzy rizik společně s řízením rizik, se nazývá testování založené na rizicích.

### Definice rizika a jeho atributy

Riziko je možná událost, nebezpečí, hrozba nebo situace, jejíž výskyt má nepříznivý vliv. Riziko lze charakterizovat dvěma faktory:

* pravděpodobnost rizika – pravděpodobnost vzniku rizika vyjádřená v procentech nebo v intervalu \<0;1\>,
* dopad rizika (škoda) – důsledky výskytu takové události.

Tyto dva faktory vyjadřují úroveň rizika, která je jeho mírou (metrikou). Čím vyšší je úroveň rizika, tím důležitější je jeho ošetření.

### Projektová a produktová rizika

Při testování softwaru se obecně zabýváme dvěma typy rizik – projektová rizika a produktová rizika.

**Projektová rizika** se týkají managementu a řízení projektu. Mezi projektová rizika patří:

* organizační problémy (např. zpoždění při dodávání pracovních produktů, nepřesné odhady, snižování nákladů),
* problémy s lidmi (např. nedostatečné dovednosti, konflikty, komunikační problémy, nedostatek zaměstnanců),
* technické problémy (např. narůstající rozsah, špatná podpora nástrojů),
* problémy s dodavateli (např. selhání dodávky třetí strany, úpadek dodavatele).

Projektová rizika mohou mít dopad na harmonogram, rozpočet nebo rozsah projektu, což ovlivňuje schopnost projektu dosáhnout svých cílů.

**Produktová rizika** souvisejí s kvalitativními charakteristikami produktu (např. popsanými v modelu kvality [@ISO25010]). Mezi příklady produktových rizik patří:

* chybějící nebo nesprávná funkcionalita,
* nesprávné výpočty,
* chyby při běhu (runtime errors),
* špatná architektura,
* neefektivní algoritmy,
* nedostatečná doba odezvy,
* špatná uživatelská zkušenost,
* bezpečnostní zranitelnosti.

Produktová rizika mohou mít různé negativní důsledky, například:

* nespokojenost uživatelů,
* ztráta příjmů, důvěry, pověsti,
* škody způsobené třetím stranám,
* vysoké náklady na údržbu,
* přetížení helpdesku,
* trestněprávní postihy,
* fyzické poškození, zranění, v extrémních případech smrt.

### Analýza produktových rizik {#product-risks-analysis}

Z hlediska testování je cílem analýzy produktových rizik poskytnout povědomí o produktových rizicích s cílem nasměrovat pracnost při testování tak, aby došlo k minimalizaci jejich reziduálních úrovní. V ideálním případě začíná analýza produktových rizik v rané fázi SDLC. Analýza produktových rizik se skládá z identifikace a ohodnocení rizik.

**Identifikace rizik** spočívá ve vytvoření komplexního seznamu rizik. Zúčastněné strany mohou identifikovat rizika pomocí různých technik a nástrojů, např. brainstormingu, workshopů, rozhovorů nebo grafů příčin a následků.

**Ohodnocení rizik** zahrnuje kategorizaci identifikovaných rizik, určení jejich pravděpodobnosti, dopadu a úrovně, stanovení priorit a navržení způsobů jejich řešení. Kategorizace pomáhá při přiřazování zmírňujících opatření, protože obvykle lze rizika spadající do stejné kategorie zmírnit podobnými činnostmi.

Ohodnocení rizik může využívat kvantitativní nebo kvalitativní přístup (příp. obojí). Při kvantitativním přístupu se úroveň rizika vypočítá jako násobek pravděpodobnosti rizika a dopadu rizika. Při kvalitativním přístupu lze úroveň rizika stanovit pomocí matice rizik.

Analýza produktových rizik může ovlivnit důkladnost a rozsah testování. Její výsledky se používají k:

* určení rozsahu testování, které má být provedeno,
* určení konkrétních úrovní testování a návrhu typů testů, které mají být provedeny,
* určení technik testování, které mají být použity,
* určení pokrytí, kterého má být dosaženo,
* odhadu pracnosti testování vyžadovaného pro každý úkol,
* stanovení priorit testování s cílem co nejrychlejšího nalézání kritických defektů,
* určení, zda by mohly být ke snížení rizika použity i jiné činnosti (kromě testování).

### Řízení produktových rizik {#product-risk-management}

Řízení produktových rizik zahrnuje všechna opatření, která jsou přijata v reakci na identifikovaná a ohodnocená produktová rizika. Skládá se ze zmírňování rizik a monitoringu rizik.

Obsahem **zmírňování rizik** je zavedení opatření navržených při ohodnocení rizik s cílem snížit úroveň rizika. Jakmile je riziko analyzováno, je možné na něj reagovat několika způsoby, např. jeho zmírněním pomocí testování, přijetím, přenosem nebo záložním plánem [@veenendaal2012prisma]. Opatření, která lze přijmout ke zmírnění produktových rizik prostřednictvím testování, jsou následující:

* výběr testerů se zkušenostmi a dovednostmi vhodnými pro daný typ rizika,
* použití vhodné úrovně nezávislosti testování,
* provedení revizí a statické analýzy,
* použití vhodných technik testování a úrovní pokrytí,
* použití vhodných typů testů zaměřených na dotčené kvalitativní charakteristiky,
* provedení dynamického testování (včetně regresního testování).

Cílem **monitoringu rizik** je zajištování efektivity zmírňujících opatření, získ dalších informací pro zlepšení ohodnocení rizik a identifikace nově vznikajících rizik.

## Monitoring, řízení a dokončení testování {#monitoring-management-completion-of-testing}

**Monitoring testování** se zabývá shromažďováním informací o testování. Tyto informace se využívají k posouzení postupu prací při testování a ke stanovení, zda jsou naplněna výstupní kritéria testování nebo dokončeny testovací úkoly spojené s výstupními kritérii (jako např. splnění cílů pro pokrytí produktových rizik, požadavků nebo akceptačních kritérií).

**Řízení testování** využívá informace z monitoringu testování k tomu, aby byly (ve formě nařízení nebo směrnic) poskytnuty pokyny a nezbytná nápravná opatření k dosažení co nejúčinnějšího a nejefektivnějšího testování. Mezi příklady takových nařízení patří:

* přehodnocení priorit testů při výskytu identifikovaného rizika,
* přehodnocení, zda v důsledku změn (přepracování) splňuje daná položka testování vstupní nebo výstupní kritéria,
* úprava harmonogramu testování s ohledem na zpoždění v dodání testovacího prostředí,
* přidávání nových zdrojů tam, kde je potřeba a kdy je potřeba.

**Při dokončení testů** se shromažďují data z dokončených testovacích činností za účelem konsolidace zkušeností, testwaru a dalších důležitých informací. K činnostem souvisejícím s dokončením testování dochází v rámci projektových milníků jako je dokončení úrovně testování, dokončení iterace při agilním vývoji, dokončení (nebo zrušení) testovacího projektu, vydání softwarového systému nebo dokončení servisního vydání (maintenance release).

### Metriky používané v testování {#metrics-in-testing}

Testovací metriky jsou shromažďovány s cílem ukazovat postup proti plánovanému harmonogramu a rozpočtu, aktuální kvalitu testovaného objektu a efektivitu testovacích činností s ohledem na cíle projektu nebo iterace. Monitoring testování shromažďuje různé metriky pro podporu řízení a dokončení testování.

Mezi typické testovací metriky patří:

* metriky o postupu projektu (např. dokončení úkolu, využití zdrojů, pracnost testování),
* metriky o postupu testování (např. postup implementace testovacích případů, postup přípravy testovacích prostředí, počet spuštěných / nespuštěných testovacích případů, počet provedených testů, které prošly / selhaly, doba provedení testu),
* metriky týkající se kvality produktu (např. dostupnost, doba odezvy, střední doba mezi poruchami),
* metriky nad defekty (např. počet a priority zjištěných / opravených defektů, hustota defektů, procento zjištěných defektů – DDP, defect density percentage),
* metriky nad riziky (např. úroveň reziduálních rizik),
* metriky pokrytí (např. pokrytí požadavků, pokrytí kódu),
* metriky týkající se nákladů (např. náklady na testování, náklady na kvalitu v rámci organizace).

### Účel, obsah a cílové skupiny reportů z testování {#purpose-content-target-of-test-reports}

Cílem reportování testů je shrnutí a komunikace informací z testování při jeho průběhu a po něm. Reporty o postupu prací při testování podporují průběžné řízení testování. Musí poskytovat dostatek informací pro provedení změn v harmonogramu testování, zdrojích nebo plánu testování, pokud jsou tyto změny nutné z důvodu odchylky od plánu nebo změny okolností. Souhrnné reporty z testování shrnují určitou fázi testování (např. úroveň testování, testovací cyklus, iteraci) a mohou poskytnout informace pro následné testování.

Během monitoringu a řízení testování vytváří testovací tým reporty o postupu prací při testování s cílem poskytovat zúčastněným stranám informace. Reporty o postupu prací při testování jsou obvykle generovány pravidelně (např. denně, týdně atd.) a obsahují:

* testovací období,
* postup prací při testování (např. náskok nebo zpoždění oproti harmonogramu) včetně všech významných odchylek,
* překážky při testování a jejich řešení,
* testovací metriky (viz <#section:metrics-in-testing>),
* nová a změněná rizika během testovacího období,
* testování plánované pro následující období.

Souhrnný report z testování se připravuje v průběhu fáze dokončení testování, kdy je projekt, úroveň testování nebo typ testu ukončen, a kdy jsou (v ideálním případě) splněna stanovená výstupní kritéria. Tento report využívá informace z dílčích reportů o postupu prací při testování a doplňuje je o další data. Typické souhrnné reporty z testování obsahují:

* shrnutí testů,
* vyhodnocení testování a kvality produktu na základě původního plánu testování (tj. cílů testování a výstupních kritérií),
* odchylky od plánu testování (např. rozdíly oproti plánovanému harmonogramu, trvání a pracnosti),
* překážky při testování a jejich řešení,
* testovací metriky na základě reportů o postupu prací při testování,
* neošetřená rizika, nevyřešené defekty,
* získané zkušenosti (lessons learned), které jsou relevantní pro testování.

Různé cílové skupiny potřebují v těchto reportech různé informace a ovlivňují tím míru formálnosti a četnost reportování. Podávání zpráv o postupu prací při testování ostatním členům stejného týmu je většinou časté a neformální, zatímco podávání souhrnných reportů z testování z ukončeného projektu se provádí typicky pouze jednou, a to dle definované šablony.

V normě ČSN ISO/IEC/IEEE 29119-3 [@ISO29119-3] lze nalézt šablony a příklady reportů o postupu prací při testování (nazývané reporty o stavu testů) a souhrnných reportů z testování.

### Komunikování stavu testování

Optimální způsob komunikování stavu testování se liší v závislosti na potřebách managementu testování, strategiích testování v organizaci, regulatorních normách nebo v případě samoorganizujících se týmů (viz <#section:team-approach>) na samotném týmu. Mezi možnosti komunikace patří:

* verbální komunikace se členy týmu a dalšími zúčastněnými stranami,
* dashboardy (např. CI/CD dashboard, tabule s úkoly a grafy burn-down),
* elektronické komunikační kanály (např. e-mail, chat),
* online dokumentace,
* formální reporty z testování (viz <#section:purpose-content-target-of-test-reports>).

Lze použít jednu nebo kombinaci několika možností, formálnější komunikace může být vhodnější pro distribuované týmy, kde není přímá osobní komunikace vždy možná kvůli geografické vzdálenosti nebo časovým rozdílům. Obvykle se různé zúčastněné strany zajímají o jiný typ informací, proto by měla být komunikace odpovídajícím způsobem přizpůsobena.

## Konfigurační management {#configuration-management}

V oblasti testování je konfigurační management disciplína, která slouží pro identifikaci, řízení a sledování pracovních produktů. Konfiguračními položkami mohou být jakékoliv plány testování, strategie testování, testovací podmínky, testovací případy, skripty, výsledky testů, protokoly testů (test logs) a reporty z testování.

V případě komplexní konfigurační položky (např. testovací prostředí) lze v rámci konfiguračního managementu zaznamenávat dílčí položky, ze kterých se tato komplexní položka skládá, jejich vztahy a verze. V momentě, kdy je konfigurační položka schválena pro testování, stává se součástí tzv. baseline a lze ji měnit pouze prostřednictvím formálního procesu pro řízení změn.

V případě vytvoření nové baseline je úkolem konfiguračního managementu uchovávat záznamy o všech změněných konfiguračních položkách. Pokud je například nutné reprodukovat předchozí výsledky testů, je možné vrátit se k předchozí baseline.

Konfigurační management jako podpůrná disciplína testování zajišťuje následující:

* Všechny konfigurační položky včetně položek testování (jednotlivých částí testovaného objektu) jsou jednoznačně identifikovány, jejich verze jsou řízeny, všechny změny jsou evidovány a vztahy s jinými konfiguračními položkami jsou zaznamenány tak, aby bylo možné zajistit trasovatelnost v průběhu celého procesu testování.
* V dokumentaci testování vedou na všechny identifikované dokumenty a softwarové položky jednoznačné odkazy.

Průběžná integrace, průběžné dodávání, průběžné nasazování a s těmito procesy související testování jsou obvykle implementovány jako součást automatizované DevOps pipeline (viz <#section:devops-and-testing>), jejíž součástí je obvykle i automatizovaný konfigurační management.

## Management defektů {#defects-management}

Vzhledem k tomu, že jedním z hlavních cílů testování je nalezení defektů, je zavedení procesu managementu defektů nezbytné. Tento proces musí dodržovat všechny zúčastněné strany a zahrnuje minimálně definici pracovního postupu (workflow) pro zpracování jednotlivých anomálií od jejich odhalení až po jejich uzavření a pravidla pro jejich klasifikaci. Pracovní postup obvykle zahrnuje činnosti, jejichž cílem je zaznamenávat nahlášené anomálie, analyzovat je a klasifikovat, rozhodnout o vhodné reakci (typicky opravit nebo ponechat) a uzavření reportu o defektu. Anomálie mohou být hlášeny v kterékoli fázi SDLC a jejich forma často závisí na použitém SDLC.

Podobným způsobem je vhodné řešit i defekty zjištěné statickým testováním (zejména statickou analýzou).

Platí, že ne všechny nahlášené anomálie musí být nutně skutečné defekty (např. falešně pozitivní výsledky testů nebo změnové požadavky). Toto vyhodnocení je prováděno v rámci zpracování reportu o defektu. Reporty o defektu mají obvykle následující cíle:

* Poskytovat osobám odpovědným za zpracování a řešení hlášených defektů dostatečné informace pro vyřešení problému.
* Poskytovat způsob sledování kvality pracovního produktu.
* Navrhovat nápady pro zlepšování procesů vývoje a procesů testování.

Report o defektu zaznamenaný během dynamického testování obvykle obsahuje:

* jedinečný identifikátor,
* název obsahující krátké shrnutí reportované anomálie,
* datum zjištění anomálie, reportující organizace a autor (včetně role autora),
* identifikaci testovaného objektu a testovacího prostředí,
* kontext defektu (např. provedený testovací případ, provedená testovací činnost, fáze SDLC a další relevantní informace jako např. použitá technika testování, použitý kontrolní seznam nebo použitá testovací data),
* popis selhání umožňující reprodukci a vyřešení včetně kroků, které anomálii vyvolaly, všech relevantních protokolů testů (test logs), záloh databází, snímků obrazovky nebo videozáznamů,
* očekávané a skutečné výsledky,
* závažnost defektu (míru dopadu) na zájmy zúčastněných stran nebo na požadavky,
* naléhavost / prioritu opravy,
* stav defektu (např. otevřený, odložený, duplicitní, čekající na opravu, čekající na konfirmační testování, znovu otevřený, uzavřený, zamítnutý),
* odkazy (např. na testovací případ).

Některé z těchto informací mohou být automaticky vkládány nástrojem pro management defektů (např. identifikátor, datum, autor a počáteční stav). Šablony dokumentů pro report o defektu a příklady reportů o defektu lze nalézt v normě ČSN ISO/IEC/IEEE 29119-3 [@ISO29119-3]. Norma však používá termín zpráva o incidentu.