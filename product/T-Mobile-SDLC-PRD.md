# PRD · Agentní vývoj napříč systémy T-Mobile

**Verze 0.1 · 11. listopadu 2026 · návrh k revizi**

Pracovní návrh pro produktového sponzora, vlastníka služby a tým připravující PoC.

**Účel.** Vymezit produktový záměr, očekávané výsledky, první ověřitelný rozsah a rozhodnutí potřebná před realizací. Požadavky a kritéria níže tvoří navržený produktový kontrakt určený ke schválení. Rozsah zakázky, systém pro pilot, termín a rozpočet se stanoví po úvodním ověření prostředí.

## 1. Produktový záměr

Vybudovat workflow, které pomůže připravit kvalitní zadání, zajistí jeho zpracování agentními úlohami a dovede povolenou změnu přes ověření a potřebná rozhodnutí k nasazení. Workflow má společný průběh pro změny kódu a pro zásahy do uzavřených aplikací. Konkrétní realizace vychází ze schopností a oprávnění každého systému.

Vstupem je produktový podnět nebo incident. Výstupem je ověřená změna, odpovídající dokumentace a dohledatelný výsledek v původním pracovním kanálu. Lidé doplňují věcná rozhodnutí, řídí rozsah a přebírají případy, které vyžadují jejich zásah.

**Produktová hypotéza.** Spojení lepší přípravy zadání, práce s kontextem a automatizace realizace a kontrol sníží aktivní práci lidí i čekání mezi jednotlivými kroky. Průběžná aktualizace dokumentace má omezit její zastarávání při změnách. Velikost přínosu a vhodný záběr musí potvrdit pilot.

## 2. Potřeby a hypotézy

Při úvodním ověření se upřesní současný průběh práce, četnost vhodných případů a měřitelný výchozí stav.

| Potřeba nebo hypotéza | Co z ní plyne pro produkt |
| --- | --- |
| Kvalita vstupního zadání významně ovlivňuje výsledek. | Příprava specifikace, kontrola úplnosti a doptávání patří do základního toku. |
| Produkt má pokrýt nové funkcionality i incidenty. | Dva typy vstupu se společným dalším zpracováním. |
| Hodnotu má podpora systémů, ke kterým tým nemá zdrojový kód. | Realizační větev pro konfiguraci nebo změnu přes ověřené rozhraní aplikace. |
| Agenti potřebují větší kontext, například diagnostiku. | Povolené kontextové zdroje se připojí k analýze a realizaci. |
| Prostředí pro běh a testovací instance jsou podstatnou závislostí. | První use case se vybírá i podle možnosti provést a ověřit změnu. |
| Dokumentace se má aktualizovat spolu se změnou. | Dokumentace je samostatná schopnost produktu a součást dokončení změny. |
| Menší ruční pracnost a změna role vývojářů směrem k řízení agentů jsou očekávaným přínosem. | Přínos se vyhodnotí podle aktivního času lidí, čekání, přepracování a nákladů. |

Kandidáty pro ověření jsou **Sprinklr, MaJa, Siebel a OC+**. Konkrétní úloha, operace a rozsah napojení se potvrdí v rozhodnutích D02 a D04.

## 3. Uživatelé a odpovědnost

| Role | Potřebný výsledek | Rozhodnutí a odpovědnost |
| --- | --- | --- |
| Produktový manažer nebo zadavatel | Z podnětu vznikne proveditelná specifikace s ověřitelným výsledkem. | Potvrdí věcná očekávání a potřebné změny rozsahu. |
| Podpora nebo vlastník incidentu | Problém, screenshot a doplněné údaje se zpracují bez opakovaného předávání kontextu. | Doplní reprodukci, určí relevantního vlastníka a sleduje výsledek. |
| Vývojář nebo vlastník konfigurace | Připravená změna má dohledatelný důvod, diff a výsledky kontrol. | Převezme výjimky a rozhodne o technických dopadech přesahujících připravené zadání. |
| Schvalovatel podle pravidel služby | Vidí konkrétní verzi, její ověření a cílové prostředí. | Potvrdí nebo zamítne změnu v rozsahu své pravomoci. |
| Vlastník dokumentace | Potřebné postupy a popisy odpovídají změně. | Určí relevantní dokumenty a potvrdí jejich věcnou správnost. |
| Platformní a provozní tým | Běhy mají omezené přístupy, známý stav a podklady pro nápravu. | Potvrdí prostředí, identity, nástroje, přístup k datům a eskalační postup. |
| Produktový sponzor | Má doložený přínos a náklady na pokračování. | Vybere pilotní oblast a rozhoduje o rozsahu další etapy. |

