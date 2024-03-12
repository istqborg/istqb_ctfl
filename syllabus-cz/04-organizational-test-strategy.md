## Přehled technik testování {#overview-of-testing-techniques}
Techniky testování podporují testery při testovací analýze (ve smyslu „co testovat") a při návrhu testů (ve smyslu „jak testovat") a pomáhají systematicky definovat relativně malou, ale dostatečnou sadu testovacích případů. Pomáhají také testerům (opět během testovací analýzy a návrhu testů) definovat testovací podmínky, identifikovat položky pokrytí a identifikovat testovací data. Více informací o technikách testování lze nalézt v normě ISO/IEC/IEEE 29119-4 [@ISO29119-4] a v [@beizer1990software], [@craig2002systematic], [@copeland2004practitioner], [@vroon2013tmap], [@jorgensen2014software], [@ammann2016introduction], [@forgacs2019practical].

V těchto učebních osnovách jsou popsány techniky testování černé skříňky, testování bílé skříňky a testování založené na zkušenostech.

**Techniky testování černé skříňky** (známé také jako techniky založené na specifikacích) jsou založeny na analýze specifikovaného chování testovaného objektu bez informací o jeho vnitřní struktuře. Testovací případy jsou tedy nezávislé na tom, jak je software napsán. V důsledku toho platí, že pokud se implementace kódu změní, ale požadované chování zůstane stejné, lze testovací případy stále používat.

**Testovací techniky bílé skříňky** (známé také jako techniky založené na struktuře) jsou založeny na analýze vnitřní struktury a způsobu zpracování uvnitř testovaného objektu. Vzhledem k tomu, že testovací případy jsou závislé na návrhu daného softwaru, mohou být vytvořeny pouze po ukončení návrhu nebo implementaci testovaného objektu (pokud není použita technika, která to umožňuje, např. TDD).

**Techniky testování založené na zkušenostech** využívají znalosti a zkušenosti testerů pro návrh a implementaci testovacích případů. Efektivita těchto technik silně závisí na dovednostech testerů. Techniky testování založené na zkušenostech mohou odhalit defekty, které techniky testování černé a bílé skříňky neodhalí. Lze tedy říct, že techniky testování založené na zkušenostech jsou doplňkem technik testování černé a bílé skříňky.

## Techniky testování černé skříňky {#black-box-testing-techniques}
Běžně používané techniky testování černé skříňky jsou popsány v následujících kapitolách:

* rozdělení tříd ekvivalence,
* analýza hraničních hodnot,
* testování dle rozhodovací tabulky,
* testování přechodů stavů.

### Rozdělení tříd ekvivalence
Rozdělení tříd ekvivalence (EP – equivalence partitioning) je technika testování rozdělující data do tříd (označováných jako třídy ekvivalence), u kterých lze očekávat stejný způsob zpracování testovaným objektem. Teorie stojící za touto technikou spočívá v tom, že pokud testovací případ detekuje defekt pro jednu hodnotu z třídy ekvivalence, měl by tento případ odhalit defekt i pro jakoukoli jinou hodnotu téže třídy. Proto stačí jeden test pro každou třídu.

Třídu ekvivalence lze identifikovat pro libovolný datový element související s testovaným objektem jako jsou např. vstupy, výstupy, konfigurační položky, interní hodnoty, hodnoty související s časem nebo parametry rozhraní. Třídy mohou být spojité nebo diskrétní, uspořádané nebo neuspořádané, konečné nebo nekonečné. Třídy se nesmí překrývat a musí se jednat o neprázdné množiny.

Pro jednoduché testované objekty může být aplikace této techniky snadná, ale v praxi je pochopení toho, jak bude testovaný objekt reagovat s různými hodnotami, často komplikované. Proto by se rozdělení do tříd mělo provádět uvážlivě.

