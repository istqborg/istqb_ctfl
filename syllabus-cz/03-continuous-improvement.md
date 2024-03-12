## Základy statického testování

Na rozdíl od dynamického testování není při statickém testování nutné testovaný software spouštět. Kód, specifikace procesu, specifikace architektury systému nebo jiné pracovní produkty jsou hodnoceny a prověřovány buďto manuálně (např. revizemi) nebo pomocí nástroje (např. statická analýza). Mezi cíle testování patří zlepšování kvality, odhalování defektů a posuzování vlastností jako je čitelnost, úplnost, správnost, testovatelnost a konzistence. Statické testování lze používat jak pro ověřování (verifikaci), tak pro validaci.

Testeři, zástupci byznysu a vývojáři během popisu příkladů (např. při využití techniky specifikace pomocí příkladů), psaní uživatelských scénářů a zpřesňování backlogu (backlog refinement) spolupracují tak, aby uživatelské scénáře a související pracovní produkty splňovaly definovaná kritéria, např. definice připravenosti (viz <#section:entry-and-exit-criteria>). Techniky revizí lze použít k zajištění toho, aby uživatelské scénáře byly úplné a srozumitelné a obsahovaly testovatelná akceptační kritéria. Tím, že testeři kladou správné otázky vlastně zkoumají, konfrontují a pomáhají vylepšovat navrhované uživatelské scénáře.

Statická analýza může upozornit na problémy ještě před provedením dynamického testování, přičemž často vyžaduje menší pracnost – nevyžaduje totiž tvorbu testovacích případů a lze u ní využít různých nástrojů (viz <#section:testTools>). Statická analýza je často začleněna do nástrojů průběžně integrace (viz <#section:devops-and-testing>). I když se z velké části používá k odhalování specifických defektů kódu, lze ji také použít k vyhodnocení udržovatelnosti a bezpečnosti. Dalšími příklady nástrojů statické analýzy jsou nástroje pro kontrolu pravopisu a čitelnosti.

### Pracovní produkty, které mohou být prověřeny statickým testováním

Téměř každý pracovní produkt může být prozkoumán pomocí statického testování. Mezi takové produkty patří například specifikace požadavků, zdrojový kód, plány testování, testovací případy, položky produktového backlogu, testovací listiny, projektová dokumentace, smlouvy nebo modely.

**Revizi** lze použít na jakýkoliv pracovní produkt, který lze přečíst a porozumět mu.

Pro **statickou analýzu** je nutné, aby měly zkoumané pracovní produkty formální strukturu, vůči které mohou být kontrolovány (např. modely, kód nebo text s formální syntaxí).

Pracovní produkty, které nejsou vhodné pro statické testování, jsou obvykle ty, které jsou obtížně interpretovatelné lidmi a současně by neměly být analyzovány nástroji (např. spustitelný kód třetí strany, který z právních důvodů nelze analyzovat s využitím nástrojů).

### Přínosy statického testování

Statické testování může odhalit defekty v nejranějších fázích SDLC, čímž naplňuje princip včasného testování (viz <#section:testing-principles>). Může také odhalit defekty, které nelze zjistit dynamickým testováním (např. nedosažitelný kód, chybně implementované návrhové vzory, defekty v nespustitelných pracovních produktech).

Statické testování vytváří důvěru v dané pracovní produkty a umožňuje vyhodnotit jejich kvalitu. Ověřením zdokumentovaných požadavků mohou zúčastněné strany také zajistit, aby tyto požadavky odrážely jejich skutečné potřeby. Vzhledem k tomu, že statické testování může být prováděno v raných fázích SDLC, je možné nastavit pravidla jednotného chápání (např. požadavků), čímž se také zlepší komunikace mezi zúčastněnými stranami. Z tohoto důvodu se doporučuje zapojit do statického testování různé typy účastníků.

I když může být provedení revizí nákladné, celkové náklady na projekt jsou obvykle mnohem nižší, než když se revize vůbec neprovádí. Důvodem je to, že později v projektu není potřeba vynaložit tolik času a pracnosti na opravu defektů.

Některé defekty v kódu lze odhalit pomocí statické analýzy mnohem efektivněji než při dynamickém testování, což obvykle vede k jejich menšímu počtu a tím i nižší celkové pracnosti při vývoji.

### Rozdíly mezi statickým a dynamickým testováním

Statické a dynamické testovací postupy se vzájemně doplňují. Mají podobné cíle (např. odhalování defektů v pracovních produktech, viz <#section:typical-testing-objectives>), ale existují mezi nimi také určité rozdíly, například:

* Jak statické, tak dynamické testování (včetně analýzy selhání) může vést k odhalení defektu, nicméně existují některé typy defektů, které lze nalézt buď jenom statickým nebo jenom dynamickým testováním.
* Statické testování najde defekty přímo, zatímco dynamické testování hledá selhání, ze kterých jsou příslušné defekty určeny následnou analýzou.
* Statické testování může snadněji odhalovat defekty obtížně dosažitelné pomocí dynamického testování nebo takové, které jsou v kódu v částech spouštěných jen zřídka.
* Dynamické testování lze použít pouze na spustitelné pracovní produkty, statické testování i na nespustitelné.
* Statické testování lze použít k měření kvalitativních charakteristik (např. udržovatelnosti) nezávislých na spuštění kódu, dynamické testování pouze k těm, které jsou na spuštění kódu závislé (např. výkonnostní efektivity).

Mezi typické defekty odhalitelné snadněji a levněji statickým testováním patří:

* defekty v požadavcích (např. nesrovnalosti, nejednoznačnosti, rozpory, opomenutí, nepřesnosti a duplicity),
* defekty v návrhu (např. neefektivní databázové struktury, špatná modularita),
* některé typy defektů při kódování (např. proměnné s nedefinovanými hodnotami, nedeklarované proměnné, nedosažitelný nebo duplicitní kód, nadměrná složitost kódu),
* odchylky od norem (např. nedostatečné dodržování konvencí pro kódování),
* nesprávné specifikace rozhraní (např. rozdílný počet, typ nebo pořadí parametrů),
* některé bezpečnostní zranitelnosti (např. přetečení vyrovnávací paměti),
* chybějící části nebo nepřesnosti v pokrytí testovací báze (např. chybějící testy pro některé akceptační kritérium).

## Proces zpětné vazby a revize

### Výhody včasné a časté zpětné vazby od zúčastněných stran {#benefits-early-and-frequent-feedback-from-stakeholders}

Včasná a častá zpětná vazba pomáhá s odhalením potenciálních problémů s kvalitou. Pokud se zúčastněné strany zapojují do vývoje nedostatečně, vyvíjený produkt nemusí splňovat jejich původní nebo současné představy. Pokud není tým schopen dodat to, co zúčastněná strana chce, hrozí riziko vícenákladů na přepracování, zmeškaných termínů, vzájemného obviňování, a dokonce může dojít k úplnému selhání projektu.

Častá zpětná vazba zúčastněných stran během SDLC může zabránit nedorozuměním při definici požadavků a zajistit, aby změny požadavků byly správně a včas pochopeny a implementovány. To pomáhá vývojovému týmu lépe porozumět tomu, co vyvíjí. Umožňuje jim také zaměřit se na ty užitné vlastnosti, které přinášejí zúčastněným stranám nejvyšší přidanou hodnotu, a které mají nejvíce pozitivní dopad na zjištěná rizika.

### Činnosti procesu revize {#review-process-activities}

Norma ISO/IEC 20246 [@ISO20246] definuje obecný proces revize a popisuje strukturovaný, ale flexibilní rámec, ze kterého může být daný proces revize přizpůsoben konkrétní situaci. Čím vyšší je požadovaný stupeň formálnosti revize, tím vyšší je počet úkolů během různých činností.

Mnohé pracovní produkty jsou tak rozsáhlé, že je nelze pokryt pouze jedinou revizí a proces revize může být proveden opakovaně.

Činnosti procesu revize jsou:

* **Plánování**. Během fáze plánování se stanoví rozsah revize obsahující definici účelu a revidovaného pracovního produktu, kvalitativní charakteristiky pro vyhodnocení, oblasti zájmu, výstupní kritéria, doplňující informace (např. normy), pracnost a časový rámec celé revize.
* **Zahájení revize**. Během zahájení revize je cílem zajistit, aby bylo všechno (včetně zúčastněných stran) připraveno k revizi. To mimo jiné vyžaduje, aby měl každý účastník přístup k revidovanému pracovnímu produktu, rozuměl své roli a odpovědnostem a obdržel vše potřebné k provedení revize.
* **Individuální revize**. Každý revidující reviduje definovaný pracovní produkt individuálně s cílem posoudit jeho kvalitu a identifikovat anomálie, doporučení a otázky pomocí jedné nebo více technik revize (např. revize založená na kontrolním seznamu, revize založená na scénáři – viz norma ISO/IEC 20246 [@ISO20246]). Revidující zaznamenává všechny zjištěné anomálie, doporučení a otázky.
* **Komunikace a analýza**. Ne každá anomálie identifikovaná během revize musí být nutně defekt. Proto je nutné všechny takové anomálie analyzovat a prodiskutovat a u každé by mělo být rozhodnuto o jejím stavu, vlastnictví a požadovaných opatřeních. To se obvykle provádí při revizní schůzce, během níž účastníci také diskutují o úrovni kvality každého revidovaného pracovního produktu a jaká následná opatření jsou vyžadována. K uzavření opatření může být vyžadována další revize.
* **Opravy a reportování**. Aby bylo možné provést nápravu, měl by být pro každý defekt vytvořen report o defektu. Při splnění daných výstupních kritérií může být pracovní produkt akceptován a výsledky revize jsou reportovány.

### Role a odpovědnosti při revizích

Revizi mohou provádět různí lidé a mohou zastávat různé role. Hlavní role a jejich povinnosti jsou:

* **Manažer** – rozhoduje o tom, co má být revidováno a jaké zdroje budou využity (včetně lidí a času).
* **Autor** – vytváří a opravuje revidovaný pracovní produkt.
* **Moderátor** (někdy také facilitátor) – zajišťuje efektivní průběh revizních schůzek včetně využití mediace. Mimo jiné dohlíží na dodržení časového rámce a zajištění komfortního prostředí, ve kterém může každý svobodně vyjádřit svůj názor.
* **Zapisovatel** – shromažďuje anomálie od revidujících a zaznamenává další informace z revize jako např. různá rozhodnutí nebo nové anomálie zjištěné během revizní schůzky.
* **Revidující** – provádí revizi. Revidujícím může být někdo, kdo pracuje na projektu nebo je odborníkem na danou problematiku nebo i jakákoli jiná zúčastněná strana.
* **Vedoucí revize** – přebírá celkovou odpovědnost za revizi (např. rozhodování o tom, kdo do ní bude zapojen) a organizaci toho, kdy a kde se bude revize konat.

Popis dalších možných rolí lze nalézt v normě ISO/IEC 20246 [@ISO20246].

### Typy revizí

Existuje mnoho typů revizí, od neformálních až po velmi formální. Požadovaná úroveň formálnosti závisí na faktorech jako je použitý SDLC, vyspělost procesu vývoje, kritičnost a složitost revidovaného pracovního produktu, právní nebo regulatorní požadavky a potřeba doložení záznamů pro případný audit. Stejný pracovní produkt může být revidován různými typy revizí, např. nejprve neformální a později formálnější.

Výběr správného typu revize je klíčový pro dosažení požadovaných cílů revize (viz<#section:success-factors-for-reviews>). Výběr je ale založen na dalších faktorech jako jsou potřeby projektu, dostupné zdroje, typ pracovního produktu, typ rizika, byznysová doména a firemní kultura.

Mezi běžně používané typy revizí patří:

* **Neformální revize**. Neformální revize se neřídí definovaným procesem a nevyžadují formální dokumentovaný výstup. Hlavním cílem je odhalování anomálií.
* **Předvedení (walkthrough)**. Předvedení (vedené autorem) může sloužit mnoha cílům jako je hodnocení kvality a budování důvěry v pracovní produkt, vzdělávání revidujících, dosažení dohody, generování nových nápadů, motivace a podpora autora s cílem zlepšovat pracovní produkt a odhalovat anomálie. Revidující mohou (ale nemusí) před předvedením provést individuální revizi.
* **Technická revize**. Technickou revizi provádějí odborně kvalifikovaní revidující a vede ji moderátor. Cílem technické revize je primárně dosáhnout shody a učinit rozhodnutí týkající se nějakého technického problému, ale také odhalit anomálie, vyhodnotit kvalitu, vybudovat důvěru v pracovní produkt, generovat nové nápady, motivovat autory a podpořit je ve zlepšování.
* **Inspekce**. Vzhledem k tomu, že inspekce jsou nejformálnějším typem revize, řídí se komplexním obecným procesem (viz <#section:review-process-activities>). Hlavním cílem je nacházet maximální počet anomálií. Dalšími cíli jsou hodnocení kvality, budování důvěry v pracovní produkt, motivace a podpora autorů ve zlepšování. Jsou shromažďovány metriky, které se používají ke zlepšování celého SDLC včetně samotného procesu inspekce. Při inspekcích nemůže autor vystupovat jako vedoucí revize nebo zapisovatel.

### Faktory úspěchu při revizi {#success-factors-for-reviews}

Existuje několik faktorů klíčových pro úspěch procesu revize:

* Jsou definovány jasné cíle a měřitelná výstupní kritéria. Nejsou hodnoceni účastníci revize, ale revidovaný pracovní produkt.
* Je vybrán takový typ revize, který je vhodný pro dosažení daných cílů, pro typ pracovního produktu, pro účastníky revize a pro potřeby a kontext projektu.
* Revize jsou prováděné po malých částech, takže revidující neztrácejí koncentraci během revize a/nebo během revizních schůzek (pokud se konají).
* Zúčastněným stranám a autorům je poskytována zpětná vazby z revizí tak, aby mohli zlepšovat produkt a své činnosti (viz <#section:benefits-early-and-frequent-feedback-from-stakeholders>).
* Účastníci mají dostatek času na přípravu.
* Management podporuje proces revize.
* Revize jsou součástí firemní kultury s cílem podporovat učení a zlepšování procesů.
* Je poskytnuto vhodné odborné školení pro všechny účastníky tak, aby věděli, jak plnit svou roli v procesu.
* Schůzky jsou správně řízené.