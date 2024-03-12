## Přehled technik testování {#overview-of-testing-techniques}

Techniky testovania podporujú testerov pri testovacej analýze (v zmysle „čo testovať“) a pri návrhu testov (v zmysle „ako testovať“). Pomáhajú systematicky definovať relatívne malú, ale dostatočnú sadu testovacích prípadov. Techniky testovania tiež pomáhajú testerom definovať testovacie podmienky, identifikovať položky pokrytia a identifikovať testovacie dáta. Ďalšie informácie o technikách testovania a im zodpovedajúcich opatreniach možno nájsť v norme ISO/IEC/IEEE 29119-4 [@ISO29119-4] a v [@beizer1990software], [@craig2002systematic], [@copeland2004practitioner], [@vroon2013tmap], [@jorgensen2014software], [@ammann2016introduction], [@forgacs2019practical].

V týchto učebných osnovách sú techniky testovania klasifikované ako čierna skrinka, biela skrinka a založené na skúsenostiach.

**Techniky testovania čiernej skrinky** (známej tiež ako techniky založené na špecifikáciách) sú založené na analýze špecifikovaného správania testovaného objektu odkazu na jeho vnútornú štruktúru. Testovacie prípady sú teda nezávislé od toho, ako je softvér implementovaný. Ak sa teda implementácia zmení, ale požadované správanie zostane rovnaké, testovacie prípady sú stále užitočné.

**Techniky testovania bielej skrinky** (známe tiež ako techniky založené na štruktúre) sú založené na analýze vnútornej štruktúry a spôsobe spracovania testovaného objektu. Keďže testovacie prípady závisia od toho, ako je softvér navrhnutý, možno ich vytvoriť až po návrhu alebo implementácii testovacieho objektu.

**Techniky testovania založené na skúsenostiach** efektívne využívajú znalosti a skúsenosti testerov pri návrhu a implementácii testovacích prípadov. Efektivita týchto techník silne závisí od zručnosti testerov. Techniky testovania založené na skúsenostiach môžu odhaliť chyby, ktoré môžu byť prehliadnuté pomocou techník testovania čiernej skrinky a bielej skrinky. Preto techniky testovania založené na skúsenostiach dopĺňajú techniky testovania čiernej a bielej skrinky.


## Techniky testovania čiernej skrinky {#black-box-testing-techniques}
Bežne používané techniky testovania čiernej skrinky sú popísané v nasledujúcich kapitolách:

* rozdelenie na triedy ekvivalencie,
* analýza hraničných hodnôt,
* testovanie rozhodovacou tabuľkou,
* testovanie prechodov stavov.

### Rozdelenie na triedy ekvivalencie

Rozdelenie na triedy ekvivalencie (EP – equivalence partitioning) je technika testovania rozdeľujúca dáta do tried (označovaných ako triedy ekvivalencie) na základe očakávania, že všetky prvky danej triedy budú testovacím objektom spracované rovnakým spôsobom. Teória tejto techniky spočíva v tom, že ak testovací prípad, ktorý testuje jednu hodnotu z triedy ekvivalencie, odhalí defekt, tento defekt by mali odhaliť aj testovacie prípady, ktoré testujú akúkoľvek inú hodnotu z tejto istej triedy. Preto stačí jeden test pre každú triedu.

Triedy ekvivalencie je možné identifikovať pre ľubovoľný dátový element súvisiaci s testovaným objektom ako sú napr. vstupy, výstupy, konfiguračné položky, interné hodnoty, hodnoty súvisiace s časom alebo parametrami rozhrania. Triedy môžu byť spojité alebo diskrétne, usporiadané alebo neusporiadané, konečné alebo nekonečné. Triedy sa nesmú prekrývať a musia ísť o neprázdne množiny.

Pre jednoduché testované objekty môže byť aplikácia tejto techniky jednoduchá, ale v praxi je často komplikované pochopiť, ako bude testovací objekt zaobchádzať s rôznymi hodnotami. Preto by sa rozdelenie do tried malo vykonávať opatrne.

