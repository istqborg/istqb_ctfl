# Poznámky k vydání

Učební osnovy ISTQB® základní úrovně (ISTQB® Foundation Syllabus) v4.0 jsou významnou aktualizací, která vychází z předchozí verze 3.1.1 osnov základní úrovně a z učebních osnov Agile Tester 2014. Z tohoto důvodu neexistují detailní poznámky k vydání (release notes) na úrovni jednotlivých kapitol a sekcí a přehled zásadních změn je uveden v této kapitole.

Kromě toho poskytuje ISTQB® (v samostatných poznámkách k vydání) trasovatelnost mezi studijními cíli (LO) učebních osnov základní úrovně ve verzi 3.1.1, studijními cíli učebních osnov Agile Tester verze 2014 a studijními cíli učebních osnov základní úrovně ve verzi 4.0, kde je navíc zdůrazněno, které studijní cíle byly přidány, aktualizovány nebo odstraněny.

V době, kdy byly tyto učební osnovy vytvořeny (2022–2023) bylo evidováno více než 1 000 000 osob ve více než 100 zemích, kteří absolvovali zkoušku základní úrovně. Celosvětově pak existuje více než 800 000 certifikovaných testerů. Za předpokladu, že si všichni z nich přečetli učební osnovy základní úrovně s cílem složit zkoušku, je možné říct, že se jedná pravděpodobně o nejčtenější dokument v oblasti testování vůbec. Tato aktualizace je vytvořena tak, aby tyto hodnoty respektovala a také, aby přispěla ke zlepšení názorů na úroveň kvality, kterou ISTQB® přináší globální testovací komunitě.

V této verzi byly všechny studijní cíle upraveny tak, aby byly atomické, a aby byla vytvořena 1:1 trasovatelnost mezi studijními cíli a kapitolami učebních osnov. Jinými slovy, učební osnovy neobsahují kapitoly (obsah), ke kterým neexistuje studijní cíl. Cílem je usnadnit čtení, porozumění, učení a překlad s důrazem na zvýšení praktické užitečnosti a rovnováhy mezi znalostmi a dovednostmi.

V této verzi došlo k následujícím změnám:

* Zmenšení celkové velikosti osnov. Učební osnovy nejsou učebnice, ale dokument, který slouží k nastínění základní kostry jakéhokoliv úvodního kurzu o testování softwaru včetně informací o tom, jaká témata by měla být pokryta a na jaké úrovni. To znamená následující:
  * Ve většině případů jsou z textu vyloučeny příklady. Úkolem poskytovatele školení je pak tyto příklady (včetně praktických cvičení) poskytnout během školení.
  * Byl dodržen princip „Velikost textu vzhledem ke K-úrovni", který definuje maximální velikost textu pro studijní cíle na každé úrovni K (K1 = max. 10 řádků, K2 = max. 15 řádků, K3 = max. 25 řádků).
* Snížení počtu studijních cílů ve srovnání s osnovami základní úrovně (CTFL) verze 3.1.1 a Agile Tester (CTFL-AT) verze 2014:
  * 14 K1 cílů (FL v3.1.1 měla 15 cílů a AT 2014 6 cílů),
  * 42 K2 cílů (FL v3.1.1 měla 40 cílů a AT 2014 13 cílů),
  * 8 K3 cílů (FL v3.1.1 měla 7 cílů a AT 2014 8 cílů).
* K dispozici jsou rozsáhlejší odkazy na klasické a/nebo uznávané knihy a články o testování softwaru a souvisejících tématech.
* Hlavní změny v kapitole 1 (Základy testování)
  * Byla rozšířena a vylepšena podkapitola o dovednostech testerů.
  * Byla přidána podkapitola o týmovém přístupu (K1).
  * Podkapitola o nezávislosti testování byla přesunuta z kapitoly 5 do kapitoly 1.
* Hlavní změny v kapitole 2 (Testování v rámci SDLC)
  * Podkapitoly 2.1.1 a 2.1.2 byly přepracovány a vylepšeny, zároveň byly upraveny odpovídající studijní cíle.
  * Je kladen vyšší důraz na techniky vývoje iniciovaného testy (K1), přístupu shift-left (K2)
 a retrospektiv (K2).
  * Přidána nová podkapitola o testování v kontextu DevOps (K2).
  * Úroveň integračního testování byla rozdělena do dvou samostatných testovacích úrovní (testování integrace komponent a testování integrace systému).
* Hlavní změny v kapitole 3 (Statické testování)
  * Podkapitola o technikách revize spolu s odpovídajícím studijním cílem „(K3) Použít techniku revize" byla odstraněna.
* Hlavní změny v kapitole 4 (Testovací analýza a návrh testů)
  * Testování případů užití bylo odstraněno (ale je stále předmětem osnov Advanced Test Analyst).
  * Vyšší důraz je kladen na techniky testování založených na spolupráci (přidán nový K3 studijní cíl o použití ATDD k odvození testovacích případů a dva nové K2 cíle o uživatelských scénářích a akceptačních kritériích).
  * Testování a pokrytí rozhodnutí nahrazeno testováním a pokrytím větví (za prvé, termín pokrytí větví se v praxi používá více; za druhé, různé standardy definují termín rozhodnutí odlišně od větve; za třetí, řeší to drobný, ale závažný nedostatek ze starých osnov základní úrovně verze 2018, kde je napsáno, že „100% pokrytí rozhodnutí znamená 100% pokrytí příkazů" – tato věta není pravdivá v případě kódu bez podmínek nebo cyklů, tedy bez bodů rozhodnutí).
  * Byla vylepšena podkapitola o hodnotě testování bílé skříňky.
* Hlavní změny v kapitole 5 (Management testovacích aktivit)
  * Oddíl o testovacích strategiích/přístupech byl odstraněn.
  * Přidán nový K3 studijní cíl o technikách odhadování pracnosti pro testování.
  * Je kladen vyšší důraz na všeobecně známé agilní koncepty a nástroje při managementu testování: plánování iterací a vydání (K1), testovací pyramida (K1) a testovací kvadranty (K2).
  * Oddíl o managementu rizik je lépe strukturovaný popisem čtyř hlavních činností: identifikace rizik, posouzení rizik, zmírnění rizik a monitoring rizik.
* Hlavní změny v kapitole 6 (Testovací nástroje)
  * Rozsah textu o automatizací testů byl snížen z důvodů příliš vysoké odbornosti nevhodné pro učební osnovy základní úrovně.
  * Podkapitola o výběru nástrojů, provádění pilotních projektů a zavádění nástrojů do organizace byla odstraněna.