Třída ekvivalence, která obsahuje platné hodnoty, se nazývá platná třída ekvivalence. Třída ekvivalence, která obsahuje neplatné hodnoty, se nazývá neplatná třída ekvivalence. Definice platných a neplatných hodnot se mohou v praxi výrazně lišit v závislosti na tom, jaké týmy a jaké organizace s nimi pracují. Například platné hodnoty mohou být interpretovány jako ty, které by měly být zpracovány testovaným objektem, nebo jako ty, pro které specifikacávere definuje jejich zpracování. Neplatné hodnoty mohou být interpretovány jako ty, které by měly být ignorovány nebo odmítnuty testovaným objektem, nebo jako ty, pro které není ve specifikaci testovaného objektu definováno žádné zpracování.

V EP jsou položkami pokrytí samotné třídy ekvivalence. Pro dosažení 100% pokrytí musí testovací případy pokrývat všechny identifikované třídy ekvivalence (včetně neplatných), a to použitím minimálně jedné hodnoty z každé třídy. Pokrytí je měřeno jako poměr počtu tříd otestovaných alespoň jedním testovacím případem k celkovému počtu identifikovaných tříd (obvykle vyjádřeno v procentech).

Mnoho testovaných objektů obsahuje více množin tříd ekvivalence (např. testované objekty s více vstupními parametry). V tomto případě může jeden testovací případ pokrývat třídy z různých množin tříd. Nejjednodušším kritériem pokrytí v takových případech je tzv. pokrytí každé volby (viz [@ammann2016introduction]). Toto kritérium vyžaduje, aby testovací případy pokryly každou třídu z každé množiny tříd alespoň jednou a zároveň nebere v úvahu kombinace tříd.

### Analýza hraničních hodnot 
Analýza hraničních hodnot (BVA – boundary value analysis) je technika založená na pokrytí okrajových hodnot tříd ekvivalencí. Proto ji lze použít pouze pro uspořádané (seřazené) třídy, kdy minimální a maximální hodnoty každé třídy jsou její hraniční hodnoty. Pro tuto techniku platí, že pokud dva prvky patří do stejné třídy, musí do této třídy patřit také všechny prvky ležící mezi nimi.

BVA se zaměřuje na hraniční hodnoty tříd, protože pravděpodobnost, že vývojáři udělají chybu právě na těchto hranicích, je vyšší. Typické defekty zjištěné technikou BVA se nacházejí v těch oblastech, kde jsou implementované (skutečné) hranice přesunuty na pozice nad nebo pod jejich specifikovanými (předpokládanými) hodnotami, případně kde jsou zcela vynechány.

Tyto učební osnovy se zabývají dvěma variantami: 2-hodnotová a 3-hodnotová BVA. Tyto dvě varianty se liší v počtu položek pokrytí v dané hranici nutných k dosažení 100% pokrytí.

V případě 2-hodnotové BVA [@craig2002systematic], [@myers2011art] existují pro každou hranici dvě položky pokrytí: hraniční hodnota a její nejbližší soused patřící do sousední třídy. Pro dosažení 100% pokrytí s touto variantou musí být testovací případy vykonány pro všechny položky pokrytí (tj. pro všechny identifikované hraniční hodnoty). Pokrytí se měří jako poměr počtu hraničních hodnot pokrytých testovacími případy k celkovému počtu identifikovaných hraničních hodnot (vyjádřeno v procentech).

V případě 3-hodnotové BVA [@vroon2013tmap], [@oregan2019concise] existují pro každou hranici tři položky pokrytí: hraniční hodnota a oba její sousedé. U této varianty se může stát, že některé položky pokrytí nemusí být hraničními hodnotami žádné třídy. Pro dosažení 100% pokrytí s touto variantou musí být testovací případy vykonány pro všechny položky pokrytí, tj. pro identifikované hraniční hodnoty i pro všechny jejich sousedy. Pokrytí se měří jako poměr součtu hraničních a jejích sousedních hodnot pokrytých testovacími případy k celkovému součtu identifikovaných hraničních hodnot a jejích sousedů (obvykle vyjádřeno v procentech).