Trieda ekvivalencie, ktorá obsahuje platné hodnoty, sa nazýva platná trieda ekvivalencie. Trieda ekvivalencie, ktorá obsahuje neplatné hodnoty, sa nazýva neplatná trieda ekvivalencie. Definície platných a neplatných hodnôt sa môžu v jednotlivých tímoch a organizáciách líšiť. Napríklad platné hodnoty sa môžu interpretovať ako hodnoty, ktoré by mal testovací objekt spracovať, alebo ako hodnoty, pre ktoré špecifikácia definuje ich spracovanie. Neplatné hodnoty sa môžu interpretovať ako hodnoty, ktoré by mal testovací objekt ignorovať alebo odmietnuť, alebo ako hodnoty, pre ktoré nie je v špecifikácii testovacieho objektu definované žiadne spracovanie.

V EP sú položkami pokrytia samotné triedy ekvivalencie. Na dosiahnutie 100 % pokrytia musia testovacie prípady pokrývať všetky identifikované triedy ekvivalencie (vrátane neplatných), a to použitím minimálne jednej hodnoty z každej triedy. Pokrytie sa meria ako pomer počtu tried otestovaných aspoň jedným testovacím prípadom  
k celkovému počtu identifikovaných tried (obvykle vyjadrené v percentách).

Mnohé testovacie objekty obsahujú viacero množín tried ekvivalencie (napr. testované objekty s viacerými vstupnými parametrami). V tomto prípade môže jeden testovací prípad pokrývať triedy z rôznych množín tried. Najjednoduchším kritériom pokrytia v takýchto prípadoch je tzv. pokrytie každej voľby (pozri [@ammann2016introduction]). Toto kritérium vyžaduje, aby testovacie prípady pokryli každú triedu z každej množiny tried aspoň raz a zároveň neberie do úvahy kombinácie tried.

### Analýza hraničných hodnôt

Analýza hraničných hodnôt (BVA – boundary value analysis) je technika založená na pokrytí okrajových hodnôt tried ekvivalencií. Preto ju možno použiť iba pre usporiadané (zoradené) triedy, kde minimálne a maximálne hodnoty každej triedy sú jej hraničné hodnoty. Pre túto techniku ​​platí, že pokiaľ dva prvky patria do rovnakej triedy, všetky prvky medzi nimi musia tiež patriť do tejto triedy.

BVA sa zameriava na hraničné hodnoty tried, pretože vývojári sa pri týchto hraničných hodnotách častejšie dopúšťajú chýb. Typické defekty zistené technikou BVA sa nachádzajú v tých oblastiach, kde sú implementované (skutočné) hranice nesprávne presunuté na pozície nad alebo pod ich špecifikovanými (predpokladanými) hodnotami, prípadne kde sú úplne vynechané.

Tieto učebné osnovy sa zaoberajú dvoma variantmi: 2-hodnotová a 3-hodnotová BVA. Tieto dva varianty sa líšia  
v počte položiek pokrytia na danej hranici, potrebných na dosiahnutie 100% pokrytia.

V prípade 2-hodnotovej BVA [@craig2002systematic], [@myers2011art] existujú pre každú hranicu dve položky pokrytia: hraničná hodnota a jej najbližší sused patriaci do susednej triedy. Na dosiahnutie 100 % pokrytia s týmto variantom musia byť testovacie prípady vykonané pre všetky položky pokrytia (t.j. pre všetky identifikované hraničné hodnoty). Pokrytie sa meria ako pomer počtu vykonaných hraničných hodnôt k celkovému počtu identifikovaných hraničných hodnôt (obvykle vyjadrené v percentách).

V trojhodnotovom BVA [@vroon2013tmap], [@oregan2019concise] sú pre každú hraničnú hodnotu tri položky pokrytia: táto hraničná hodnota a obe jej susedné hodnoty. Preto v 3-hodnotovej BVA niektoré z položiek pokrytia nemusia byť hraničnými hodnotami. Na dosiahnutie 100 % pokrytia s týmto variantom musia byť testovacie prípady vykonané pre všetky položky pokrytia, t.j. pre identifikované hraničné hodnoty aj pre všetkých susedov. Pokrytie sa meria ako pomer počtu vykonaných hraničných hodnôt a ich susedných hodnôt vydelený k celkovému počtu identifikovaných hraničných hodnôt a ich susedných hodnôt (obvykle vyjadrené v percentách).