Přiřazení rolí ke konkrétním lidem je součást rozhodnutí D01.

## 4. Cíle a měření úspěchu

| Cíl | Ukazatel a způsob měření | Cílová hodnota a okamžik rozhodnutí |
| --- | --- | --- |
| **G01 · Ověřit průchod od vstupu k výsledku** | Dokončený případ s vazbou na specifikaci, změnu, dokumentaci, testy a výsledek vydání. | PoC doloží úplný průchod ve vybraném testovacím prostředí podle AT01–AT12. |
| **G02 · Snížit aktivní práci lidí** | Součet aktivních minut na přípravu, realizaci, review, opravy a dokumentaci na srovnatelný případ. | Baseline a požadovaný přínos schválí tým před pilotem v D08. |
| **G03 · Zkrátit cestu k ověřenému výsledku** | Čas od přijetí podnětu do připraveného zadání a od přijetí do ověřeného vydání. Čekání se vykáže zvlášť. | Cíl se stanoví v D08 podle současného procesu a vybraného typu změny. |
| **G04 · Udržovat dokumentaci při změnách** | Podíl případů s vyhodnoceným dopadem a podíl potřebných aktualizací dokončených při vydání. Zvlášť čas lidí na jejich opravu. | PoC doloží konkrétní dokumentační změnu. Pilotní cíl se stanoví s vlastníkem dokumentace. |
| **G05 · Ověřit využitelný rozsah napříč systémy** | Podíl způsobilých případů z posuzovaného backlogu, důvody vyloučení a náklady na ověření a údržbu adaptéru. | Pilot potvrdí vhodnost vybrané operace. Rozšíření na další systém se rozhoduje samostatně. |

Vyhodnocení uvede počet případů, typy změn, prostředí a důvody zastavení nebo ručního převzetí. Porovnání zahrne i práci přesunutou do review a dokumentace. Malý nebo nesrovnatelný vzorek se označí jako omezený podklad pro rozhodnutí o rozšíření. Vyčíslení úspor, zrychlení a návratnosti je předmětem pilotu.

## 5. Rozsah po etapách

| Etapa | Výstup | Podmínka dokončení |
| --- | --- | --- |
| **Nabídka a discovery** | Prezentační tok, tento PRD, prohlídka konkrétního typu ticketu a ověření první systémové cesty. | Rozhodnuté D01–D03 a návrh dostupných prostředí a přístupů. |
| **Funkční PoC** | Jeden úplný průchod vybranou realizační větví v sandboxu nebo testovacím prostředí. Dva typy vstupu se předvedou na testovacích podkladech. Součástí je doptání, změna, dokumentace, ověření, potřebné rozhodnutí a výsledek v ticketu. | Doložené AT01–AT12 pro schválený rozsah. Každá simulovaná část má viditelné označení. |
| **Pilot v jednom týmu** | Skutečný zdroj požadavků, jedna vymezená operace nebo typ změny, odpovědný vlastník a povolené neprodukční prostředí. Měření proti baseline. | Přínos a provozní náklady vyhodnocené podle D08. Ověřené postupy předání a nápravy. |
| **Rozšíření a produkce** | Další typy změn, systémy a vydání do produkce podle potvrzené připravenosti. | Rozhodnuté D04–D09 pro příslušný systém a prostředí, vlastník provozu a schválená pravidla vydání. |

**Návrh první ověřovací jednotky.** Jeden tým, jeden vlastník služby, jeden opakovatelný typ změny a jeden cílový systém. Větev se vybere podle přístupu, možností testování a hodnoty pro zákazníka. Může jít o změnu vlastního kódu nebo o konfiguraci uzavřené platformy. Druhá větev může mít v PoC označenou simulaci. Tento výběr zpřesňuje dřívější pracovní námět s testovacím repozitářem a simulovanou konfigurací.