3-hodnotová BVA je „přísnější" než 2-hodnotová BVA, s její pomocí lze odhalit defekty, které by mohly být s použitím 2-hodnotové BVA přehlédnuty. Pokud je např. podmínka "IF (x ≤ 10) ..." nesprávně implementována jako "IF (x = 10) ...", žádný z testovacích případů vytvořených pomocí 2-hodnotové BVA (x = 10, x = 11) nemůže tuto chybnou implementaci (a následný defekt) odhalit. Testovací případ x = 9 odvozený pomocí 3-hodnotové BVA tuto chybu pravděpodobně odhalí.

### Testování dle rozhodovací tabulky
Rozhodovací tabulky jsou vhodné pro testování implementace systémových požadavků definujících, jakým způsobem vedou různé kombinace podmínek k různým výsledkům. Představují efektivní způsob zaznamenávání složité logiky jako jsou například byznysová pravidla.

Při vytváření rozhodovacích tabulek se určí podmínky a výsledné akce systému, které tvoří dvě skupiny řádků tabulky. Každý sloupec odpovídá jednomu pravidlu rozhodování, které definuje jedinečnou kombinaci podmínek vedoucí k provedení akcí spojených s tímto pravidlem. V rozhodovacích tabulkách s omezeným počtem vstupů (limited-entry decision table) jsou všechny hodnoty podmínek a akcí (s výjimkou irelevantních nebo neproveditelných hodnot, viz níže) zobrazeny jako logické hodnoty (pravda / true nebo nepravda / false).
V rozhodovacích tabulkách s rozšířeným počtem vstupů (extended-entry decision table) mohou některé (nebo všechny) podmínky a akce také zpracovávat více hodnot (např. rozsahy hodnot, třídy ekvivalence, diskrétní hodnoty).

Symboly používané v rozhodovacích tabulkách pro podmínky jsou následující:

* „T" (true) – podmínka je splněna,
* „F" (false) – podmínka není splněna,
* „–" znamená, že hodnota podmínky je pro výsledek akce (výstup) irelevantní,
* „N/A" – podmínka je pro dané pravidlo neproveditelná.

Zápis akcí (výstupů) je následující:

* „X" – akce by měla nastat,
* „" (prázdná hodnota) – akce by neměla nastat.

Lze samozřejmě použít i jiné notace.

Úplná rozhodovací tabulka obsahuje takový počet sloupců, aby došlo k pokrytí každé kombinace podmínek. Tabulku lze zjednodušit odstraněním sloupců obsahujících neproveditelnou kombinaci podmínek nebo také sloučením sloupců, jejichž hodnoty nemají vliv na výsledek. Popis těchto algoritmů je ale nad rámec těchto osnov.

U rozhodovacích tabulek jsou položkami pokrytí sloupce obsahující proveditelnou kombinaci podmínek. Pro dosažení 100% pokrytí touto technikou musí testovací případy pokrýt všechny takové sloupce. Pokrytí se měří jako poměr počtu pokrytých sloupců k celkovému počtu proveditelných sloupců (obvykle vyjádřeno v procentech).

Význam testování dle rozhodovací tabulky spočívá v tom, že poskytuje systematický přístup k identifikaci všech kombinací podmínek, z nichž některé by jinak mohly být přehlédnuty. Pomáhá také při odhalování případných nedostatků v požadavcích.

V případě, že existuje mnoho podmínek, může být prověřování všech rozhodovacích pravidel časově náročné, protože počet pravidel roste exponenciálně s počtem podmínek. V takovém případě lze ke snížení počtu testovaných pravidel použít zjednodušenou rozhodovací tabulku nebo přístup založený na rizicích.

### Testování přechodů stavů
Diagram přechodů stavů modeluje chování systému zobrazením jeho možných stavů a platných přechodů mezi nimi. Přechod je iniciován výskytem události a může být doplněn o podmínku přechodu (guard condition), jejíž splnění přechod podmiňuje. Předpokládá se, že přechody jsou prováděny okamžitě a někdy mohou vést k tomu, že software provede určitou akci. Běžná syntaxe označování přechodů je „událost [podmínka přechodu] / akce". Pokud podmínky přechodů nebo akce neexistují (příp. jsou pro testery irelevantní), mohou být vynechány.

