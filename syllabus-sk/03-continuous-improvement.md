## Základy statického testovania

Na rozdiel od dynamického testovania nie je pri statickom testovaní nutné testovaný softvér spúšťať. Kód, špecifikácia procesu, špecifikácia architektúry systému alebo iné pracovné produkty sú hodnotené a preverované buď manuálne (napr. revíziami) alebo pomocou nástroja (napr. statická analýza). Medzi ciele testovania patrí zlepšovanie kvality, odhaľovanie defektov a posudzovanie vlastností ako je čitateľnosť, úplnosť, správnosť, testovateľnosť a konzistencia. Statické testovanie je možné používať ako na verifikáciu, tak na validáciu.

Testeri, zástupcovia biznisu a vývojári počas popisu príkladov (napr. pri využití techniky špecifikácie pomocou príkladov), písaní používateľských scenárov a spresňovaní backlogu (backlog refinement) spolupracujú tak, aby používateľské scenáre a súvisiace pracovné produkty spĺňali definované kritériá, napr. definície pripravenosti (Definition of Ready) (pozri <#section:entry-and-exit-criteria>). Techniky revízií možno použiť na zabezpečenie toho, aby používateľské scenáre boli úplné a zrozumiteľné a obsahovali testovateľné akceptačné kritériá. Tým, že testeri kladú správne otázky vlastne skúmajú, konfrontujú a pomáhajú vylepšovať navrhované používateľské scenáre.

Statická analýza môže upozorniť na problémy ešte pred vykonaním dynamického testovania, pričom často vyžaduje menšie úsilie – nevyžaduje totiž tvorbu testovacích prípadov a je možné u nej využiť rôzne nástroje (pozri <#section:test-tools>). Statická analýza je často začlenená do nástrojov priebežnej integrácie (pozri kapitolu <#section:devops-and-testing>). Aj keď sa z veľkej časti používa na odhaľovanie špecifických defektov kódu, možno ju tiež použiť na vyhodnotenie udržovateľnosti a bezpečnosti (security). Ďalšími príkladmi nástrojov statickej analýzy sú nástroje na kontrolu pravopisu a čitateľnosti.

### Pracovné produkty, ktoré môžu byť preverené statickým testovaním

Takmer každý pracovný produkt môže byť preskúmaný pomocou statického testovania. Medzi také produkty patria napríklad špecifikácie požiadaviek, zdrojový kód, plány testovania, testovacie prípady, položky produktového backlogu, testovacie listiny, projektová dokumentácia, zmluvy alebo modely.

**Revíziu** je možné použiť na akýkoľvek pracovný produkt, ktorý je možné prečítať a porozumieť mu.

Pre **statickú analýzu** je nutné, aby mali skúmané pracovné produkty formálnu štruktúru, voči ktorej môžu byť kontrolované (napr. modely, kód alebo text s formálnou syntaxou).

Pracovné produkty, ktoré nie sú vhodné na statické testovanie, sú obvykle tie, ktoré sú ťažko interpretovateľné ľuďmi a súčasne by nemali byť analyzované nástrojmi (napr. spustiteľný kód tretej strany, ktorý z právnych dôvodov nemožno analyzovať s využitím nástrojov).

### Prínosy statického testovania

Statické testovanie môže odhaliť defekty v najskorších fázach SDLC, čím napĺňa princíp včasného testovania (pozri <#section:testing-principles). Môže tiež odhaliť defekty, ktoré nemožno zistiť dynamickým testovaním (napr. nedosiahnuteľný kód, chybne implementované návrhové vzory, defekty v nespustiteľných pracovných produktoch).

Statické testovanie vytvára dôveru v dané pracovné produkty a umožňuje vyhodnotiť ich kvalitu. Verifikáciou zdokumentovaných požiadaviek môžu zainteresované strany tiež zabezpečiť, že tieto požiadavky odrážajú ich skutočné potreby. Vzhľadom na to, že statické testovanie môže byť vykonávané v raných fázach SDLC, je možné nastaviť pravidlá jednotného chápania (napr. požiadaviek), čím sa tiež zlepší komunikácia medzi zainteresovanými stranami. Z tohto dôvodu sa odporúča zapojiť do statického testovania rôzne typy účastníkov.

Aj keď môže byť vykonanie revízií nákladné, celkové náklady na projekt sú obvykle oveľa nižšie, než keď sa revízia vôbec nevykonáva. Dôvodom je to, že neskôr v projekte nie je potrebné vynaložiť toľko času a úsilia na opravu defektov.

Niektoré defekty v kóde je možné odhaliť pomocou statickej analýzy oveľa efektívnejšie ako pri dynamickom testovaní, čo obvykle vedie k ich menšiemu počtu a tým aj nižšej celkovej náročnosti pri vývoji.

### Rozdíly mezi statickým a dynamickým testováním

Statické a dynamické testovacie postupy sa vzájomne dopĺňajú. Majú podobné ciele (napr. odhaľovanie defektov v pracovných produktoch, pozri <#section:typical-testing-objectives>), ale existujú medzi nimi aj určité rozdiely, napríklad:

* Ako statické, tak aj dynamické testovanie (vrátane analýzy zlyhania) môže viesť k odhaleniu defektu, avšak existujú niektoré typy defektov, ktoré možno nájsť buď len statickým alebo iba dynamickým testovaním.
* Statické testovanie nájde defekty priamo, zatiaľ čo dynamické testovanie hľadá zlyhanie, z ktorých sú príslušné defekty určené následnou analýzou.
* Statické testovanie môže ľahšie odhaľovať defekty ťažko dosiahnuteľné pomocou dynamického testovania alebo také, ktoré sú v kóde v častiach spúšťaných len zriedka.
* Dynamické testovanie je možné použiť iba na spustiteľné pracovné produkty, statické testovanie aj na nespustiteľné.
* Statické testovanie je možné použiť na meranie kvalitatívnych charakteristík (napr. udržovateľnosti) nezávislých na spustení kódu, dynamické testovanie iba na tie, ktoré sú na spustení kódu závislé (napr. výkonnostná fektivita).

Medzi typické defekty odhaliteľné ľahšie a lacnejšie statickým testovaním patria:

* defekty v požiadavkách (napr. nezrovnalosti, nejednoznačnosti, rozpory, opomenutia, nepresnosti a duplicity),
* defekty v návrhu (napr. neefektívne databázové štruktúry, zlá modularita),
* niektoré typy programovaích defektov (napr. premenné s nedefinovanými hodnotami, nedeklarované premenné, nedosiahnuteľný alebo duplicitný kód, nadmerná zložitosť kódu),
* odchýlky od noriem (napr. nedostatočné dodržiavanie konvencií pre programovanie),
* nesprávne špecifikácie rozhrania (napr. rozdielny počet, typ alebo poradie parametrov),
* niektoré bezpečnostné zraniteľnosti (napr. pretečenie vyrovnávacej pamäte),
* chýbajúce časti alebo nepresnosti v pokrytí testovacej bázy (napr. chýbajúce testy pre niektoré akceptačné kritérium).

## Proces spätnej väzby a revízie

### Prínosy včasnej a častej spätnej väzby od zainteresovaných strán {#benefits-early-and-frequent-feedback-from-stakeholders}

Včasná a častá spätná väzba pomáha s odhalením potenciálnych problémov s kvalitou. Pokiaľ sa zainteresované strany zapájajú do vývoja nedostatočne, vyvíjaný produkt nemusí spĺňať ich pôvodné alebo súčasné predstavy. Pokiaľ nie je tím schopný dodať to, čo zainteresovaná strana chce, hrozia neočakávané náklady na prepracovanie, zmeškaných termínov, vzájomného obviňovania, a dokonca môže dôjsť k úplnému zlyhaniu projektu.

Častá spätná väzba zainteresovaných strán počas SDLC môže zabrániť nedorozumeniam pri definícii požiadaviek a zabezpečiť, aby zmeny požiadaviek boli správne a včas pochopené a implementované. To pomáha vývojovému tímu lepšie porozumieť tomu, čo vyvíja. Umožňuje im tiež zamerať sa na tie funkcionality, ktoré prinášajú zainteresovaným stranám najvyššiu pridanú hodnotu, a ktoré majú najviac pozitívny vplyv na zistené riziká.

### Činnosti procesu revízie {#review-process-activities}

Norma ISO/IEC 20246 [@ISO20246] definuje všeobecný proces revízie a popisuje štruktúrovaný, ale flexibilný rámec, z ktorého môže byť daný proces revízie prispôsobený konkrétnej situácii. Čím vyšší je požadovaný stupeň formálnosti revízie, tým vyšší je počet úloh počas rôznych činností.

Mnohé pracovné produkty sú tak rozsiahle, že ich nemožno pokryť iba jedinou revíziou a proces revízie môže byť vykonaný opakovane.

Činnosti procesu revízie sú:

* **Plánovanie**. Počas fázy plánovania sa stanoví rozsah revízie obsahujúci definíciu účelu a revidovaného pracovného produktu, kvalitatívne charakteristiky pre vyhodnotenie, oblasti záujmu, výstupné kritériá, doplňujúce informácie (napr. normy), potrebné úsilie a časový rámec celej revízie.
* **Začatie revízie**. Počas začatia revízie je cieľom zabezpečiť, aby bolo všetko (vrátane zainteresovaných strán) pripravené na revíziu. To okrem iného vyžaduje, aby mal každý účastník prístup k revidovanému pracovnému produktu, rozumel svojej úlohe a zodpovednostiam a dostal všetko potrebné na vykonanie revízie.
* **Individuálna revízia**. Každý revidujúci reviduje definovaný pracovný produkt individuálne s cieľom posúdiť jeho kvalitu a identifikovať anomálie, odporúčania a otázky pomocou jednej alebo viacerých techník revízie (napr. revízia založená na kontrolnom zozname, revízia podľa scenárov– pozri norma ISO/IEC 20246 [@ISO20246]). Revidujúci zaznamenáva všetky zistené anomálie, odporúčania a otázky.
* **Komunikácia a analýza**. Nie každá anomália identifikovaná počas revízie musí byť nutne defekt. Preto je nutné všetky takéto anomálie analyzovať a prediskutovať a pri každej by sa malo rozhodnúť o jej stave, vlastníctve a požadovaných opatreniach. To sa zvyčajne vykonáva pri revíznej schôdzke, počas ktorej účastníci tiež diskutujú o úrovni kvality každého revidovaného pracovného produktu a aké následné opatrenia sú vyžadované. Na uzatvorenie opatrení môže byť vyžadovaná ďalšia revízia.
* **Opravy a reportovanie**. Aby bolo možné vykonať nápravu, mala by byť pre každý defekt vytvorený report o defekte. Pri splnení daných výstupných kritérií môže byť pracovný produkt akceptovaný a výsledky revízie sú podané v správe.

### Roly a zodpovednosti pri revíziách

Revíziu môžu vykonávať rôzni ľudia a môžu zastávať rôzne roly. Hlavné roly a ich povinnosti sú:

* **Manažér** – rozhoduje o tom, čo má byť revidované a aké zdroje budú využité (vrátane ľudí a času).
* **Autor** – vytvára a opravuje revidovaný pracovný produkt.
* **Moderátor** (niekedy aj facilitátor) – zaisťuje efektívny priebeh revíznych schôdzok vrátane využitia mediácie. Okrem iného dohliada na dodržanie časového rámca a zabezpečenie komfortného prostredia, v ktorom môže každý slobodne vyjadriť svoj názor.
* **Zapisovateľ** – zhromažďuje anomálie od revidujúcich a zaznamenáva ďalšie informácie z revízie ako napr. rôzne rozhodnutia alebo nové anomálie zistené počas revízneho stretnutia.
* **Revidujúci** – vykonáva revíziu. Revidujúcim môže byť niekto, kto pracuje na projekte alebo je odborníkom na danú problematiku alebo ktorákoľvek osoba zo zainteresovaných strán.
* **Vedúci revízie** – preberá celkovú zodpovednosť za revíziu (napr. rozhodovanie o tom, kto do nej bude zapojený) a organizáciu toho, kedy a kde sa bude revízia konať.

Popis ďalších možných rolí možno nájsť v norme ISO/IEC 20246 [@ISO20246].

### Typy revízií

Existuje mnoho typov revízií, od neformálnych až po veľmi formálne. Požadovaná úroveň formálnosti závisí od faktorov ako je použitý SDLC, vyspelosť procesu vývoja, kritickosť a zložitosť revidovaného pracovného produktu, právne alebo regulatórne požiadavky a potreba doloženia záznamov pre prípadný audit. Rovnaký pracovný produkt môže byť revidovaný rôznymi typmi revízií, napr. najprv neformálne a neskôr formálnejšie.

Výber správneho typu revízie je kľúčový pre dosiahnutie požadovaných cieľov revízie (pozri <#section:success-factors-for-reviews>). Výber je ale založený aj na ďalších faktoroch ako sú potreby projektu, dostupné zdroje, typ pracovného produktu, typ rizika, biznisová doména a firemná kultúra.

Medzi bežne používané typy revízií patria:

* **Neformálna revízia**. Neformálne revízie sa neriadia definovaným procesom a nevyžadujú formálny dokumentovaný výstup. Hlavným cieľom je odhaľovanie anomálií.
* **Predvedenie (walkthrough)**. Predvedenie (vedené autorom) môže slúžiť mnohým cieľom ako je hodnotenie kvality a budovanie dôvery v pracovný produkt, vzdelávanie revidujúcich, dosiahnutie dohody, generovanie nových nápadov, motivácia a podpora autora s cieľom zlepšovať pracovný produkt a odhaľovať anomálie. Revidujúci môžu (ale nemusia) pred predvedením vykonať individuálnu revíziu.
* **Technická revízia**. Technickú revíziu vykonávajú odborne kvalifikovaní revidujúci a vedie ju moderátor. Cieľom technickej revízie je primárne dosiahnuť zhodu a urobiť rozhodnutia týkajúce sa nejakého technického problému, ale tiež odhaliť anomálie, vyhodnotiť kvalitu, vybudovať dôveru v pracovný produkt, generovať nové nápady, motivovať autorov a podporiť ich v zlepšovaní.
* **Inšpekcia**. Vzhľadom na to, že inšpekcie sú najformálnejším typom revízie, riadia sa komplexným všeobecným procesom (pozri <#section:review-process-activities>). Hlavným cieľom je nachádzať maximálny počet anomálií. Ďalšími cieľmi sú hodnotenie kvality, budovanie dôvery v pracovný produkt, motivácia a podpora autorov v zlepšovaní. Sú zhromažďované metriky, ktoré sa používajú na zlepšovanie celého SDLC vrátane samotného procesu inšpekcie. Pri inšpekciách nemôže autor vystupovať ako vedúci revízie alebo zapisovateľ.*

### Faktory úspechu pri revízii {#success-factors-for-reviews}

Existuje niekoľko faktorov kľúčových pre úspech procesu revízie:

* Sú definované jasné ciele a merateľné výstupné kritériá. Nie sú hodnotení účastníci revízie, ale revidovaný pracovný produkt.
* Je vybraný taký typ revízie, ktorý je vhodný na dosiahnutie daných cieľov, pre typ pracovného produktu, pre účastníkov revízie a pre potreby a kontext projektu.
* Revízie sú vykonávané po malých častiach, takže revidujúci nestrácajú koncentráciu počas revízie a/alebo počas revíznych schôdzok (ak sa konajú).
* Zainteresovaným stranám a autorom je poskytovaná spätná väzba z revízií tak, aby mohli zlepšovať produkt a svoje činnosti (pozri <#section:benefits-early-and-frequent-feedback-from-stakeholders>).
* Účastníci majú dostatok času na prípravu.
* Manažment podporuje proces revízie.
* Revízie sú súčasťou firemnej kultúry s cieľom podporovať učenie a zlepšovanie procesov.
* Je poskytnuté vhodné odborné školenie pre všetkých účastníkov tak, aby vedeli, ako plniť svoju rolu v procese.
* Schôdze sú správne riadené.