**Navazující možnosti.** Agentní widget v aplikaci, ovládání vývoje webovým chatem a další vstupní kanály se posoudí po prvním průchodu. Produkční akce, více týmů a skutečné zápisy do dalších dodavatelských aplikací mají vlastní rozsah a podmínky. Závazný harmonogram a cena se stanoví po discovery.

## 6. Uživatelské scénáře

| ID | Uživatel a potřeba | Pozorovatelný výsledek | Požadavky |
| --- | --- | --- | --- |
| **US01** | Produktový manažer potřebuje převést podnět na zadání pro realizaci. | Dostane návrh specifikace, otázky k mezerám a kritéria přijetí. | FR01–FR03. |
| **US02** | Podpora potřebuje nahlásit incident s dostupným screenshotem a doplnit potřebný kontext. | Případ má vlastníka, dohledatelné doptání a po doplnění může pokračovat. | FR01–FR04, FR12. |
| **US03** | Technický vlastník potřebuje realizovat změnu podle možností cílového systému. | Získá kódový nebo konfigurační diff, dokumentaci a výsledky ověření. | FR03–FR09, FR13. |
| **US04** | Schvalovatel potřebuje rozhodnout nad aktuální změnou. | Vidí verzi, důkazy a prostředí a může změnu potvrdit, vrátit nebo předat. | FR07–FR11. |
| **US05** | Vlastník dokumentace potřebuje udržet relevantní popis a postup při vydání změny. | Potřebná aktualizace je připojená k případu a odpovídá vydané verzi. | FR09, FR11–FR12. |
| **US06** | Sponzor potřebuje rozhodnout o dalším rozsahu. | Má srovnatelné údaje o práci lidí, průchodu, kvalitě a nákladech včetně zastavených případů. | FR12 a cíle G01–G05. |

## 7. Produktový tok

1. **Přijmout podnět nebo incident.** Zachovat původ, přílohy, vlastníka a místo pro komunikaci.
2. **Připravit specifikaci.** Načíst povolený kontext, určit mezery a doptat se. Případ čeká, dokud nemá proveditelné zadání a ověřitelný výsledek.
3. **Provést triáž a naplánovat práci.** Přiřadit systém, odpovědnost, testovací cestu a dostupné nástroje. Případ mimo rozsah předat člověku.
4. **Realizovat změnu.** Připravit úpravu kódu nebo konfigurace. Podle dopadu aktualizovat dokumentaci.
5. **Ověřit kandidáta.** Provést požadované testy, relevantní UI scénář a review. Nálezy vrátit k opravě a novému ověření.
6. **Rozhodnout podle pravidel služby.** Použít požadované schválení nebo předat výjimku člověku. Rozhodnutí se vztahuje na konkrétní verzi a cíl.
7. **Vydat a ověřit výsledek.** Použít povolenou cestu nasazení nebo publikace konfigurace a ověřit výsledek v cílovém prostředí.
8. **Dokončit případ.** Zpřístupnit odpovídající dokumentaci a oznámit skutečný výsledek v ticketu. Uchovat podklady pro měření a případné navazující řešení.

Stavy viditelné uživateli mají rozlišovat alespoň přijetí, doplňování, připravené zadání, realizaci, ověřování, čekání na rozhodnutí, vydávání, dokončení a ruční převzetí. Čekání a chyba obsahují důvod a odpovědnou roli. Přesné názvy stavů se sladí s vybraným ticketingem.

## 8. Funkční požadavky

Požadavky popisují cílové chování. V PoC se ověří základní tok a jedna skutečná realizační větev podle D02. Pilot rozšiřuje ověřený základ o reálné přístupy a workflow vybraného týmu.