K diagramu přechodů stavů je ekvivalentní také tabulka přechodů stavů. Její řádky představují stavy a její sloupce události doplněné o podmínky přechodů (pokud existují). Jednotlivé položky tabulky (buňky) představují přechody a obsahují cílový stav spolu s podmínkami přechodů a výslednými akcemi (pokud jsou definovány). Na rozdíl od diagramu přechodů stavů zobrazuje tabulka přechodů stavů i neplatné přechody, které jsou reprezentovány prázdnými buňkami.

Testovací případ odvozený z diagramu přechodů stavů nebo z tabulky přechodů stavů je obvykle znázorněn jako série událostí vedoucí k posloupnosti změn stavů (a akcí, pokud jsou definovány). Jeden testovací případ může (a obvykle bude) pokrývat několik přechodů mezi stavy.

Existuje mnoho kritérií pokrytí pro testování přechodů stavů. Tyto učební osnovy popisují tři z nich.

Při **pokrytí všech stavů** jsou položkami pokrytí příslušné stavy. Aby bylo dosaženo 100% pokrytí všech stavů, musí testovací případy zajistit pokrytí všech stavů. Pokrytí se měří jako poměr počtu pokrytých stavů k celkovému počtu stavů (obvykle vyjádřeno v procentech).

Při **pokrytí platných přechodů** (nazývaném také pokrytí 0-switch) jsou položkami pokrytí jednotlivé platné přechody. Pro dosažení 100% pokrytí platných přechodů musí testovací případy pokrýt všechny platné přechody. Pokrytí se měří jako poměr počtu pokrytých platných přechodů k celkovému počtu platných přechodů (obvykle vyjádřeno v procentech).

Při **pokrytí všech přechodů** jsou položkami pokrytí všechny přechody v tabulce přechodů stavů. Pro dosažení 100% pokrytí všech přechodů musí testovací případy prověřit všechny platné přechody a pokusit se prověřit přechody neplatné (tzn. pokrýt jak platné, tak neplatné přechody). Je vhodné testovat jeden neplatný přechod v jednom testovacím případu, neboť se tak snižuje riziko tzv. maskování defektu, tj. situace, kdy není možno identifikovat defekt v důsledku výskytu jiného. Pokrytí se měří jako počet platných a neplatných přechodů, které byly nebo měly být pokryty provedenými testovacími případy, k celkovému počtu všech platných a neplatných přechodů (obvykle vyjádřeno v procentech).

Kritérium pokrytí všech stavů je „slabší" než kritérium pokrytí platných přechodů, protože může být obvykle dosaženo bez provedení všech přechodů. Nejpoužívanějším kritériem pokrytí je ale pokrytí platných přechodů, které by také mělo být minimálním požadavkem pro bezpečnostně kritický software.

Platí, že dosažení plného pokrytí platných přechodů garantuje také plné pokrytí všech stavů, dosažení plného pokrytí všech přechodů zaručuje jak plné pokrytí všech stavů, tak plné pokrytí platných přechodů.

## Techniky testování bílé skříňky {#white-box-testing-techniques}
Tato kapitola se zaměřuje na dvě nejznámější techniky testování bílé skříňky, s jejichž pomocí lze otestovat kód:

* testování příkazů,
* testování větví.

Existují samozřejmě pokročilejší techniky používané např. při testování v bezpečnostně kritických, provozně kritických a integračně kritických prostředích, kdy je cílem dosahovat vyššího stupně pokrytí. Techniky testování bílé skříňky nesouvisí výhradně s úrovní testování komponent. Existují také techniky testování bílé skříňky používané ve vyšších úrovních testování (např. při API testování) nebo dokonce techniky pro měření pokrytí nesouvisející s kódem (např. pokrytí neuronů při testování neuronových sítí). Popis všech takových technik přesahuje rámec daný těmito učebním osnovami.

