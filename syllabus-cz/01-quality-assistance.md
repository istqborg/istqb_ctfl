## Co je to testování?
Softwarové systémy jsou nedílnou součástí našeho každodenního života. Většina lidí má zkušenosti se softwarem, který fungoval jinak, než očekávali. Software, který nefunguje správně, může vést k mnoha problémům, např. ztrátě peněz, času nebo obchodní pověsti a v extrémních případech dokonce ke zranění nebo smrti. Testování softwaru hodnotí kvalitu softwaru a pomáhá snižovat riziko selhání softwaru v provozu.

Testování softwaru je sada činností, jejichž cílem je odhalování defektů a vyhodnocování kvality softwarových artefaktů, které se při testování označují jako testované objekty. Běžná (a bohužel mylná) představa o testování je, že se jedná pouze o provádění testů (tj. spuštění softwaru a kontrola výsledků testů). Testování softwaru ale zahrnuje i další činnosti a musí být v souladu s životním cyklem vývoje softwaru (viz <#section:improve-quality-and-flow-in-a-value-driven-organization>).

Další běžnou mylnou představou o testování je, že testování se zaměřuje výhradně na ověření testovaného objektu. Testování ale zahrnuje nejen ověření neboli verifikaci (tj. kontrolu, zda systém splňuje specifikované požadavky), ale také validaci (tedy kontrolu, zda systém splňuje potřeby uživatelů a dalších zúčastněných stran v jejich provozním prostředí).

Testování může být dynamické nebo statické. Dynamické testování vyžaduje spuštění testovaného softwaru, zatímco statické testování spuštění nevyžaduje. Statické testování zahrnuje revize (viz <#section:static-testing>) a statickou analýzu. Dynamické testování používá různé techniky testování a přístupy k testování s cílem definovat testovací případy (viz <#section:organizational-test-strategy-in-a-value-driven-organization>).

Testování není jen technická činnost. Rovněž je třeba jej řádně plánovat, řídit, odhadovat, monitorovat a kontrolovat (viz <#section:testPpocesses-strategy-in-a-value-driven-organization>).

Testeři sice používají při testování nástroje (viz <#section:testTools>), ale je důležité si uvědomit, že testování je hlavně intelektuální činnost. Při ní je potřebné, aby testeři měli specializované znalosti, používali analytické dovednosti a aplikovali kritické a systémové myšlení ([@myers2011art],[@roman2018thinking]).

Další informace o konceptech testování softwaru lze nalézt v normě ČSN ISO/IEC/IEEE 29119-1 [@ISO29119-1].

### Typické cíle testování {#typical-testing-objectives}

Typické cíle testování jsou:

* ohodnocení pracovních produktů jako jsou požadavky, uživatelské scénáře, návrhy a kód,
* vyvolání selhání a nalezení defektů,
* zajištění požadovaného pokrytí testovaného objektu,
* snížení úrovně rizika plynoucí z nedostatečné kvality softwaru,
* ověření, zda byly splněny stanovené požadavky,
* ověření, že testovaný objekt vyhovuje smluvním, právním a regulatorním požadavkům,
* poskytnutí informací zúčastněným stranám tak, aby mohly přijmout kvalifikovaná rozhodnutí,
* vytvoření důvěry v danou úroveň kvality testovaného objektu,
* kontrola, zda je testovaný objekt kompletní a funguje dle očekávání všech zúčastněných stran.

Cíle testování se mohou lišit v závislosti na kontextu, který zahrnuje faktory jako je charakteristika testovaného pracovního produktu, úroveň testování, rizika, zvolený životní cyklus vývoje softwaru (SDLC). Kromě toho ale závisí také na byznysovém kontextu s faktory jako struktura společnosti, konkurenční hlediska nebo doba uvedení na trh (time to market).

### Testování a ladění

Testování a ladění (debugging) jsou samostatné činnosti. Testování může vyvolat selhání, která jsou způsobena defekty v softwaru (dynamické testování), nebo může přímo odhalit defekty v testovaném objektu (statické testování).

Zatímco dynamické testování (viz <#section:organizational-test-strategy-in-a-value-driven-organization>) se snaží vyvolat selhání, ladění se zabývá hledáním příčin takových selhání (tj. defektů), jejich analýzou a jejich odstraněním. Typický proces ladění v tomto případě zahrnuje:

* reprodukování selhání,
* diagnostika (nalezení kořenové příčiny),
* oprava příčiny.

Následné tzv. konfirmační testování ověřuje, zda došlo v důsledku těchto oprav k vyřešení problému. Provádí jej ideálně stejná osoba, která provedla prvotní test. Kromě toho lze také provést následné tzv. regresní testování s cílem ověřit, zda opravy nezpůsobují selhání v jiných částech testovaného objektu. Více informací o konfirmačním a regresním testování (viz <#section:confirmation-and-regression-testing>)

Statické testování přímo identifikuje defekt, ladění se pak zabývá jeho odstraněním. Obvykle při něm není nutno provádět reprodukování a diagnostiku, protože statické testování nachází přímo defekty a nemůže způsobit selhání (viz <#section:static-testing>).

## Proč je testování nezbytné?

Testování jako jeden ze způsobů řízení kvality pomáhá při dosažení dohodnutých cílů v rámci stanoveného rozsahu, času, kvality a rozpočtových omezení. K úspěchu projektu nepřispívají nutně pouze činnosti zajištěné testovacím týmem – kdokoliv ze zúčastněných stran může využít své testovací dovednosti k tomu, aby se projekt přiblížil ke svému úspěšnému cíli. Testování komponent, systémů a související dokumentace pomáhá identifikovat defekty v softwaru.

### Jak testování přispívá k úspěchu

Testování poskytuje nákladově efektivní způsob detekce defektů. Tyto defekty lze odstranit (laděním, tedy aktivitou, která nespadá pod oblast testování), takže testování vlastně nepřímo přispívá ke kvalitnějším testovaným objektům.

Testování poskytuje prostředky pro přímé hodnocení kvality testovaného objektu v různých fázích SDLC. Tato hodnocení se používají jako součást širších aktivit managementu projektů a přispívají tak k rozhodnutí o přechodu do další fáze SDLC, například k rozhodnutí o vydání. Testování tak vlastně poskytuje uživatelům nepřímou reprezentaci celého vývojového projektu.

Testeři jsou zárukou toho, že jejich pochopení potřeb uživatelů je zohledněno v průběhu celého životního cyklu vývoje. Alternativou k využití testerů je zapojení reprezentativní skupiny uživatelů do projektu, což ale obvykle není možné kvůli vysokým nákladům a nedostatečné dostupnosti vhodných uživatelů.

Vedle hodnocení kvality testovaného objektu může být testování softwaru vyžadováno také z důvodu splnění smluvních nebo zákonných požadavků či regulatorních norem.

### Testování a zajištění kvality

Lidé často zaměňují pojmy testování a zajištění kvality (QA – quality assurance), nicméně není to totéž.

Testování je forma řízení kvality (QC – quality control). QC je nápravný přístup zaměřený na produkt a zaměřuje se na činnosti podporující dosažení odpovídající úrovně kvality. Testování je sice hlavní formou QC, nicméně není jedinou. Lze využít i jiné formální metody (např. ověření modelu nebo důkazy správnosti), případně simulace nebo prototypování.

QA je preventivní přístup orientovaný na procesy, který se zaměřuje na jejich zavádění a zlepšování. Je založen na předpokladu, že pokud je dodržován správný proces, pak je jeho výsledkem správný produkt. QA se vztahuje na procesy vývoje i testování a je odpovědností všech osob v projektu.

Výsledky testů jsou využívány v QA i v QC. V QC se používají k opravě defektů, zatímco v QA poskytují zpětnou vazbu o tom, jak dobře fungují procesy vývoje a testování.

### Chyby, defekty, selhání a kořenové příčiny

Lidé dělají chyby (omyly), v jejichž důsledku vznikají defekty (vady, bugy), které mohou vést k selhání. Lidské chyby vznikají z různých důvodů jako jsou časová tíseň nebo složitost pracovních produktů, procesů, infrastruktury a interakcí. Chyby mohou také vzniknout jednoduše proto, že jsou lidé unavení nebo jim chybí odpovídající školení.

Defekty lze nalézt v dokumentaci (např. ve specifikaci požadavků nebo testovacím skriptu), ve zdrojovém kódu nebo v jakémkoliv podpůrném artefaktu, např. v souboru sestavení (buildu). Pokud nejsou zjištěny defekty artefaktů vzniklých v dřívějších fázích SDLC, vedou často ke vzniku defektních artefaktů v jeho navazujících fázích.

Pokud je spuštěn defekt v kódu, systém nemusí dělat to, co by měl dělat nebo může udělat něco, co by neměl. To může (ale nemusí) způsobit selhání. Některé defekty mohou vést při spuštění k selhání vždy, jiné pouze za určitých okolností, některé dokonce nemusí selhání způsobit nikdy.

Chyby a defekty nejsou jedinou příčinou selhání. Selhání mohou být způsobena také podmínkami prostředí, příkladem může být defekt u firmwaru způsobený zářením nebo působením elektromagnetického pole.

Kořenová příčina je primárním důvodem vzniku problému (např. situace, která vede k chybě). Kořenové příčiny lze identifikovat pomocí jejich analýzy, která se obvykle provádí po výskytu selhání nebo identifikaci defektu. Předpokládá se, že řešením kořenové příčiny (nejlépe jejím odstraněním) lze zabránit podobným selháním nebo defektům (popř. alespoň snížit jejich četnost).

## Principy testování {#testing-principles}

Během posledních let byla zdokumentována řada principů, které poskytují obecný návod aplikovatelný pro všechny druhy testování. Tyto učební osnovy popisují sedm takových principů.

**1. Testování prokazuje přítomnost defektů, nikoli jejich nepřítomnost.** Testování může prokázat, že defekty jsou v testovaném objektu přítomny, ale nemůže prokázat, že v něm žádné nejsou [@buxton1970software]. Testování snižuje pravděpodobnost, že v testovaném objektu zůstaly neodhalené defekty, nicméně pokud nejsou žádné defekty nalezeny, není tím prokázána jeho správnost.

**2. Kompletní testování není možné.** Testování všeho (např. všech kombinací vstupů) není možné s výjimkou triviálních případů [@manna1978logic]. Místo snahy o kompletní testování je lepší se zaměřit na vhodné techniky testování (viz <#section:organizational-test-strategy-in-a-value-driven-organization>), stanovení priorit testovacích případů (viz <#section:test-cases-prioritization>) a testování založené na rizicích (viz <#section:risk-management>).

**3. Včasné testování šetří čas a peníze.** Defekty, které jsou odstraněny v rané fázi procesu, nezpůsobí následně jiné defekty v odvozených (následných) pracovních produktech. Náklady na kvalitu budou navíc sníženy, protože později v SDLC dojde k menšímu počtu selhání [@boehm1981software]. Pro včasné odhalení defektů by mělo být co nejdříve zahájeno jak statické testování (viz <#section:static-testing>), tak dynamické testování (viz <#section:organizational-test-strategy-in-a-value-driven-organization>).

**4. Shlukování defektů.** Většinu zjištěných defektů obsahuje obvykle malé množství systémových komponent, případně je malé množství systémových komponent zodpovědných za většinu provozních selhání [@endres1975analysis]. Tento jev je ilustrací tzv. Paretova pravidla. Předpokládané a skutečně pozorované shluky defektů během testování nebo v provozu jsou významným vstupem pro testování založené na rizicích (viz <#section:risk-management>).

**5. Testy se opotřebovávají.** Pokud se stejné testy opakují neustále dokola, stávají se stále méně účinnými a nedochází k odhalování nových defektů [@beizer1990software]. Abychom se vypořádali s důsledky tohoto principu, je nutné měnit stávající testy a testovací data, příp. je potřeba vytvořit testy nové. V některých případech má však opakování stejných testů význam, např. při automatizovaném regresním testování (viz <#section:confirmation-and-regression-testing>).

**6. Testování je závislé na kontextu.** Neexistuje jediný univerzálně použitelný přístup k testování, testování se provádí odlišně v různých kontextech [@kaner1999testing].

**7. Nepřítomnost defektů je klam.** Je mylnou představou očekávat, že pouhé ověřování (verifikace) softwaru zajistí jeho úspěch. I při důkladném testování všech specifikovaných požadavků a odstranění všech zjištěných defektů může vzniknout systém, který nesplňuje potřeby a očekávání uživatelů, který nepomáhá dosahovat byznysových cílů zákazníka, a který je horší ve srovnání s jinými konkurenčními systémy. Kromě ověřování by měla být provedena také validace [@boehm1981software].

## Testovací činnosti, testware a role v testování

Testování je sice závislé na kontextu, nicméně existují testovací činnosti, bez nichž je méně pravděpodobné, že bude dosaženo vytyčených cílů. Skupiny takových činností nazýváme proces testování. Proces testování může být přizpůsoben dané situaci na základě různých faktorů. O tom, které testovací činnosti jsou zahrnuty do procesu testování, jak jsou implementovány a kdy k nim dojde, se obvykle rozhoduje v rámci plánování testování pro konkrétní situaci (viz <#section:planning-testing>).

Následující text popisuje obecné aspekty tohoto procesu z hlediska testovacích činností a úkolů, vlivu kontextu, testwaru, trasovatelnosti mezi testovací bází a testwarem a také rolí v testování.

Další informace o procesech testování lze nalézt v normě ČSN ISO/IEC/IEEE 29119-2 [@ISO29119-2].

### Testovací činnosti a úkoly {#test-activities-and-tasks}

Proces testování se obvykle skládá z hlavních skupin činností (viz dále), které je obvykle nutno přizpůsobit systému a projektu. I když se mnohé z těchto hlavních skupin činností mohou jevit jako logicky seřazené za sebou, jsou často prováděny iterativně nebo paralelně.

**Plánování testování** se skládá z definování cílů testování a následného výběru takového přístupu, který nejlépe dosahuje definovaných cílů v rámci omezení daných celkovým kontextem. Plánování testování je dále vysvětleno v <#section:planning-testing>.

**Monitoring a řízení testování**. Monitoring testování zahrnuje průběžnou kontrolu všech testovacích činností a porovnávání skutečného stavu proti plánu, řízení testování se zabývá přijetím opatření nezbytných pro dosažení cílů testování. Monitoring a řízení testování jsou dále vysvětleny v <#section:monitoring-management-completion-of-testing>.

**Testovací analýza** zahrnuje analýzu testovací báze za účelem identifikace testovatelných užitných vlastností (features) a definování příslušných testovacích podmínek včetně stanovení jejich priorit a souvisejících rizik spolu s jejich úrovněmi (viz <#section:risk-management>). Testovací báze a testované objekty jsou také hodnoceny za účelem posouzení jejich testovatelnosti a identifikace případných defektů v nich obsažených. Při testovací analýze jsou často používány techniky testování (viz <#section:organizational-test-strategy-in-a-value-driven-organization>). Testovací analýza určuje „Co se má testovat?" ve smyslu měřitelných kritérií pokrytí.

**Návrh testů** zahrnuje rozpracování testovacích podmínek do testovacích případů a dalšího testwaru (např. testovacích listin). Často obsahuje také identifikaci položek pokrytí sloužících jako vodítko pro stanovení vstupů testovacích případů. Při této činnosti lze použít taktéž vhodné techniky testování (viz <#section:organizational-test-strategy-in-a-value-driven-organization>). Návrh testů také zahrnuje stanovení požadavků na testovací data, návrh testovacího prostředí a identifikaci další potřebné infrastruktury nebo nástrojů. Návrh testů dává odpověď na otázku „Jak testovat?".

**Implementace testování** zahrnuje vytvoření nebo získání testwaru nezbytného pro provedení testů (např. testovací data). Testovací případy mohou být uspořádány do testovacích procedur a jsou často seskupeny do testovacích sad. Mimo jiné jsou v rámci této činnosti vytvářeny manuální a automatizované testovací skripty. Z důvodu efektivního provedení testů (viz <#section:test-cases-prioritization>) jsou testovací procedury prioritizovány a uspořádány v harmonogramu provedení testů. Součástí činností implementace testování je sestavení testovacího prostředí a ověření jeho správného nastavení.

**Provedení testů** zahrnuje spuštění testů v souladu s harmonogramem provedení testů (jako dílčích běhů testů, test runs). Provedení testů může být manuální nebo automatizované a může mít mnoho forem včetně tzv. průběžného nebo párového testování. V rámci této činnosti jsou porovnány skutečné výsledky testů s očekávanými a zaznamenány jejich výsledky. Anomálie jsou analyzovány s cílem identifikace jejich pravděpodobné příčiny. Tato analýza umožňuje reportovat anomálie na základě pozorovaných selhání (viz <#section:defects-management>).

K činnostem **dokončení testování** obvykle dochází při dosažení milníků projektu (např. vydání, konec iterace, dokončení úrovně testování) a provádí se pro všechny nevyřešené defekty, požadavky na změny nebo vytvořené položky produktového backlogu. Jakýkoli testware, který může být v budoucnu užitečný, je identifikován a archivován, případně je předán příslušným týmům. Testovací prostředí se uvede do dohodnutého stavu (např. je vypnuto). Testovací činnosti jsou analyzovány s cílem identifikace získaných poznatků a vylepšení pro případné budoucí iterace, vydání nebo i jiné projekty (viz <#section:retrospectives-and-process-improvement>). Je vytvořen souhrnný report z testování, který je komunikován příslušným zúčastněným stranám.

### Proces testování v souvislostech

Testování neprobíhá izolovaně. Testovací činnosti jsou nedílnou součástí procesů vývoje prováděných v rámci organizace. Finálním cílem testování je (mimo jiné) pomoci splnit byznysové potřeby zúčastněných stran, které také proces testování financují. Způsob, jakým se testování provádí, bude proto záviset na řadě faktorů, například:

* zúčastněné strany (jejich potřeby, očekávání, požadavky, ochota spolupracovat),
* členové týmu (jejich dovednosti, znalosti, úroveň zkušeností, dostupnost, potřeby školení),
* obor podnikání (kritičnost testovaného objektu, identifikovaná rizika, potřeby trhu, konkrétní právní předpisy),
* technické faktory (typ softwaru, architektura produktu, použité technologie),
* omezení projektu (rozsah, čas, rozpočet, zdroje),
* organizační faktory (organizační struktura, existující politiky, používané postupy),
* životní cyklus vývoje softwaru (technické postupy, metody vývoje atd.),
* nástroje (dostupnost, použitelnost, shoda s předpisy).

Tyto faktory budou mít dopad na mnoho aspektů souvisejících s testováním včetně strategie testování, použitých technik testování, stupně automatizace testů, požadované úrovně pokrytí, úrovně podrobnosti dokumentace testování, reportování atd.

### Testware

Testware je definován jako výstupní pracovní produkt z testovacích činností popsaných v [kapitola 1.4.1](#section:{#test-activities-and-tasks}). V tom, jak různé organizace vytvářejí, pojmenovávají, organizují a spravují takové pracovní produkty, existují nicméně značné rozdíly. Pro podporu konzistence a integrity testwaru je důležité zajištění dobrého konfiguračního managementu (viz <#section:configuration-management>).

Následující seznam uvádí některé (ale ne všechny) takové typické výstupní pracovní produkty (testware):

* **Pracovní produkty z plánování testování** : plán testování, harmonogram testování, registr rizik a vstupní a výstupní kritéria (viz <#section:planning-testing>). Registr rizik je seznam rizik spolu s jejich pravděpodobností, dopadem a informacemi o jejich možném zmírnění (risk mitigation), viz <#section:risk-management>. Harmonogram testování, registr rizik, vstupní a výstupní kritéria jsou často součást plánu testování.
* **Pracovní produkty z monitoringu a řízení testování** : reporty o postupu prací při testování (viz kapitola 5.3.2), pokyny a nezbytná nápravná opatření (viz <#section:monitoring-management-completion-of-testing>) a informace o rizicích (viz kapitola 5.2).
* **Pracovní produkty z testovací analýzy** : (prioritizované) testovací podmínky (např. akceptační kritéria, viz kapitola 4.5.2) a reporty o defektech v testovací bázi (pokud už nebyly opraveny).
* **Pracovní produkty z návrhu testů** : (prioritizované) testovací případy, testovací listiny, položky pokrytí, požadavky na testovací data a požadavky na testovací prostředí.
* **Pracovní produkty z implementace testování** : testovací procedury, automatizované testovací skripty, testovací sady, testovací data, harmonogram provedení testů a prvky testovacího prostředí. Mezi příklady položek testovacího prostředí patří stuby, ovladače, simulátory a virtualizace služeb.
* **Pracovní produkty z provedení testů** : protokoly z testování (test logs) a reporty o defektech (viz kapitola 5.5).

* **Pracovní produkty z dokončení testování** : souhrnný report z testování (viz <#section:purpose-content-target-of-test-reports>), akční body pro zlepšení budoucích projektů nebo iterací, zdokumentované získané poznatky (lessons learned) a změnové požadavky (např. jako položky produktového backlogu).

### Trasovatelnost mezi testovací bází a pracovními produkty z testování

Aby bylo možné efektivně monitorovat a řídit testování, je důležité vytvořit a následně udržovat v průběhu celého procesu testování trasovatelnost mezi každou položkou testovací báze, výstupními pracovními produkty vztaženým k této položce (testwarem − např. testovací podmínky, rizika nebo testovací případy), výsledky testů a nalezenými defekty.

Přesná trasovatelnost umožňuje vyhodnocovat pokrytí, takže je velmi užitečné, pokud jsou v testovací bázi pro toto pokrytí definována jeho měřitelná kritéria. Kritéria pokrytí mohou představovat jeden z klíčových ukazatelů výkonnosti (KPI – key performance indicator) pro řízení testovacích činností, která ukazují na míru dosažení cílů testování (viz <#section:typical-testing-objectives>). Například:

* Trasovatelnost mezi testovacími případy a požadavky pomůže ověřit, že požadavky jsou pokryty testovacími případy.
* Trasovatelnost mezi výsledky testů a riziky lze použít k vyhodnocení úrovně zbytkového rizika u testovaného objektu.

Kromě vyhodnocení pokrytí umožňuje dobrá trasovatelnost určit dopad změn, usnadňuje provádění auditů testování a pomáhá plnit kritéria zásad správného řízení v IT. Dobrá trasovatelnost rovněž zlepšuje srozumitelnost reportů o postupu prací při testování a souhrnných reportů z testování tím, že ukazuje stav položek testovací báze. To může rovněž přispět ke srozumitelné komunikaci se zúčastněnými stranami o technických aspektech testování. Trasovatelnost poskytuje informace pro posouzení kvality produktu, způsobilosti procesů a postupu prací v projektu vzhledem k byznysovým cílům.

### Role v testování

V těchto učebních osnovách jsou definovány dvě hlavní role při testování: role manažera testování a role testera. Činnosti a úkoly vykonávané těmito dvěma rolemi závisí na kontextu projektu a produktu, na dovednostech lidí v daných rolích a na dané organizaci.

**Manažer testování** má celkovou odpovědnost za proces testování, testovací tým a úspěšné řízení testovacích činností. Zaměřuje se především na činnosti plánování testování, monitoringu a řízení testování a dokončení testování. Způsob, jakým se tato role vykonává, se liší v závislosti na životním cyklu vývoje softwaru, například v agilním vývoji jsou některé úkoly manažera testování vykonávány celým agilním týmem. Úkoly, které zahrnují více týmů nebo celou organizaci, mohou být prováděny manažery testování mimo vývojový tým.

**Tester** přebírá celkovou odpovědnost za inženýrský (technický) aspekt testování. Zaměřuje se především na činnosti testovací analýzy, návrhu testů, implementace testování a provedení testů.

Obě role mohou být vykonávány v různých obdobích různými lidmi, například role manažera testování může být vykonávaná vedoucím týmu, samotným manažerem testování nebo manažerem vývoje. Je také možné, aby jedna osoba převzala roli testera i roli manažera testování současně.

## Základní dovednosti a osvědčené postupy při testování

Dovednost je schopnost dělat něco dobře a vychází z něčích znalostí, praxe a schopností. Aby mohli testeři dobře vykonávat svou práci, potřebují mít určité základní dovednosti, mimo jiné by měli být dobrými týmovými hráči a měli by být schopni pracovat v různých úrovních nezávislosti testování.

#### Obecné dovednosti potřebné pro testování {#general-skills-needed-for-testing}

Následující dovednosti jsou sice obecné, ale pro testery obzvláště důležité:

* Znalost testování (s cílem zvyšování efektivity testování, např. pomocí technik testování).
* Důkladnost, pečlivost, zvídavost, důraz na detail, schopnost pracovat metodicky (s cílem identifikace defektů, a to zejména těch, které lze jen obtížně najít).
* Dobré komunikační dovednosti, aktivní naslouchání, schopnost být týmovým hráčem (s cílem efektivně komunikovat se všemi zúčastněnými stranami, předávat informace ostatním, být pochopen, reportovat defekty a diskutovat o nich).
* Analytické myšlení, kritické myšlení, kreativita (s cílem zvyšování efektivity testování).
* Technické znalosti (s cílem zvyšování efektivity testování, např. použitím vhodných testovacích nástrojů).
* Znalost domény (s cílem mít schopnost porozumět koncovým uživatelům nebo obchodním zástupcům a komunikovat s nimi).

Běžnou lidskou vlastnosti je obviňování nositelů špatných zpráv a testeři jsou často nositeli takových špatných zpráv. Z tohoto důvodu jsou pro testery klíčové komunikační dovednosti – sdělování výsledků testů může být totiž vnímáno jako kritika produktu a jeho autora.

Termín konfirmační zkreslení (confirmation bias) popisuje tendenci člověka obtížně přijímat informace, které jsou v rozporu s jeho stávajícími názory. Jedná se o psychologický faktor, v jehož důsledku mohou někteří lidé vnímat testování jako destruktivní aktivitu, přestože významně přispívá k úspěchu projektu a kvalitě produktu. Při snaze snížit tato vnímání by informace o defektech a selháních měly být komunikovány konstruktivně a bez emocí.

### Týmový přístup {#team-approach}

Jednou z důležitých dovedností testerů je schopnost efektivně pracovat v týmu a pozitivně přispívat k týmovým cílům. Tzv. týmový přístup (whole team approach, technika vycházející z extrémního programování, viz <#section:testing-in-context-of-software-development-life-cycle>) je postaven na této dovednosti.

Při týmovém přístupu může každý člen týmu s potřebnými znalostmi a dovednostmi vykonávat jakýkoliv úkol a každý člen týmu je zodpovědný za kvalitu. Členové týmu sdílejí stejný pracovní prostor, protože společné umístění v jednom fyzickém nebo virtuálním prostoru usnadňuje vzájemnou komunikaci a interakci. Týmový přístup zvyšuje týmovou dynamiku, zlepšuje komunikaci a spolupráci v rámci týmu a vytváří synergii tím, že umožňuje využití různých dovedností v týmu ve prospěch projektu.

Pokud má být dosaženo požadované úrovně kvality, musí testeři úzce spolupracovat s ostatními členy týmu. To zahrnuje (mimo jiné) spolupráci s obchodními zástupci (kteří mohou např. pomoci s vytvořením vhodných akceptačních testů) nebo s vývojáři (např. s cílem dosahovat společné dohody o strategii testování a o přístupech k automatizaci testů). Testeři mohou také předávat znalost testování ostatním členům týmu a ovlivňovat vývoj produktu.

Týmový přístup nemusí být v kontextu projektu vždy vhodnou metodikou. Typickým příkladem je testování bezpečnostně kritických scénářů, kdy je nutné zachovat vysokou úroveň nezávislosti testování.

### Nezávislost testování

Určitá míra nezávislosti činí testery efektivnějšími při hledání defektů, což je způsobeno rozdíly mezi kognitivním zkreslením autorů (vývojářů) a testerů [@salman2016cognitive]. Nezávislost však není náhrada za dobrou znalost systému – i vývojáři mohou efektivně najít mnoho defektů ve svém vlastním kódu.

Pracovní produkty mohou být testovány jejich autorem (nulová nezávislost), kolegy autora ze stejného týmu (malá nezávislost), testery mimo tým autora, ale v rámci organizace (vysoká nezávislost) nebo testery mimo organizaci (velmi vysoká nezávislost). U většiny projektů je obvykle nejlepší provádět testování s více úrovněmi nezávislosti (např. vývojáři provádějící testování komponent a integrační testování komponent, testovací tým provádějící systémové testování a systémové integrační testování a obchodní zástupci provádějící akceptační testování).

Hlavním přínosem nezávislosti testování je to, že nezávislí testeři dokáží pravděpodobněji rozpoznat různé druhy selhání a defektů ve srovnání s vývojáři, a to z důvodu jejich odlišného zázemí, technického nadhledu a předsudků. Nezávislí testeři mohou navíc ověřit, napadnout či vyvrátit předpoklady, které měly zúčastněné strany v době přípravy specifikace či implementace systému.

Existují však i některé nevýhody. Nezávislí testeři mohou být izolováni od vývojového týmu, což může vést k nedostatečné spolupráci, problémům v komunikaci nebo nepřátelskému vztahu s vývojovým týmem. Vývojáři mohou ztratit pocit zodpovědnosti za kvalitu. Nezávislí testeři mohou být úzkým místem ve vývojovém procesu nebo mohou být viněni za zpoždění při vydávání produktu.