| ID | Požadované chování | Vymezení prvního rozsahu | Ověření |
| --- | --- | --- | --- |
| **FR01 · Dva typy vstupu** | Přijmout produktový podnět a incident, zachovat původní text, povolené přílohy a identitu případu. Případ má vlastníka a kanál pro odpovědi. | Jeden testovací kanál, dvě vstupní šablony. Další kanály podle pilotu. | AT01, AT02. |
| **FR02 · Specifikace a doptání** | Připravit návrh očekávaného chování a kritérií přijetí. Při chybějících podkladech položit konkrétní otázky, pozastavit realizaci a pokračovat po odstranění mezery. | U incidentu reprodukce a cílové prostředí. U podnětu uživatel, potřeba a rozsah. | AT02, AT03. |
| **FR03 · Triáž a volba realizace** | Přiřadit odpovědnost, cílový systém a povolený způsob změny. Případ mimo rozsah nebo neřešitelnou výjimku předat člověku s důvodem a podklady. | Jeden předem vymezený typ změny. Kritické incidenty se řídí provozním postupem týmu. | AT03, AT11. |
| **FR04 · Kontext pro agenty** | Načítat relevantní povolené podklady a zachovat jejich reference. Chybějící nebo rozporný kontext označit a předat k doplnění. | PoC má testovací dokumentaci a podklady. Kibana, logy a Elastic jsou kandidáti k ověření v pilotu. | AT04. |
| **FR05 · Změna kódu** | Ve vybraném repozitáři připravit dohledatelný diff a testy odpovídající specifikaci. Výstup předat k ověření a review. | Skutečné provedení, pokud je v D02 zvolena kódová větev. | AT05, AT06. |
| **FR06 · Změna uzavřené platformy** | Připravit konfiguraci nebo jinou vymezenou změnu přes schválené rozhraní. Doložit rozsah akce, stav před změnou a ověřený výsledek. | Konkrétní operace, API, MCP nebo UI se potvrdí v D04. PoC může tuto větev doložit simulací. | AT05, AT06. |
| **FR07 · Testy a UI ověření** | Pro kandidáta získat výsledky povinných kontrol a relevantního uživatelského scénáře. Selhání vrátit k opravě a zablokovat další postup vyžadující úspěšné ověření. | Testovací instance nebo schválená testovací cesta. U opravy doložit reprodukci a úspěch po změně. | AT06, AT10. |
| **FR08 · Review a opravy** | Připravit agentní review a zpracovat jeho nálezy v omezené opravné smyčce. Novou verzi předat k novému odpovídajícímu ověření. | Konkrétní kontroly a limity podle D05 a D09. Neřešitelný nález převezme člověk. | AT07, AT09. |
| **FR09 · Údržba dokumentace** | Vyhodnotit dokumentační dopad, připravit potřebnou aktualizaci a připojit ji ke změně. Dokumentace dostupná po vydání odpovídá skutečné verzi. | PoC upraví jeden skutečný verzovaný dokument. Věcný soulad potvrdí určený vlastník v review. Úložiště a typy dokumentů určí D06. | AT08, AT12. |
| **FR10 · Rozhodnutí a předání člověku** | Umožnit potřebné schválení, vrácení a převzetí případu. Rozhodnutí je spojené s aktuální verzí, oprávněnou rolí a cílovým prostředím. | PoC předvede explicitní rozhodnutí člověka. Rozsah autonomie cílového provozu se určí podle systému a typu změny v D05. | AT09, AT11. |
| **FR11 · Vydání a následné ověření** | Vydat ověřenou změnu povolenou cestou a doložit výsledek v cíli. Při nejasném výsledku nejdřív zjistit stav původní akce a přidělit další postup vlastníkovi. | PoC vydává do sandboxu. Produkční pravidla a dostupný postup nápravy se potvrdí před produkčním rozšířením. | AT09–AT11. |
| **FR12 · Stav, oznámení a evidence** | Z ticketu zpřístupnit stav, důvod čekání a důkazy o výsledku. Oznámit dokončení povoleným kanálem a zaznamenat časové body pro měření. | Interní testovací kanál v PoC. Způsob oznámení a finální stavy se sladí s týmem. | AT01, AT12. |
| **FR13 · Centrální běh a nástroje** | Zajistit řízený běh úloh v povoleném prostředí a připojit nástroje podle jejich ověřených schopností. Přístup k jednotlivým operacím je oddělený od samotné dostupnosti integrace. | Jedno testovací prostředí a minimální sada adaptérů. Skutečný MCP hub, hosting a nástroje se ověří v D04 a D07. | AT04, AT05, AT11. |

## 9. Integrační rozsah a závislosti