### Testování a pokrytí příkazů
Při testování příkazů jsou položkami pokrytí spustitelné příkazy. Cílem je navrhovat takové testovací případy, které pokryjí příkazy v určité části kódu při definované akceptovatelné úrovni pokrytí. Pokrytí se měří jako počet spustitelných příkazů pokrytých testy k celkovému počtu spustitelných příkazů v kódu (obvykle vyjádřeno v procentech).

V případě dosažení 100% pokrytí příkazů je zajištěno, že všechny spustitelné příkazy v kódu byly otestovány alespoň jednou. To znamená, že bude spuštěn každý příkaz, který může způsobit selhání indikující výskyt defektu. Opět ale platí, že otestování příkazu pomocí testovacího případu nemusí vždy odhalit defekt, technika například nemusí detekovat defekty související s daty (např. dělení nulou, které selže pouze při nulové hodnotě dělitele). 100% pokrytí příkazů také nezaručuje, že veškerá rozhodovací logika byla otestována, protože nemusí dojít ke spuštění všech větví v kódu (viz <#section:branch-testing-and-coverage>).

### Testování a pokrytí větví {#branch-testing-and-coverage}
Větev je přenos řízení mezi dvěma uzly v grafu řídicího toku zobrazujícího možné sekvence, ve kterých jsou příkazy zdrojového kódu v testovacím objektu prováděny. Každý přenos řízení může být buď nepodmíněný (tj. lineární kód) nebo podmíněný (tj. výsledek rozhodnutí).

Při testování větví jsou položkami pokrytí větve a cílem je navrhovat testovací případy tak, aby došlo k pokrytí větví v určité části kódu při definované akceptovatelné úrovni pokrytí. Pokrytí se měří jako počet větví pokrytých testy k celkovému počtu větví (obvykle vyjádřeno v procentech).

Při dosažení 100% pokrytí větví jsou všechny nepodmíněné a podmíněné větve v kódu pokryty testovacími případy. Podmíněné větve obvykle odpovídají pravdivému nebo nepravdivému výsledku z podmínky (IF / THEN / ELSE), výsledku z vícecestné podmínky (SWITCH / CASE) nebo rozhodnutí, zda ukončit nebo pokračovat ve smyčce (FOR / NEXT, WHILE / DO, DO / WHILE, REPEAT / UNTIL). Opět ale platí, že otestování větve pomocí testovacího případu nemusí vždy odhalit defekt, například nemusí detekovat defekt vyžadující provedení určité cesty v kódu.

Pokrytí větví automaticky zaručuje pokrytí příkazů. To znamená, že jakákoliv sada testovacích případů, která dosáhne 100% pokrytí větví, dosáhne také 100% pokrytí příkazů (ale ne naopak).

### Význam testování bílé skříňky
Silnou stránkou technik bílé skříňky je, že při testování je zohledněna samotná implementace softwaru, což usnadňuje detekci defektů v případech, kdy je jeho specifikace vágní, zastaralá nebo neúplná. Slabinou je fakt, že nemusí odhalit defekty při opomenutí implementace jednoho nebo více požadavků [@watson1996structured].

Techniky bílé skříňky mohou být použity při statickém testování (např. během tzv. běhů kódu „nanečisto", dry-runs). Jsou také vhodné při revizi kódu, který ještě není připraven ke spuštění [@hetzel1988complete] stejně jako při revizi pseudokódu nebo jiného zápisu logiky vyšší nebo nižší úrovně, které mohou být modelovány pomocí grafu řídicího toku.

Pouhé testování pomocí technik černé skříňky neposkytuje informace o míře skutečného pokrytí kódu. Naopak výsledky testování s využitím technik bílé skříňky poskytují objektivní měření pokrytí a poskytují také nezbytné informace umožňující vytváření dalších testů s cílem zvyšování tohoto pokrytí a tím i následné zvyšování důvěry v kód.

## Techniky testování založené na zkušenostech {#experience-based-testing-techniques}
Nejznámější používané techniky testování založené na zkušenostech popsány v následujících kapitolách jsou:

* odhadování chyb,
* průzkumné testování,
* testování založené na kontrolním seznamu.

### Odhadování chyb
Odhadování chyb je technika používaná k předvídání výskytu chyb, defektů a selhání, která je založená na znalostech testerů jako jsou např.:

* jak fungovala aplikace v minulosti,
* typické vývojářské chyby a typické defekty, které jsou důsledkem těchto chyb,
* typická selhání, která nastala v jiných (podobných) aplikacích.

Obecně platí, že chyby, defekty a selhání mohou souviset se vstupem (např. nebyl akceptován správný vstup, parametry byly chybně nastaveny nebo úplně chyběly), výstupem (např. chybný formát nebo výsledek), logikou (např. chybějící ošetření některých případů v příkazu switch/case, chybný operátor), výpočtem (např. nesprávný operand, chybný výpočet), rozhraními (např. nesoulad parametrů, nekompatibilní typy) nebo daty (např. nesprávná inicializace, chybný typ).

Známým metodickým přístupem k implementaci odhadování chyb je útok na vady (fault attack). Při této technice je nutné, aby testeři vytvořili nebo získali seznam možných chyb, defektů a selhání a navrhli takové testy, které je identifikují, odhalí nebo způsobí. Tyto seznamy lze sestavit na základě zkušeností, údajů o defektech a selháních nebo z obecných znalostí o důvodech selhávání softwaru.

Více informací o těchto technikách viz Whittaker 2002, Whittaker 2003 a Andrews 2006.

### Průzkumné testování
Při průzkumném testování jsou testy současně navrhovány, prováděny a vyhodnocovány, zatímco testeři získávají znalosti o testovaném objektu. Testování se (mimo jiné) používá k získání dalších informací o testovaném objektu, k jeho hlubšímu prozkoumání pomocí cílených testů a k vytvoření testů pro dosud neotestované oblasti.

Průzkumné testování se někdy provádí pomocí tzv. testování v relacích s cílem lépe strukturovat testování, kdy se definuje časový rámec pro test. Jako vstup pro řízení celého testu používají testeři tzv. testovací listinu (test charter) s definicí cílů testování. Po testovací relaci obvykle následuje tzv. debriefing s diskusí testerů a zúčastněných stran, které se zajímají o výsledky testovací relace.

Obecnými testovacími podmínkami mohou být při průzkumném testování cíle testování. Jednotlivé položky pokrytí jsou identifikovány a prověřovány během testovací relací a testeři mohou používat dokumenty testovací relace (v test session sheets) pro záznam prováděných kroků a objevených zjištění.

Průzkumné testování je nejvíce užitečné v případech, kdy je specifikace nedostatečná nebo úplně chybí, taktéž je vhodnou metodou v případě výrazného časové tlaku na testování. Je také užitečné jako doplněk jiných (formálnějších) testovacích technik. Obecně bude účinnější v případech, kdy jsou testeři zkušení, mají znalosti z dané domény a vysokou úroveň základních dovedností jako jsou analytické schopnosti, zvídavost a kreativita (viz <#section:general-skills-needed-for-testing>).

Průzkumné testování může využívat i jiné testovací techniky (např. rozdělení tříd ekvivalence). Více informací o průzkumném testování viz [@kaner1999testing], [@whittaker2003break] a [@hendrickson2013explore].

### Testování založené na kontrolních seznamech

Při testování založeném na kontrolních seznamech testeři navrhují, implementují a provádí testy za účelem pokrytí testovacích podmínek uvedených v kontrolním seznamu. Kontrolní seznamy lze vytvářet na základě zkušeností, znalostí o tom, co je pro uživatele důležité, nebo na základě pochopení, proč a jak software selhává. Kontrolní seznamy by neměly obsahovat položky, které lze zkontrolovat automaticky, položky, které jsou vhodnější jako vstupní či výstupní kritéria, nebo položky, které jsou příliš obecné [@brykczynski1999survey].

Položky kontrolního seznamu jsou často formulovány ve formě otázky. Každou položku by mělo být možné přímo ověřit, a to odděleně (nezávisle na ostatních položkách). Položky kontrolního seznamu se mohou týkat požadavků, vlastností grafického rozhraní (UI), kvalitativních charakteristik nebo jiných forem testovacích podmínek. Kontrolní seznamy mohou být taktéž vytvořeny jako podpora různých typů testů včetně funkcionálního a nefunkcionálního testování (např. 10 principů testování použitelnosti, viz [@nielsen1994enhancing]).

Některé položky kontrolního seznamu mohou být časem méně efektivní, protože vývojáři se postupně učí a neopakují určitý typ chyb. Kontrolní seznamy by proto měly být pravidelně aktualizovány na základě analýzy defektů, typicky je možné do nich přidávat nové položky reflektující výskyt nově zjištěných defektů s vysokou závažností. Je však třeba dbát na to, aby se kontrolní seznam nestal příliš dlouhým [@gawande2011checklist].

V případech absence testovacích případů může testování založené na kontrolních seznamech poskytnout návod pro testování a zajistit určitý stupeň konzistence. Jelikož se jedná o obecné seznamy (high-level sheets), je pravděpodobné, že se v takovém testování může objevit určitá variabilita. To může přispět k většímu pokrytí, ale také k menší míře opakovatelnosti testování.

## Přístupy k testování založené na spolupráci {#collaborative-testing-approaches}
Každá z výše uvedených technik (viz <#section:black-box-testing-techniques>, <#section:white-box-testing-techniques>, <#section:experience-based-testing-techniques>) má svůj specifický cíl ve vztahu k identifikaci defektů. Přístupy založené na spolupráci využívají odlišné principy a jsou zaměřeny spíše na prevenci výskytu defektů využitím spolupráce a komunikace.

### Společné psaní uživatelských scénářů {#co-writing-user-scenarios}
Uživatelský scénář (user story) představuje užitnou vlastnost (feature), která má pro uživatele nebo pro budoucího majitele softwaru / systému určitou hodnotu. Uživatelské scénáře obsahují tři důležité části (viz [@jeffries2001extreme]) nazývané dohromady „3C":

* **karta** (card) – médium popisující uživatelský scénář (např. barevné štítky na tabuli nebo digitální karta v online systému),
* **konverzace** (conversation) – vysvětlení, jak bude software používán (může být dokumentována nebo být pouze verbální),
* **potvrzení** (confirmation) – ve formě akceptačního kritéria (viz <#section:acceptance-criteria>).

Nejběžnějším formátem uživatelského scénáře je formule „Jako [ROLE] chci, aby [CÍL, který má být splněn], protože [výsledná byznysová HODNOTA pro roli]" doplněná akceptačními kritérii.

Společné autorství uživatelského scénáře může využívat techniky jako je brainstorming nebo tvorba myšlenkových map (mind mapping). Spolupráce umožňuje týmu získat společnou vizi toho, čeho by mělo být dosaženo s přihlédnutím ke třem aspektům (byznys, vývoj, testování).

Správné uživatelské scénáře by měly být tzv. INVEST: nezávislé (Independent), schůdné (Negotiable), hodnotné (Valuable), odhadnutelné (Estimable), malé (Small) a testovatelné (Testable). V určitých situacích se může stát, že zástupce zúčastněné strany neví, jak otestovat daný uživatelský scénář. To může znamenat, že není dostatečně jasný nebo že neodráží něco, co je pro zúčastněné strany cenné, případně že pouze potřebují pomoc při testování [@wake2003invest].

### Akceptační kritéria {#acceptance-criteria}
Akceptační kritéria pro uživatelský scénář jsou podmínky, které musí jeho implementace splňovat, aby byla přijata zúčastněnými stranami. Z tohoto hlediska lze na ně pohlížet jako na testovací podmínky, které by měly testy prověřit. Akceptační kritéria jsou obvykle výsledkem konverzace (viz <#section:co-writing-user-scenarios>).

Akceptační kritéria se používají k:

* definování rozsahu uživatelského scénáře,
* dosažení shody mezi zúčastněnými stranami,
* popisu pozitivních i negativních scénářů,
* základní definici akceptačního testování uživatelského scénáře (viz <#section:atdd>),
* přesnějšímu plánování a odhadování testování.

Existuje několik způsobů, jak napsat akceptační kritéria pro uživatelský scénář. Dva nejběžnější formáty jsou:

* orientovaný na scénáře (např. formát Given/When/Then používaný v BDD, viz <#section:test-driven-software-development>),
* orientovaný na pravidla (např. verifikační seznam s odrážkami nebo tabulka s mapováním vstupů a výstupů).

Ačkoliv lze většinu akceptačních kritérií dokumentovat v jednom z těchto dvou formátů, může tým použít libovolný jiný (i vlastní) formát za předpokladu, že jsou akceptační kritéria dobře definovaná a jednoznačná.

### Vývoj řízený akceptačními testy (ATDD) {#atdd}
ATDD je jedním z přístupů iniciovaných testy (viz <#section:test-driven-software-development>), kdy jsou testovací případy vytvořeny před vlastní implementací uživatelského scénáře členy týmu s různými perspektivami, což jsou např. zákazníci, vývojáři a testeři (Adzic 2009). Testovací případy mohou být prováděny manuálně nebo automatizovaně.

Prvním krokem je obvykle schůzka nad specifikacemi, kde členové týmu analyzují, diskutují a dokumentují uživatelské scénáře a (pokud ještě nejsou definována) jejich akceptační kritéria. Během tohoto procesu jsou obvykle vyřešeny neúplnosti, nejednoznačnosti nebo defekty v uživatelském scénáři.

Dalším krokem je vytvoření testovacích případů, což může být provedeno jak celým týmem společně, tak pouze testery. Testovací případy jsou založeny na akceptačních kritériích a lze je považovat za příklady toho, jak by měl software pracovat, což pomůže týmu správně implementovat uživatelský scénář. Vzhledem k tomu, že příklady a testy jsou vlastně totožné, používají se oba termíny zaměnitelně. Obvykle jsou první testovací případy pozitivní a potvrzují správné chování bez výjimečných situací nebo chybových stavů, často obsahují posloupnost prováděných činností v případech, kdy vše probíhá podle očekávání. Po dokončení pozitivních testovacích případů by měl tým provést negativní testování, a nakonec pokrýt nefunkcionální kvalitativní charakteristiky (např. výkonnostní efektivita nebo použitelnost). Při návrhu testů je možné použít techniky testování popsané v kapitolách <#section:black-box-testing-techniques>,<#section:white-box-testing-techniques> a <#section:experience-based-testing-techniques.

Testovací případy by měly být vyjádřeny způsobem, který je pro zúčastněné strany srozumitelný. Obvykle obsahují věty v přirozeném jazyce zahrnující nezbytné vstupní podmínky (pre-conditions – pokud existují), vstupy a výstupní podmínky (post-conditions). Musí pokrývat všechny charakteristiky uživatelského scénáře a neměly by přesahovat jeho rámec. Žádné dva testovací případy by neměly popisovat stejné charakteristiky uživatelského scénáře.

Akceptační kritéria mohou podrobně popisovat některé aspekty popsané v uživatelském scénáři. Při zápisu ve formátu podporovaném nějakým frameworkem automatizace testování mohou vývojáři testovací případy automatizovat vytvořením podpůrného kódu již při implementaci užitné vlastnosti popsané uživatelským scénářem. V takovém případě se akceptační testy vlastně stanou spustitelnými požadavky.