3-hodnotová BVA je „prísnejšia“ ako 2-hodnotová BVA, s jej pomocou je možné odhaliť defekty, ktoré by mohli byť  
s použitím 2-hodnotové BVA prehliadnuté. napríklad, ak je podmienka "IF (x ≤ 10) ..." nesprávne implementovaná ako "IF (x = 10) ...", žiadny z testovacích prípadov vytvorených pomocou 2-hodnotovej BVA (x = 10, x = 11) nemôže túto chybnú implementáciu (a následný defekt) odhaliť. Testovací prípad x = 9 odvodený pomocou 3-hodnotovej BVA túto chybu pravdepodobne odhalí.

### Testovanie rozhodovacou tabuľkou
Rozhodovacie tabuľky sa používajú na testovanie implementácie systémových požiadaviek, ktoré špecifikujú, ako rôzne kombinácie podmienok vedú k rôznym výsledkom. Predstavujú efektívny spôsob zaznamenávania zložitej logiky ako sú napríklad biznisové pravidlá.

Pri vytváraní rozhodovacích tabuliek sa definujú podmienky a výsledné akcie systému, ktoré tvoria dve skupiny riadkov tabuľky. Každý stĺpec zodpovedá jednému pravidlu rozhodovania, ktoré definuje jedinečnú kombináciu podmienok vedúcich k vykonaniu akcií spojených s týmto pravidlom. V rozhodovacích tabuľkách s obmedzeným počtom vstupov sú všetky hodnoty podmienok a akcií (s výnimkou irelevantných alebo neuskutočniteľných hodnôt, pozri nižšie) zobrazujú ako logické hodnoty (pravda alebo nepravda).  
Alternatívne, v rozhodovacích tabuľkách s rozšíreným počtom vstupov môžu niektoré (alebo všetky) podmienky a akcie tiež nadobúdať viac hodnôt (napr. rozsahy hodnôt, triedy ekvivalencie, diskrétne hodnoty).

Zápis podmienok je nasledovný:

* „T“ (true) – podmienka je splnená,
* „F“ (false) – podmienka nie je splnená,
* „–“ znamená, že hodnota podmienky je pre výsledok akcie (výstup) irelevantná,
* „N/A“ – podmienka je pre dané pravidlo neuskutočniteľná.

Zápis akcií (výstupov) je nasledujúci:

* „X“ – akcia by mala nastať,
* „“ (prázdna hodnota) – akcia by nemala nastať.

Môžu sa použiť aj iné zápisy.

Úplná rozhodovacia tabuľka obsahuje taký počet stĺpcov, aby došlo k pokrytiu každej kombinácie podmienok. Tabuľku je možné zjednodušiť odstránením stĺpcov obsahujúcich neuskutočniteľnú kombináciu podmienok alebo tiež zlúčením stĺpcov, v ktorých niektoré podmienky neovplyvňujú výsledok, do jedného stĺpca. Popis týchto algoritmov je ale nad rámec týchto osnov.

Pri rozhodovacích tabuľkách sú položkami pokrytia stĺpce obsahujúce uskutočniteľnú kombináciu podmienok. Na dosiahnutie 100% pokrytia touto technikou musia testovacie prípady pokryť všetky takéto stĺpce. Pokrytie sa meria ako pomer počtu pokrytých stĺpcov k celkovému počtu uskutočniteľných stĺpcov (zvyčajne vyjadrené  
v percentách).

Silnou stránkou testovania rozhodovacou tabuľkou je, že poskytuje systematický prístup na identifikáciu všetkých kombinácií podmienok, z ktorých by niektoré mohli byť inak prehliadnuté. Pomáha tiež nájsť prípadné medzery alebo rozpory v požiadavkách.

Ak je podmienok veľa, môže byť preverovanie všetkých rozhodovacích pravidiel časovo náročné, pretože počet pravidiel rastie exponenciálne s počtom podmienok. V takom prípade sa na zníženie počtu pravidiel, ktoré je potrebné vykonať, môže použiť minimalizovaná rozhodovacia tabuľka alebo prístup založený na riziku.

### Testovanie prechodov stavov

Diagram prechodov stavov modeluje správanie systému zobrazením jeho možných stavov a platných prechodov medzi nimi. Prechod je iniciovaný výskytom udalosti a môže byť doplnený o podmienku prechodu, ktorej splnenie prechod podmieňuje. Predpokladá sa, že prechody sú vykonávané okamžite a niekedy môžu viesť k tomu, že softvér vykoná určitú akciu. Bežná syntax označovania prechodov je „udalosť \[podmienka prechodu\] / akcie“. Pokiaľ podmienky prechodov alebo akcie neexistujú (príp. sú pre testerov irelevantné), môžu byť vynechané.