| Oblast | Role v návrhu | Co potřebuje discovery |
| --- | --- | --- |
| **Sprinklr** | Příklad uzavřené platformy. Pro vybranou operaci se posoudí dostupná a schválená rozhraní. | Ověřit konkrétní operace, dostupná oprávnění, testovací prostředí a způsob potvrzení výsledku v dané instanci. |
| **MaJa, Siebel, OC+** | Kandidáti pro ověření navazujících integrací. | Úloha vybrané aplikace v pilotu, vlastník, rozhraní, typ změny a ověřovací cesta. |
| **Ticketing** | Společný vstup pro produkty i incidenty a místo pro informaci o výsledku. | Skutečný nástroj, události, přístupy, přílohy a způsob mapování stavů. |
| **Repozitář a CI/CD** | Kódová větev, review, automatické testy a vydání. | Repo, testy, identita, pravidla merge a nasazení, formát výstupů a vazba na konkrétní verzi. |
| **Dokumentace** | Výslovný požadavek na průběžnou údržbu. | Vlastník, typy dokumentů, úložiště, podoba review a publikace. |
| **Diagnostika a znalostní zdroje** | Kibana, logy a Elastic pro větší kontext. | Přístup, povolený rozsah dat, relevantní dotazy a reference použitelné v pracovním případu. |
| **Runtime a nástrojová vrstva** | Centrální prostředí pro agenty a testování, zmiňovaný hub nebo gateway. | Existující stav, dostupné prostředí, omezení běhu, model, síťové cíle a způsob správy přístupů. |

Pro každou skutečnou operaci se před pilotem zaznamená systém, vlastník, prostředí, povolená identita, vstup, očekávaný výstup, způsob ověření a reakce na nejasný nebo částečný výsledek. Potvrzený název aplikace je podklad pro discovery jejího zapojení.

## 10. Nefunkční a provozní požadavky

| ID | Požadavek | Ověření nebo rozhodnutí |
| --- | --- | --- |
| **NF01 · Přístupy a data** | Akce a cíle vynucuje aplikační nebo integrační vrstva podle oprávnění. Použité podklady, model a místo běhu odpovídají povolenému toku dat. Příloha ani výstup modelu nemění tato oprávnění. | PoC používá syntetická data a testovací cíle. Před pilotem potvrdit D07. AT11 ověří odmítnutí nepovolené akce. |
| **NF02 · Dohledatelnost verze** | Specifikace, změna, dokumentace, kontroly, rozhodnutí a vydání mají společnou identitu případu a přesné reference. Nová relevantní verze vyvolá odpovídající nové ověření. | AT05, AT08–AT10. |
| **NF03 · Konzistentní opakování** | Opakovaná událost nebo timeout nevede k duplicitnímu vydání. Běh udržuje jednoznačný stav. U operace s neověřitelným výsledkem následuje pozastavení a ruční převzetí. | AT01 a AT11. Podpora opakování v konkrétní aplikaci se ověří v D04. |
| **NF04 · Omezený běh a převzetí** | Každý běh má stanovené limity času, pokusů a nákladů a odpovědnou roli. Je možné běh pozastavit a předat s dosavadními podklady. | Hodnoty limitů, eskalační doby a cílové provozní parametry stanoví D09. AT07 a AT11. |
| **NF05 · Srozumitelnost stavu** | Uživatel pozná, co probíhá, co čeká, proč se případ zastavil a kdo má další krok. Oznámení odpovídá skutečnému výsledku. | Uživatelský průchod US01, US02 a US04. AT02, AT09 a AT12. |

## 11. Kritéria přijetí funkčního PoC

Následující scénáře jsou návrh ověření. Před začátkem musí být potvrzený use case, skutečná realizační větev, testovací cíl a příslušná rozhodnutí z oddílu 13. Každý výsledek uvádí, co proběhlo skutečně a která část využila simulaci.

| ID | Testovaný případ | Podmínka přijetí |
| --- | --- | --- |
| **AT01 · Příjem a duplicity** | Produktový podnět a incident dorazí testovacím kanálem. U jednoho případu přijde stejná událost opakovaně i souběžně. | Oba typy mají dohledatelnou identitu a vlastníka. Opakované doručení stejné události vrátí stejný běh a nepřidá souběžnou realizaci. |
| **AT02 · Chybějící podklad** | Incident postrádá potřebný údaj. Produktový podnět postrádá kritérium výsledku. | Systém položí odpovídající otázky, uvede vlastníka dalšího kroku a čeká. Realizace pokračuje až po odstranění konkrétní mezery. |
| **AT03 · Připravenost a předání** | Případ je úplný, případně zasahuje nepodporovanou operaci nebo oblast mimo rozsah. | Úplný případ má specifikaci, kritéria, cíl a testovací cestu. Ostatní varianta má důvod a odpovědnou roli pro převzetí. |
| **AT04 · Použití kontextu** | Agent používá testovací dokument a diagnostický podklad, případně potřebný podklad chybí. | Výstup odkazuje na použité zdroje. Chybějící nebo rozporný podklad je označený a předaný k doplnění. Přístup se drží povoleného rozsahu. |
| **AT05 · Skutečná vybraná větev** | Vybraný případ projde kódovou nebo konfigurační realizací podle D02. | Vznikne skutečný dohledatelný diff a ověřitelný výstup v povoleném testovacím systému. Je-li druhá větev simulovaná, její výstupy ji výslovně identifikují. |
| **AT06 · Testy a blokace** | Kandidát projde povinnými kontrolami a dohodnutým scénářem chování v testovacím prostředí. Samostatně se vyvolá selhání povinné kontroly. | Výsledky jsou přiřazené k ověřované verzi. Selhání zablokuje vydání a zaznamená konkrétní nález. U opravy chyby je doložený neúspěch na výchozí verzi a úspěch na opravené. |
| **AT07 · Review a oprava** | Review vrátí nález a samostatně se vyčerpá předem nastavený limit pokusů. | Oprava vytvoří novou verzi a potřebné nové kontroly. Vyčerpaný limit vede k ručnímu převzetí s podklady. |
| **AT08 · Dokumentace** | Změna vyžaduje aktualizaci testovacího dokumentu. Ověří se také záměrně zastaralý popis. | Agent připraví skutečný dokumentační diff. Kontrola ověří jeho vazbu na verzi. Odmítnutý nesoulad blokuje vydání do opravy a potvrzení. K dokončení je dostupná odpovídající dokumentace. |
| **AT09 · Rozhodnutí a aktuální verze** | PoC vyžaduje souhlas člověka. Ověří se chybějící souhlas, neoprávněná role a změna kandidáta nebo cílového prostředí po souhlasu. | Vydání vyžaduje platné rozhodnutí pro aktuální kombinaci. Každá neplatná varianta je zablokovaná s důvodem. |
| **AT10 · Vydání a kontrola výsledku** | Ověřená změna se vydá do sandboxu. Následná kontrola samostatně uspěje a selže. | Úspěšný případ má referenci vydání a důkaz chování v cíli. Selhání zůstane označené k řešení a předá se vlastníkovi. |
| **AT11 · Nejasný výsledek a oprávnění** | Operace vrátí timeout. Samostatně nástroj požaduje zápis mimo povolený cíl. | Systém se před dalším zápisem pokusí ověřit stav původní operace. Nejasný stav se předá člověku bez duplicitního vydání. Nepovolenou akci odmítne vrstva oprávnění. |
| **AT12 · Dokončení a vyhodnocení** | Úspěšný případ a případ předaný člověku se zobrazí zadavateli. | Stav odpovídá výsledku. Úspěšný případ obsahuje specifikaci, diff, dokumentaci, kontroly, rozhodnutí a vydání. Oba případy mají podklady pro vykázání času, čekání a nákladů běhu. |

Přijetí PoC vyžaduje důkazy ke všem scénářům v dohodnutém rozsahu, seznam zjištěných omezení a společné rozhodnutí vlastníka služby o dalším kroku. Změna rozsahu ověření se zaznamená před vyhodnocením.

## 12. Výstupy a rozhodnutí o pokračování