K diagramu prechodov stavov je ekvivalentná aj tabuľka prechodov stavov. Jej riadky predstavujú stavy a jej stĺpce udalosti (doplnené o podmienky prechodov ak existujú). Jednotlivé položky tabuľky (bunky) predstavujú prechody a obsahujú cieľový stav spolu s podmienkami prechodov a výslednými akciami (ak sú definované). Na rozdiel od diagramu prechodov stavov, zobrazuje tabuľka prechodov stavov aj neplatné prechody, ktoré sú reprezentované prázdnymi bunkami.

Testovací prípad odvodený z diagramu prechodov stavov alebo z tabuľky prechodov stavov je obvykle znázornený ako séria udalostí vedúcich k postupnosti zmien stavov (a akcií, ak sú definované). Jeden testovací prípad môže (a obvykle bude) pokrývať niekoľko prechodov medzi stavmi.

Existuje mnoho kritérií pokrytia pre testovanie prechodov stavov. Tieto učebné osnovy popisujú tri z nich.

Pri **pokrytí všetkých stavov** sú položkami pokrytia príslušné stavy. Aby bolo dosiahnuté 100% pokrytie všetkých stavov, musia testovacie prípady zabezpečiť pokrytie všetkých stavov. Pokrytie sa meria ako pomer počtu pokrytých stavov k celkovému počtu stavov (obvykle vyjadrené v percentách).

Pri **pokrytí platných prechodov** (nazývanom tiež pokrytie 0-switch) sú položkami pokrytia jednotlivé platné prechody. Na dosiahnutie 100 % pokrytia platných prechodov musia testovacie prípady pokryť všetky platné prechody. Pokrytie sa meria ako pomer počtu pokrytých platných prechodov k celkovému počtu platných prechodov (obvykle vyjadrené v percentách).

Pri **pokrytí všetkých prechodov** sú položkami pokrytia všetky prechody v tabuľke prechodov stavov. Na dosiahnutie 100% pokrytia všetkých prechodov musia testovacie prípady preveriť všetky platné prechody a pokúsiť sa preveriť prechody neplatné (tzn. pokryť ako platné, tak neplatné prechody). Testovanie iba jedného neplatného prechodu  
v jednom testovacom prípade pomáha vyhnúť sa maskovaniu chýb, t. j. situácii, keď jedna chyba bráni odhaleniu inej. Pokrytie sa meria ako pomer počtu platných a neplatných prechodov, ktoré boli alebo mali byť pokryté vykonanými testovacími prípadmi, k celkovému počtu všetkých platných a neplatných prechodov (obvykle vyjadrené v percentách).

Kritérium pokrytia všetkých stavov je „slabšie“ ako kritérium pokrytia platných prechodov, pretože môže byť obvykle dosiahnuté bez vykonania všetkých prechodov. Najpoužívanejším kritériom pokrytia je ale pokrytie platných prechodov, ktoré by tiež malo byť minimálnou požiadavkou pre bezpečnostne kritický softvér.

Platí, že dosiahnutie plného pokrytia prechodov garantuje plné pokrytie všetkých stavov a všetkých platných prechodov.

## Techniky testovania bielej skrinky {#white-box-testing-techniques}

Táto kapitola sa zameriava na dve najznámejšie techniky testovania bielej skrinky, s pomocou ktorých je možné otestovať kód:

* testovanie príkazov,
* testovanie vetiev.

Existujú prísnejšie techniky, ktoré sa používajú v niektorých prostrediach kritických z hľadiska bezpečnosti (safety-critical), kritických z hľadiska použitia (mission-critical) alebo vysokej integrity (high-integrity) na dosiahnutie dôkladnejšieho pokrytia kódu. Techniky testovania bielej skrinky nesúvisia výhradne s úrovňou testovania komponentov. Existujú aj techniky testovania bielej skrinky používané vo vyšších úrovniach testovania (napr. pri API testovaní) alebo využívajú pokrytie, ktoré nesúvisí s kódom (napr. pokrytie neurónov pri testovaní neurónových sietí). Tieto techniky nie sú v týchto učebných osnovách rozoberané.

### Testovanie a pokrytie príkazov

Pri testovaní príkazov sú položkami pokrytia spustiteľné príkazy. Cieľom je navrhovať také testovacie prípady, ktoré pokryjú príkazy v kóde, kým sa nedosiahne akceptovateľná úroveň pokrytia. Pokrytie sa meria ako pomer počtu spustiteľných príkazov pokrytých testami k celkovému počtu spustiteľných príkazov v kóde (obvykle vyjadrené  
v percentách).

Ak sa dosiahne 100 % pokrytie príkazov, zabezpečí sa, že všetky vykonateľné príkazy v kóde boli vykonané aspoň raz. To znamená, že bude spustený každý príkaz, ktorý môže spôsobiť zlyhanie indikujúce výskyt defektu. Opäť ale platí, že otestovanie príkazu pomocou testovacieho prípadu nemusí vždy odhaliť defekt, technika napríklad nemusí odhaliť defekty súvisiace s dátami (napr. delenie nulou, ktoré zlyhá iba pri nulovej hodnote deliteľa). Takisto 100% pokrytie príkazov nezaručuje, že všetka rozhodovacia logika bola otestovaná, pretože nemusí dôjsť k spusteniu všetkých vetiev v kóde (pozri <#section:branch-testing-and-coverage>).

### Testovanie a pokrytie vetiev {#branch-testing-and-coverage}

Vetva je prenos riadenia medzi dvoma uzlami v grafe riadiaceho toku zobrazujúceho možné sekvencie, v ktorých sú príkazy zdrojového kódu v testovacom objekte vykonávané. Každý prenos riadenia môže byť buď nepodmienený (t.j. lineárny kód) alebo podmienený (t.j. výsledok rozhodnutia).

Pri testovaní vetiev sú položkami pokrytia vetvy a cieľom je navrhovať testovacie prípady tak, aby došlo k pokrytiu vetiev v kóde, kým sa nedosiahne akceptovateľná úroveň pokrytia. Pokrytie sa meria ako pomer počtu vetiev pokrytých testami k celkovému počtu vetiev (obvykle vyjadrené v percentách).

Pri dosiahnutí 100% pokrytia vetiev sú všetky nepodmienené a podmienené vetvy v kóde pokryté testovacími prípadmi. Podmienené vetvy zvyčajne zodpovedajú pravdivému alebo nepravdivému výsledku z podmienky (IF / THEN / ELSE), výsledku z viaccestnej podmienky (SWITCH / CASE) alebo rozhodnutiu, či ukončiť alebo pokračovať v slučke. Vykonávanie vetvy pomocou testovacieho prípadu však neodhalí chyby vo všetkých prípadoch. Nemusí napríklad odhaliť chyby vyžadujúce vykonanie konkrétnej cesty v kóde.

Pokrytie vetiev automaticky zaručuje pokrytie príkazov. To znamená, že akákoľvek sada testovacích prípadov, ktorá dosiahne 100% pokrytie vetiev, dosiahne tiež 100% pokrytie príkazov (ale nie naopak).

### Význam testovania bielej skrinky

Silnou stránkou techník bielej skrinky je, že pri testovaní je zohľadnená samotná implementácia softvéru, čo uľahčuje odhalenie defektov v prípadoch, keď je jeho špecifikácia vágna, zastaraná alebo neúplná. Zodpovedajúcou slabinou je, že ak softvér neimplementuje jednu alebo viacero požiadaviek, testovanie bielych skriniek nemusí odhaliť výsledné chyby z opomenutia [@watson1996structured].

Techniky bielej skrinky môžu byť použité pri statickom testovaní (napr. počas tzv. behov kódu „nanečisto“, dry-runs). Sú tiež vhodné pri revízii kódu, ktorý ešte nie je pripravený na spustenie [@hetzel1988complete] rovnako ako pri revízii pseudokódu a inej vysokoúrovňovej alebo zhora nadol orientovanej logiky, ktorú možno modelovať pomocou grafu riadiaceho toku.

Samotné testovanie pomocou techník čiernej skrinky neposkytuje informácie o miere skutočného pokrytia kódu. Naopak výsledky testovania s využitím techník bielej skrinky poskytujú objektívne meranie pokrytia a poskytujú tiež nevyhnutné informácie umožňujúce vytváranie ďalších testov s cieľom zvyšovania tohto pokrytia a tým aj následné zvyšovanie dôvery v kód.

## Techniky testovania založené na skúsenostiach {#experience-based-testing-techniques}

Bežne používané techniky testovania založené na skúsenostiach popísané v nasledujúcich kapitolách sú:

* odhadovanie chýb,
* prieskumné testovanie,
* testovanie založené na kontrolnom zozname.

### Odhadovanie chýb

Odhadovanie chýb je technika používaná na predvídanie výskytu chýb, defektov a zlyhaní, ktorá je založená na znalostiach testerov, vrátane:

* ako fungovala aplikácia v minulosti
* typy chýb, ktorých sa vývojári dopúšťajú, a typy chýb, ktoré z nich vyplývajú
* typy zlyhaní, ktoré sa vyskytli v iných podobných aplikáciách

Všeobecne platí, že chyby, defekty a zlyhania môžu súvisieť so vstupom (napr. nebol akceptovaný správny vstup, nesprávne alebo chýbajúce parametre), výstupom (napr. nesprávny formát alebo nesprávny výsledok), logikou (napr. chýbajúce prípady, nesprávny operátor), výpočtom (napr. nesprávny operand, nesprávny výpočet), rozhraniami (napr. nesúlad parametrov, nekompatibilné typy) alebo dátami (napr. nesprávna inicializácia, nesprávny typ).

Známym metodickým prístupom k implementácii odhadovania chýb je útok na vady (fault attack). Táto technika vyžaduje, aby tester vytvoril alebo získal zoznam možných chýb, defektov a zlyhaní a navrhol testy, ktoré identifikujú chyby, odhalia defekty alebo spôsobia zlyhania. Tieto zoznamy je možné zostaviť na základe skúseností, údajov o defektoch  
a zlyhaniach alebo na základe všeobecných znalostí o tom, prečo softvér zlyháva.

Viac informácií o odhadovaní chýb a útokoch na vady nájdete v [@whittaker2003break], [@whittaker2009exploratory], [@andrews2006break].

### #### Prieskumné testovanie

Pri prieskumnom testovaní sú testy súčasne navrhované, vykonávané a vyhodnocované, zatiaľ čo testeri získavajú znalosti o testovanom objekte. Testovanie sa (okrem iného) používa k získaniu ďalších informácií  
o testovanom objekte, na jeho hlbšie preskúmanie pomocou cielených testov a na vytvorenie testov pre netestované oblasti.

Prieskumné testovanie sa niekedy vykonáva pomocou tzv. testovania v sedeniach, ktoré pomáhajú štruktúrovať testovanie. Testovanie sa vykonáva v rámci definovaného časového rámca. Tester používa testovaciu listinu obsahujúcu ciele testovania, ktorou sa testovanie riadi. Po testovacej relácii obvykle nasleduje tzv. debriefing s diskusiou medzi testerom  
a zainteresovanými stranami, ktoré sa zaujímajú o výsledky testovacieho sedenia.

Všeobecnými testovacími podmienkami môžu byť pri prieskumnom testovaní ciele testovania. Jednotlivé položky pokrytia sú identifikované a preverované počas testovacieho sedenia a testeri môžu používať dokumenty pre testovacie sedenie (test session sheets) pre zdokumentovanie vykonávaných krokov a nových zistení.

Prieskumné testovanie je najviac užitočné v prípadoch, keď je špecifikácia nedostatočná alebo úplne chýba, taktiež je vhodnou metódou v prípade výrazného časového tlaku na testovanie. Je tiež užitočné ako doplnok iných (formálnejších) testovacích techník. Všeobecne bude efektívnejšie v prípadoch, keď sú testeri skúsení, majú znalosti  
z danej domény a vysokú úroveň základných zručností ako sú analytické schopnosti, zvedavosť a kreativita (pozri <#section:general-skills-needed-for-testing>).

Prieskumné testovanie môže využívať aj iné testovacie techniky (napr. rozdelenie tried ekvivalencie). Viac informácií o prieskumnom testovaní, pozri [@kaner1999testing], [@whittaker2003break] a [@hendrickson2013explore].

### Testovanie založené na kontrolných zoznamoch

Pri testovaní založenom na kontrolných zoznamoch tester navrhuje, implementuje a vykonáva testy, ktoré pokrývajú testovacie podmienky z kontrolného zoznamu. Kontrolné zoznamy môžu byť zostavené na základe skúseností, poznatkov o tom, čo je dôležité pre používateľa, alebo na základe pochopenia toho, prečo a ako softvér zlyháva. Kontrolné zoznamy by nemali obsahovať položky, ktoré sa dajú skontrolovať automaticky, položky, ktoré sú vhodnejšie ako vstupné alebo výstupné kritériá, alebo položky, ktoré sú príliš všeobecné [@brykczynski1999survey].

Položky kontrolného zoznamu sú často formulované vo forme otázky. Každú položku by malo byť možné priamo skontrolovať, a to oddelene (nezávisle od ostatných položiek). Tieto položky sa môžu týkať požiadaviek, vlastností grafického rozhrania (UI), kvalitatívnych charakteristík alebo iných foriem testovacích podmienok. Kontrolné zoznamy môžu byť taktiež vytvorené ako podpora rôznych typov testovania vrátane funkcionálneho a nefunkcionálneho testovania (napr. 10 princípov testovania použiteľnosti, pozri [@nielsen1994enhancing]).

Niektoré položky kontrolného zoznamu môžu byť časom menej efektívne, pretože vývojári sa postupne naučia  
vyhýbať rovnakým chybám. Kontrolné zoznamy by preto mali byť pravidelne aktualizované na základe analýzy defektov, typicky je možné do nich pridávať nové položky reflektujúce výskyt novo zistených defektov s vysokou závažnosťou. Treba však dbať na to, aby sa kontrolný zoznam nestal príliš dlhým [@gawande2011checklist].

Pri absencii podrobných testovacích prípadov môže testovanie založené na kontrolných zoznamoch poskytnúť vodítko a určitý stupeň konzistencie pre testovanie. Keďže ide o všeobecné zoznamy (high-level sheets), je pravdepodobné, že sa v testovaní môže objaviť variabilita, čo môže mať za následok väčšie pokrytie, ale menšiu opakovateľnosť testovania.

## Prístupy k testovaniu založené na spolupráci {#collaborative-testing-approaches}

Každá z vyššie uvedených techník (pozri <#section:black-box-testing-techniques>, <#section:white-box-testing-techniques>, <#section:experience-based-testing-techniques>) má svoj špecifický cieľ vo vzťahu k identifikácii defektov. Na druhej strane prístupy založené na spolupráci sa zameriavajú aj na predchádzanie vzniku chýb prostredníctvom spolupráce a komunikácie.

### Spoločné písanie používateľských scenárov {#co-writing-user-scenarios}

Používateľský scenár (user story) predstavuje funkcionalitu (feature), ktorá má pre používateľa alebo pre budúceho majiteľa softvéru/systému určitú hodnotu. Používateľské scenáre obsahujú tri dôležité aspekty (pozri [@jeffries2001extreme]), ktoré sa spoločne nazývajú "3 C":

* **karta** (card) – médium popisujúce používateľský scenár (napr. farebné štítky alebo záznam na elektronickej tabuli v online systéme),
* **konverzácia** (conversation) – vysvetlenie, ako sa bude softvér používať (môže byť dokumentovaná alebo byť iba verbálna),
* **potvrdenie** (confirmation) – vo forme akceptačného kritéria (pozri <#section:acceptance-criteria>).

Najbežnejším formátom používateľského scenára je formula „Ako \[ROLA\] chcem, aby \[CIEĽ, ktorý má byť splnený\], pretože \[výsledná biznisová HODNOTA pre rolu\]" doplnená akceptačnými kritériami.

Spoločné autorstvo používateľského scenára môže využívať techniky ako je brainstorming alebo tvorba myšlienkových máp (mind mapping). Spolupráca umožňuje tímu získať spoločnú víziu toho, čo by sa malo dodať, zohľadnením troch perspektív: (biznis, vývoj, testovanie).

Správne používateľské scenáre by mali byť tzv. INVEST: nezávislé (Independent), schodné (Negotiable), hodnotné (Valuable), odhadnuteľné (Estimable), malé (Small) a testovateľné (Testable). Ak zainteresovaná strana nevie, ako testovať používateľský scenár, môže to znamenať, že používateľský scenár nie je dostatočne jasný alebo že nevyjadruje niečo, čo je pre ňu hodnotné, alebo že zainteresovaná strana jednoducho potrebuje pomoc pri testovaní [@wake2003invest].

### Akceptačné kritériá {#acceptance-criteria}

Akceptačné kritériá pre používateľský scenár sú podmienky, ktoré musí jeho implementácia spĺňať, aby bola akceptovaná zainteresovanými stranami. Z tohto hľadiska je možné na ne pozerať ako na testovacie podmienky, ktoré by mali testy preveriť. Akceptačné kritériá sú zvyčajne výsledkom konverzácie (pozri <#section:co-writing-user-scenarios>).

Akceptačné kritériá sa používajú na:

* definovanie rozsahu používateľského scenára,
* dosiahnutie zhody medzi zainteresovanými stranami,
* popis pozitívnych aj negatívnych scenárov,
* základnú definíciu akceptačného testovania používateľského scenára (pozri <#section:atdd>),
* presnejšie plánovanie a odhadovanie.

Existuje niekoľko spôsobov, ako napísať akceptačné kritériá pre používateľský scenár. Dva najbežnejšie formáty sú:

* orientovaný na scenáre (napr. formát Given/When/Then používaný v BDD, pozri <#section:test-driven-software-development>),
* orientovaný na pravidlá (napr. verifikačný zoznam s odrážkami alebo tabuľka s mapovaním vstupov a výstupov).

Väčšinu akceptačných kritérií možno zdokumentovať v jednom z týchto dvoch formátov. Tím však môže použiť aj iný, vlastný formát, pokiaľ sú akceptačné kritériá dobre definované a jednoznačné.


### Vývoj riadený akceptačnými testami (ATDD) {#atdd}

ATDD je jeden z prístupov iniciovaných testami (test-first) (pozri <#section:test-driven-software-development>), kedy sú testovacie prípady vytvorené pred vlastnou implementáciou používateľského scenára členmi tímu s rôznymi perspektívami pohľadu, ako napr. zákazníci, vývojári a testeri [@adzic2009bridging]. Testovacie prípady sa môžu vykonávať manuálne alebo automatizovane.

Prvým krokom je obvykle schôdzka nad špecifikáciami, kde členovia tímu analyzujú, diskutujú a dokumentujú používateľské scenáre a (ak ešte nie sú definované) ich akceptačné kritériá. Počas tohto procesu sú obvykle vyriešené neúplnosti, nejednoznačnosti alebo defekty v používateľskom scenári.

Ďalším krokom je vytvorenie testovacích prípadov. Môže to urobiť tím ako celok alebo tester individuálne. Testovacie prípady sú založené na akceptačných kritériách a možno ich považovať za príklady toho, ako by mal softvér pracovať, čo pomôže tímu správne implementovať používateľský scenár. Keďže príklady a testy sú rovnaké, tieto pojmy sú zameniteľné. Prvé testovacie prípady sú zvyčajne pozitívne, potvrdzujú správne chovanie bez výnimiek alebo chybových stavov a obsahujú postupnosť vykonávaných činností v prípadoch, keď všetko prebieha podľa očakávania. Po dokončení pozitívnych testovacích prípadov by mal tím vykonať negatívne testovanie a nakoniec pokryť nefunkcionálne charakteristiky kvality (napr. výkonnostná efektivita alebo použiteľnosť). Pri návrhu testov je možné použiť techniky testovania popísané  
v kapitolách <#section:black-box-testing-techniques>, <#section:white-box-testing-techniques> a <#section:experience-based-testing-techniques>.

Testovacie prípady by mali byť vyjadrené spôsobom, ktorý je pre zainteresované strany zrozumiteľný. Obvykle obsahujú vety v prirodzenom jazyku zahŕňajúce nevyhnutné vstupné podmienky (pre-conditions – ak existujú), vstupy a výstupné podmienky (post-conditions). Musia pokrývať všetky charakteristiky používateľského scenára a nemali by presahovať jeho rámec. Žiadne dva testovacie prípady by nemali popisovať rovnaké charakteristiky používateľského scenára.

Akceptačné kritériá môžu podrobne popisovať niektoré aspekty popísané v používateľskom scenári. Ak sú zachytené vo formáte podporovanom nejakým frameworkom na automatizáciu testov, vývojári môžu automatizovať testovacie prípady písaním podporného kódu pri implementácii funkcionality opísanej v používateľskom scenári. V takom prípade sa akceptačné testy vlastne stanú vykonateľnými požiadavkami.