| Výstup | Minimální obsah | Příjemce |
| --- | --- | --- |
| **Záznam discovery** | Jeden konkrétní use case, současný průběh, vlastník, dostupná cesta realizace a testování. Přehled toho, co musí potvrdit zákazník. | Produktový sponzor a vlastník služby. |
| **Ověřený průchod PoC** | Testovací ticket, specifikace, skutečný diff vybrané větve, dokumentace, výsledky kontrol, rozhodnutí a ověřené testovací vydání. | Realizační tým a schvalovatel pilotu. |
| **Přehled blokací a předání** | Důkazy k negativním scénářům, dostupné režimy jednotlivých operací a omezení zjištěná při PoC. | Vlastník služby a platformní tým. |
| **Podklad pro pilot** | Navržený rozsah, odpovědnosti, baseline, způsob měření, otevřené náklady na integraci a podmínky přechodu do reálného neprodukčního prostředí. | Produktový sponzor. |

PoC poskytne podklad pro pilot po splnění dohodnutých kritérií a potvrzení přístupů a pravidel pilotního prostředí. Po pilotu sponzor rozhodne o rozšíření podle naměřeného přínosu, způsobilé části backlogu, provozních nákladů a připravenosti konkrétního systému. Produkční vydání je samostatné rozhodnutí vlastníka služby a provozu.

## 13. Otevřená rozhodnutí

Pro nejbližší jednání s Danem je potřeba vybrat vlastníka pilotní služby, jednu konkrétní změnu a ověřovací prostředí. K výběru poslouží typický dokončený ticket a případ s vracením nebo delším čekáním.

| ID | Co rozhodnout | Kdo má dodat rozhodnutí | Kdy |
| --- | --- | --- | --- |
| **D01 · Sponzor a rozsah** | Je cílem interní workflow pro více týmů, nebo konkrétní produktová oblast? Kdo vlastní první službu a kdo schvaluje rozsah? | Zadavatel a určený sponzor. | První jednání. |
| **D02 · První use case a větev** | Vybrat systém a opakovatelnou změnu s ověřitelným výsledkem. Určit, zda se skutečně ověří kódová, nebo konfigurační větev. | Sponzor, produktový tým a vlastník služby. | Discovery před zahájením PoC. |
| **D03 · Vstup a prostředí** | Potvrdit testovací ticketing, dostupný repo nebo konfiguraci, syntetický případ, testovací cíl a způsob ověření. | Vlastník služby a platformní tým. | Před PoC. |
| **D04 · Schopnosti adaptéru** | Pro každou dotčenou operaci potvrdit rozhraní, oprávnění, testovací prostředí, potvrzení výsledku a možnosti při částečném provedení. | Vlastník cílového systému a integrační tým. | Pro vybranou větev před PoC. Pro každé další skutečné zapojení před pilotem nebo rozšířením. |
| **D05 · Autonomie a vydání** | Určit, které změny vyžadují člověka, kdo může rozhodovat, co blokuje vydání a jak souvisí review s merge a nasazením. | Vlastník služby a provozní tým. | Testovací pravidla před PoC. Cílová pravidla před pilotem a produkcí. |
| **D06 · Dokumentace** | Vybrat první verzovaný dokument, jeho vlastníka, kontrolu správnosti a místo publikace. Pro pilot určit rozsah typů dokumentů. | Vlastník služby a dokumentace. | První dokument před PoC. Reálné úložiště před pilotem. |
| **D07 · Data, model a runtime** | Potvrdit místo běhu, povolené podklady, přístupy, model, cíle a pravidla ukládání důkazů. | Vlastník dat, platformní a bezpečnostní tým. | Syntetické podklady a testovací cíle před PoC. Reálná data a přístupy před pilotem. |
| **D08 · Baseline a úspěch** | Vybrat srovnatelné případy, měřené ukazatele, požadovaný přínos a hranici přijatelných nákladů. | Sponzor a vlastník procesu. | Před pilotem. |
| **D09 · Provoz a náprava** | Nastavit limity běhu, odpovědnost za převzetí, ověření výsledku, eskalaci a reakci na částečný nebo neúspěšný zásah. | Platformní a provozní tým s vlastníkem služby. | Limity a testovací eskalace před PoC. Provozní postupy před živým zápisem. |

## 14. Návazné podklady

- [Klientské plátno pipeline](../diagrams/T-Mobile-pipeline-pro-klienta.excalidraw)
- [Architektura C4](../diagrams/T-Mobile-SDLC-C4.excalidraw)
- [Interaktivní HTML](https://petrsovadina.github.io/neoviia-tmobile-pipeline/)
