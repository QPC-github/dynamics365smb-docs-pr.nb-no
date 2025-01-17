---
title: Synkroniser varer og lager
description: Konfigurer og kjør synkroniseringer av varer mellom Shopify og Business Central
ms.date: 06/06/2023
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: '30116, 30117, 30126, 30127,'
author: AndreiPanko
ms.author: andreipa
ms.reviewer: bholtorf
---

# Synkroniser varer og lager

**Varene** i [!INCLUDE[prod_short](../includes/prod_short.md)] tilsvarer *produktene* i Shopify, som inkluderer fysiske varer, digitale nedlastinger, tjenester og gavekort du selger. Det er to hovedgrunner til å synkronisere varer:

1. Databehandling skjer først og fremst i [!INCLUDE[prod_short](../includes/prod_short.md)]. Du må eksportere alle eller noen data derfra til Shopify og gjøre dem synlige. Du kan eksportere varenavn, beskrivelse, bilde, priser, tilgjengelighet, varianter, leverandørdetaljer og strekkode. Når du har eksportert, kan du se gjennom varene eller gjøre dem synlige umiddelbart.
2. Når en ordre fra Shopify importeres, er informasjonen om varer viktig for ytterligere behandling av dokumentbehandling i [!INCLUDE[prod_short](../includes/prod_short.md)].

De to foregående scenarioene er alltid aktivert.

Et tredje scenario er å behandle data i Shopify, men importere disse varene i bulk til [!INCLUDE[prod_short](../includes/prod_short.md)]. Dette scenarioet kan være nyttig for dataoverføringshendelser, som når du vil koble en eksisterende nettbutikk med et nytt [!INCLUDE[prod_short](../includes/prod_short.md)]-miljø.

## Definer varesynkroniseringer

1. Velg søkeikonet ![Lyspære som åpner funksjonen Fortell meg.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-butikk**. Åpne butikken du vil konfigurere varesynkronisering for.
2. Velg ønsket alternativ i feltet **Synkroniser vare**.

   Tabellen nedenfor viser alternativene.

|Alternativ|Description|
|------|-----------|
|**Tom**| Produkter importeres sammen med import av ordrer. Produkter eksporteres til Shopify hvis en bruker kjører **Legg til vare**-handlingen fra siden **Shopify-produkter**. Dette valget er standardprosessen.|
|**Til Shopify**| Velg dette alternativet hvis du planlegger å oppdatere produkter manuelt ved å bruke **Synkroniser produkt**-handlingen eller med jobbkøen for regelmessige oppdateringer etter første synkronisering er utløst av **Legg til vare**-handlingen. Husk å aktivere feltet **Kan oppdatere Shopify-produkt**. Hvis den ikke er aktivert, er det lik alternativet **Tom** (standard prosess). Finn ut mer i delen [Eksporter varer til Shopify](synchronize-items.md#export-items-to-shopify).|
|**Fra Shopify**| Velg dette alternativet hvis du har tenkt å importere produkter fra Shopify samtidig, enten manuelt ved hjelp av **Synkroniser produkt**-handlingen eller med jobbkøen for regelmessige oppdateringer. Finn ut mer i delen [Importer varer fra Shopify](synchronize-items.md#import-items-from-shopify).|

## Importer varer fra Shopify

Først importerer du fra Shopify samtidig eller sammen med ordrer for å legge dem til i tabellene **Shopify-produkt** og **Shopify-variant**. Tildel deretter importerte produkter og varianter til varer og varianter i [!INCLUDE[prod_short](../includes/prod_short.md)]. Administrer prosessen med følgende innstillinger:

|Felt|Beskrivelse|
|------|-----------|
|**Opprett ukjente varer automatisk**|Når Shopify-produkter og -varianter importeres til [!INCLUDE[prod_short](../includes/prod_short.md)], prøver [!INCLUDE[prod_short](../includes/prod_short.md)]-funksjonen alltid å finne tilsvarende post i varelisten. **SKU-tildeling** påvirker hvordan samsvaret utføres og oppretter en ny vare eller varevariant. Aktiver dette alternativet hvis du vil opprette en ny vare eller når det ikke finnes en samsvarende post. Den nye varen opprettes ved hjelp av importerte data og **varemalkode**. Hvis dette alternativet ikke er aktivert, må du opprette en vare manuelt og bruke **Produkttildeling**-handlingen på siden **Shopify-produkter**.|
|**Varemalkode**|Bruk dette feltet med vekslebryteren **Opprett ukjente varer automatisk**.<br>Velg malen du vil bruke for automatisk opprettede varer.|
|**SKU-tilordning**|Velg hvordan du vil bruke **SKU**-verdien som er importert fra Shopify, under vare/variant-tildeling og -oppretting. Finn ut mer i delen [Effekten av SKU-er og strekkoder for Shopify-produkt på tildeling og oppretting av varer og varianter i Business Central](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central).|
|**SKU-skilletegn**|Bruk dette feltet med **SKU-tilordning** angitt til alternativet **[Varenr. + variantkode](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central)**.<br>Definer et skilletegn som skal brukes til å dele SKU-en.<br>Hvis du oppretter varianten med SKU-en 1000/001 i Shopify, skriver du inn / i feltet **SKU-skilletegn** for å hente varenummeret i [!INCLUDE[prod_short](../includes/prod_short.md)] som 1000 og varevariantkoden som 001.|
|**Variantprefiks**|Bruk sammen med **SKU-tildeling** satt til **Variantkode** eller alternativene **Varenr. + variantkode** som en reservefunksjon når SKU-en som kommer fra Shopify, er tom.<br>Hvis du vil opprette varevarianten i [!INCLUDE[prod_short](../includes/prod_short.md)] automatisk, må du angi en verdi i **Kode**. Som standard brukes verdien som er definert i SKU-feltet som ble importert fra Shopify. Hvis SKU er tom, vil det imidlertid generere en kode som begynner med definert variantprefiks og 001.|
|**Shopify kan oppdatere vare**|Velg dette alternativet hvis du vil oppdatere varer eller varianter automatisk.|

### Effekten av SKU-er og strekkoder definert i Shopify-produkt på tildeling og oppretting av varer og varianter i Business Central

Når produkter importeres fra Shopify til tabellene **Shopify-produkter** og **Shopify-varianter**, prøver [!INCLUDE[prod_short](../includes/prod_short.md)] å finne eksisterende poster.

Tabellen nedenfor viser forskjellene mellom alternativene i feltet **SKU-tildeling**.

|Alternativ|Innvirkning på tildeling|Innvirkning ved oppretting|
|------|-----------------|------------------|
|**Tom**|SKU-feltet brukes ikke i varetildelingsrutinen.|Ingen innvirkning på oppretting av varen.<br>Dette alternativet hindrer oppretting av varianter. Når det gjelder ordre, brukes bare hovedvare. En variant kan fremdeles tildeles manuelt på siden **Shopify-produkt**.|
|**Varenr.**|Velg hvis SKU-feltet inneholder varenummeret|Ingen innvirkning på oppretting av en vare uten varianter. For en vare med varianter opprettes hver variant som en separat vare.<br>Hvis Shopify har et produkt med to varianter, og lagerføringsenhetene er 1000 og 2000 i [!INCLUDE[prod_short](../includes/prod_short.md)], opprettes to varer med tallene 1000 og 2000.|
|**Variantkode**|SKU-feltet brukes ikke i varetildelingsrutinen.|Ingen innvirkning på oppretting av varen. Når det opprettes en varevariant, brukes verdien i SKU-feltet som en kode. Hvis SKU er tom, genereres det en kode ved hjelp av feltet **Variantprefiks**.|
|**Varenr. + variantkode**|Velg dette hvis SKU-feltet inneholder et varenummer og varevariantkoden er atskilt med verdien som er definert i feltet felt **SKU-skilletegn**.|Når du oppretter en vare, blir den første delen av verdien i feltet SKU angitt som **Nr.**. Hvis SKU-feltet er tomt, genereres et varenummer med nummerserien definert i feltet **Varemalkode** eller **Varenr.** på siden **Lageroppsett**.<br>Når du oppretter en vare, bruker variantfunksjonen den andre delen av verdien i feltet SKU som **Kode**. Hvis SKU-feltet er tomt, genereres det en kode ved hjelp av feltet **Variantprefiks**.|
|**Leverandørs varenr.**|Velg hvis SKU-feltet inneholder leverandørvarenummeret. I dette tilfellet blir ikke **Leverandørvarenr.** brukt på siden **Varekort**, i stedet brukes **Leverandørvarenr.** fra **Leverandørens varekatalog**. Hvis posten *Vareleverandørkatalog* inneholder en variantkode, brukes denne koden til å tildele Shopify-varianten.|Hvis det finnes en tilsvarende leverandør i [!INCLUDE[prod_short](../includes/prod_short.md)], blir lagerføringsenhetsverdien brukt som **Leverandørs varenr.** på siden **Varekort** og som **varereferanse** av *leverandørtypen*. <br>Forhindrer oppretting av varianter. Det er nyttig når du bare vil bruke hovedvare i ordren. Du kan fremdeles tildele en variant manuelt fra siden **Shopify-produkt**.|
|**Strekkode**|Velg hvis SKU-feltet inneholder en strekkode. Det utføres et søk mellom **varereferanser** av *strekkodetypen*. Hvis varereferanseposten inneholder en variantkode, brukes denne variantkoden til å tildele Shopify-varianten.|Ingen innvirkning på oppretting av varen. <br>Forhindrer oppretting av varianter. Det er nyttig når du bare vil bruke hovedvare i ordren. Du kan fremdeles tildele en variant manuelt fra siden **Shopify-produkt**.|

Tabellen nedenfor gir en oversikt over innvirkningen til feltet **Strekkode**.

|Innvirkning på tildeling|Innvirkning ved oppretting|
|-----------------|------------------|
|Det utføres et søk mellom **varereferanser** som har en strekkodetype for verdien som er definert i **Strekkode**-feltet i Shopify. Hvis varereferanseposten inneholder en variantkode, brukes denne variantkoden til å tildele Shopify-varianten.|Strekkoden lagres som **varereferanse** for varen og varevarianten.|

> [!NOTE]  
> Du kan utløse tildeling av de valgte produktene/variantene ved å velge **Prøv søk etter produkttildeling** eller alle importerte ikke-tildelte produkter ved å velge **Prøv å finne tildelinger**.

## Eksporter varer til Shopify

Velg varene fra varelisten som skal eksporteres til Shopify. Bruk handlingen **Legg til vare** på siden **Shopify-produkter** for å legge til varer i Shopify-produktlisten. 

>[!IMPORTANT]
>Produktet blir bare lagt til i salgskanalen **Nettbutikk**. Du må publisere produkter til andre salgskanaler, for eksempel Shopify-salgsstedet, fra Shopify.

Du administrerer prosessen med å eksportere varer ved å bruke følgende innstillinger:

|Felt|Beskrivelse|
|------|-----------|
|**Synkroniser utvidet tekst for vare**|Velg dette feltet for å synkronisere den utvidede teksten for varen. Den kan inneholde HTML-kode slik den blir lagt til i feltet *Beskrivelse*. |
|**Synkroniser vareattributter**|Velg dette feltet for å synkronisere vareattributter. Attributter formateres som en tabell og inkluderes i *Beskrivelse*-feltet i Shopify.|
|**Synkroniser markedsføringstekst for vare**|Velg dette feltet for å synkronisere markedsføringsteksten for varen. Selv om markedsføringstekst er en slags beskrivelse, er den forskjellig fra varens **Beskrivelse**-felt. **Beskrivelse**-feltet brukes vanligvis som et konsekvent visningsnavn for å identifisere produktet raskt. Markedsføringsteksten er derimot mer omfattende og beskrivende. Formålet er å legge til markedsførings- og kampanjeinnhold. Denne teksten kan deretter publiseres med varen i Shopify. Det finnes to måter å opprette markedsføringstekst på. Bruk Copilot, som foreslår tekst generert av kunstig intelligens for deg, eller start fra bunnen av.|
|**Språkkode**|Velg dette feltet hvis du ønsker de oversatte versjonene til tittel, attributter og utvidet tekst.|
|**SKU-tilordning**|Velg hvordan du vil fylle ut feltet for lagerføringsenhet i Shopify. Støttede alternativer er:<br> - **Varenr.** for å bruke varenr. for både produkter og varianter.<br> - **Varenr. + variantkode** for å opprette en lagerføringsenhet ved å sette sammen verdier fra to felter. For varer uten varianter brukes bare varenummeret.<br>- **Leverandørs varenr.** for å bruke vareleverandørnummeret som er definert på *varekortet* for både varer og varianter.<br> - **Strekkode** for å bruke strekkodetypen **Varereferanse**. Dette alternativet respekterer varianter.|
|**SKU-skilletegn**|Definer et skilletegn for alternativet **Varenr. + variantkode**.|
|**Lager sporet**| Velg hvordan systemet skal fylle ut feltet **Spor lager** for produkter som er eksportert til Shopify. Du kan oppdatere tilgjengelighetsinformasjon fra [!INCLUDE[prod_short](../includes/prod_short.md)] for produkter i Shopify der spor lager er aktivert. Finn ut mer i delen [Lager](synchronize-items.md#sync-inventory-to-shopify).|
|**Standard lagerpolicy**|Velg *Avslå* for å unngå negativ beholdning på Shopify-siden.|
|**Kan oppdatere Shopify-produkter**|Definer dette feltet hvis [!INCLUDE[prod_short](../includes/prod_short.md)] kan bare opprette varer eller kan oppdatere varer også. Velg dette alternativet hvis du planlegger å oppdatere produkter manuelt ved å bruke **Synkroniser produkt**-handlingen eller med jobbkøen for regelmessige oppdateringer etter første synkronisering er utløst av **Legg til vare**-handlingen. Husk å velge **Til Shopify** i feltet **Varesynkronisering**.|

### Oversikt over felttildeling

|Shopify|Kilde når den eksporteres fra [!INCLUDE[prod_short](../includes/prod_short.md)]|Mål når det importeres til [!INCLUDE[prod_short](../includes/prod_short.md)]|
|------|-----------------|-----------------|
|Status|I henhold til feltet **Status for opprettede produkter** på **Shopify-butikkortet**. Finn ut mer i delen [Ad hoc-oppdateringer av Shopify-produkter](synchronize-items.md#ad-hoc-updates-of-shopify-products).|Ikke i bruk.|
|Tittel | **Beskrivelse**. Hvis språkkoden er definert og en tilsvarende vareoversettelse eksisterer, blir vareoversettelse brukt i stedet for beskrivelse.|**Beskrivelse**|
|Description|Kombinerer utvidede tekster, markedsføringstekst og attributter hvis du aktiverte tilsvarende vekslebrytere på Shopify-butikkortet. Overholder språkkode.|Ikke i bruk.|
|SEO-sidetittel|Fast verdi: tom. Finn ut mer i delen [Ad hoc-oppdateringer av Shopify-produkter](synchronize-items.md#ad-hoc-updates-of-shopify-products).|Ikke i bruk.|
|SEO-metabeskrivelse|Fast verdi: tom. Finn ut mer i delen [Ad hoc-oppdateringer av Shopify-produkter](synchronize-items.md#ad-hoc-updates-of-shopify-products).|Ikke i bruk.|
|Medium|**Bilde**. Finn ut mer i delen [Synkroniser varebilder](synchronize-items.md#sync-item-images)|**Bilde**|
|Pris|Beregningen av sluttkundepris omfatter vareenhetspris, kundeprisgruppe, kunderabattgruppe og valutakode. Finn ut mer i delen [Synkroniser priser](synchronize-items.md#sync-prices-with-shopify)|**Enhetspris**. Prisen importeres bare til nylig opprettede varer, men den blir ikke oppdatert i senere synkroniseringer.|
|Sammenlign i prisen|Beregningen av prisen uten rabatt.|Ikke i bruk.|
|Kostnad per vare|**Enhetskost**|**Enhetskost**. Enhetskosten importeres bare til nylig opprettede varer, og den blir ikke oppdatert i senere synkroniseringer.|
|Lagerføringsenhet|Finn ut mer om SKUer under **SKU-tilording** i delen [Eksporter varer til Shopify](synchronize-items.md#export-items-to-shopify).|Finn ut mer om dette i delen [Effekten av SKU-er og strekkoder definert i Shopify-produkt på tildeling og oppretting av varer og varianter i Business Central](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central).|
|Strekkode|**Varereferanser** av strekkodetypen.|**Varereferanser** av strekkodetypen.|
|Spor antall|I henhold til feltet **Lager sporet** på siden **Shopify-butikkort**. Finn ut mer i delen [Lager](synchronize-items.md#sync-inventory-to-shopify). Brukes bare når du eksporterer et produkt for første gang.|Ikke i bruk.|
|Fortsett å selge når tomt på lager|I henhold til **Standard lagerpolicy** på **Shopify-butikkortet**. Brukes bare når du eksporterer et produkt for første gang.|Ikke i bruk.|
|Type|**Beskrivelse** av **Varekategorikode**. Hvis typen ikke er angitt i Shopify, blir den lagt til som en egendefinert type.|**Varekategorikode**. Tildeling etter beskrivelse.|
|Leverandør|**Navn** på leverandør fra **Leverandørnr.**|**Leverandørnr.**-tildeling etter navn.|
|Vekt|**Bruttovekt**.|Ikke i bruk.|
|Avgiftspliktig|Fast verdi: aktivert.|Ikke i bruk.|
|Avgiftskoder|**Mva-gruppekode**. Bare relevant for merverdiavgift. Finn ut mer under [Definer avgifter](setup-taxes.md).|Ikke i bruk.|

### Koder

Gå gjennom de importerte kodene i **Koder**-faktaboksen på siden **Shopify-produkt**. Velg handlingen **Koder** på den samme siden for å redigere koder.
Hvis alternativet **Til Shopify** er valgt i feltet **Synkroniser vare**, eksporteres tildelte koder til Shopify ved neste synkronisering.

## Kjør varesynkronisering

Fullstendig eller delvis varesynkronisering kan utføres på mange forskjellige måter.

### Første synkronisering av varer fra Business Central til Shopify

1. Gå til søkeikonet ![Lyspære som åpner funksjonen Fortell meg.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-produkter**. Velg den relaterte koblingen.
2. Velg handlingen **Legg til varer**.
3. I feltet **Butikkode** angir du koden. Hvis du åpner vinduet **Shopify-produkt** fra siden **Butikkort**, fylles butikkoden ut automatisk.
4. Hvis du har konfigurert bilde- og lagersynkronisering, kan du inkludere dem i samme prosess. Dette er praktisk for demonstrasjons scenarier eller når du håndterer mindre datamengder. 
5. Definer filtre for varer etter behov. Du kan for eksempel filtrere etter varenr. eller varekategorikode.
6. Velg **OK**.

De resulterende varene opprettes automatisk i Shopify med priser. Avhengig av hvilke valg du har gjort, kan avbildninger og lagernivåer inkluderes. Operasjonen kan ta litt tid hvis et stort antall varer legges til.

### Synkroniser produkter fra Shopify til Business Central

1. Gå til søkeikonet ![Lyspære som åpner funksjonen Fortell meg.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-butikk**. Velg den relaterte koblingen.
2. Velg butikken du vil synkronisere varer med for å åpne siden **Shopify-butikkort**.
3. Velg handlingen **Synkroniser produkter**.

Du kan også bruke handlingen **Synkroniser produkter** på siden **Shopify-produkter** eller søk etter den satsvise jobben **Synkroniser produkter**.

Du kan planlegge at oppgaven skal utføres på en automatisk måte. Finn ut mer under [Planlegg gjentakende oppgaver](background.md#to-schedule-recurring-tasks).

### Ad hoc-oppdateringer av Shopify-produkter

Når postene oppdateres i tabellen **Shopify-produkt**, synkroniseres følgende endringer med Shopify.

Oppdater:

* **Status** – du kan velge mellom aktiv, arkivert eller kladd.
* **SEO-tittel**
* **SEO-beskrivelse**

Sletting:

Avhengig av verdien i **Handling for fjernede produkter** på siden **Shopify-butikkort**, blir produktet oppdatert i Shopify når posten slettes fra siden **Shopify-produkt**.

* **Tom** – ingenting skjer. Om nødvendig må du utføre den nødvendige handlingen fra **Shopify-administratoren**.
* **Status til utkast** – status av produktet i Shopify er satt til *utkast*.
* **Status til arkivert** – produktet arkiveres i Shopify.

## Synkroniser varebilder

Synkronisering av bilder kan konfigureres for synkroniserte varer. Velg blant følgende alternativer:

* **Deaktivert** – bildesynkronisering er deaktivert.
* **Til Shopify** – bilder av varer eksporteres til Shopify.
* **Fra Shopify** – bilder fra Shopify importeres til [!INCLUDE[prod_short](../includes/prod_short.md)].

Bildesynkronisering kan startes på de to måtene beskrevet nedenfor.

### Synkroniser produktbilder fra siden Shopify-butikk

1. Gå til søkeikonet ![Lyspære som åpner funksjonen Fortell meg.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-butikker**. Velg den relaterte koblingen.
2. Velg butikken du vil synkronisere bilder med for å åpne siden **Shopify-butikkort**.
3. Velg handlingen **Synkroniser produktbilder**.

### Synkroniser produktbilder fra siden Shopify-produkter

1. Gå til søkeikonet ![Lyspære som åpner funksjonen Fortell meg.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-produkter**. Velg den relaterte koblingen.
2. Velg handlingen **Synkroniser produktbilder**.

### Bildesynkroniseringsmerknader

* Når du eksporterer bilder fra [!INCLUDE[prod_short](../includes/prod_short.md)] til Shopify, legges de nye bildene til i Shopify, noe som gjør at gamle bilder beholdes. Hvis et bilde blir oppdatert i [!INCLUDE[prod_short](../includes/prod_short.md)], må du slette gamle bilder i **Shopify-administratoren**.
* Bilder som eksporteres til Shopify som ikke samsvarer med kravene som er definert av Shopify, importeres ikke. Finn ut mer om [produktmedietyper på help.shopify.com](https://help.shopify.com/en/manual/products/product-media/product-media-types#images).

## Synkroniser priser med Shopify

Du administrerer prosessen med å eksportere priser ved å bruke følgende innstillinger:

|Felt|Beskrivelse|
|------|-----------|
|**Kundeprisgruppe**|Bestemme prisen for en vare i Shopify. Salgsprisen for denne kundeprisgruppen tas. Hvis ingen gruppe er angitt, brukes prisen på varekortet.|
|**Kunderabattgruppe**|Bestemme rabatten som skal brukes ved beregning av prisen på en vare i Shopify. Rabatterte priser lagres i **Pris**-feltet, og hele prisen er lagret i feltet **Sammenlign med pris**.|
|**Tillat linjerabatt**|Angir om du tillater en linjerabatt ved beregning av priser for Shopify. Denne innstillingen gjelder bare priser for varen. Prisene for kundeprisgruppen har sin egen vekslebryter på linjer.|
|**Priser inkl. mva.**|Angir om prisberegninger for Shopify inkluderer mva. Finn ut mer under [Definer avgifter](setup-taxes.md).|
|**Mva-bokføringsgruppe - firma**|Angir hvilken mva-firmabokføringsgruppe som brukes til å beregne prisene i Shopify. Dette skal være gruppen du bruker for innenlandske kunder. Finn ut mer under [Definer avgifter](setup-taxes.md).|
|**Valutakode**|Angi en valutakode bare hvis nettbutikken bruker en annen valuta enn lokal valuta (LV). Den angitte valutaen må ha valutakurser konfigurert. Hvis nettbutikken bruker samme valuta som [!INCLUDEprod_short], lar du feltet stå tomt.|

Du kan eksportere priser for synkroniserte varer på de to måtene som er beskrevet nedenfor.

### Synkroniser priser fra siden Shopify-produkter

1. Gå til søkeikonet ![Lyspære som åpner funksjonen Fortell meg.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-produkter**. Velg den relaterte koblingen.
2. Velg handlingen **Synkroniser priser til Shopify**.

### Prisberegningsmerknader

* Når du skal fastsette en pris, bruker [!INCLUDE[prod_short](../includes/prod_short.md)] laveste pris-logikk. Den laveste logikken ignorerer imidlertid enhetsprisen som er definert på varekortet, hvis prisen er definert i prisgruppen. Dette gjelder også når enhetsprisen fra varekortprisen er lavere.
* For å beregne priser oppretter koblingen et midlertidig tilbud for varen med et antall på 1, og bruker standard prisberegningslogikk. Bare priser og rabatter som gjelder for antall 1, brukes. Du kan ikke eksportere forskjellige priser eller rabatter basert på antall.

## Synkroniser lager til Shopify

Lagersynkronisering kan konfigureres for allerede synkroniserte varer. Det finnes to betingelser som må oppfylles:

1. Lagersporing må være aktivert for et produkt i Shopify. Hvis varer eksporteres til Shopify, bør du vurdere å aktivere **Lager sporet** på siden **Shopify-butikk**. Finn ut mer i delen [Eksporter varer til Shopify](synchronize-items.md#export-items-to-shopify).
2. Lagersynkronisering må være aktivert for **Shopify-lokasjoner**.

### Slik aktiverer du lagersynkronisering

1. Gå til søkeikonet ![Lyspære som åpner funksjonen Fortell meg.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-butikk**. Velg den relaterte koblingen.
2. Velg butikken du vil synkronisere lager med for å åpne siden **Shopify-butikkort**.
3. Velg handlingen **Lokasjoner** for å åpne **Shopify-butikklokasjoner**.
4. Velg handlingen **Hent Shopify-lokasjoner** hvis du vil importere alle lokasjonene som er definert i Shopify. Du finner dem i innstillingene [**Lokasjoner**](https://www.shopify.com/admin/settings/locations) i **Shopify-administratoren**.
5. I feltet **Lokasjonsfilter** legger du til lokasjoner hvis du bare vil ta med lager fra bestemte lokasjoner. Du kan skrive inn *ØST|VEST* for å gjøre lageret fra bare disse to lokasjonene tilgjengelig for salg via nettbutikken.
6. Velg lagerberegningsmetoden som skal brukes for de valgte Shopify-lokasjonene.

Du kan starte lagersynkronisering på de to måtene beskrevet nedenfor.

### Synkroniser lager fra siden Shopify-butikk

1. Gå til søkeikonet ![Lyspære som åpner funksjonen Fortell meg.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-butikker**. Velg den relaterte koblingen.
2. Velg butikken du vil synkronisere lager med for å åpne siden **Shopify-butikkort**.
3. Velg handlingen **Synkroniser lager**.

### Synkroniser lager fra siden Shopify-produkter

1. Gå til søkeikonet ![Lyspære som åpner funksjonen Fortell meg.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angir **Shopify-produkter**. Velg den relaterte koblingen.
2. Velg handlingen **Synkroniser lager**.

### Lagermerknader

* Standard lagerberegningsmetode er **Beregnet disponibel saldo per dato**. Med utvidelsesmuligheter kan du legge til flere alternativer. Hvis du vil lære mer om utvidelse, kan du gå til [eksempler](https://github.com/microsoft/ALAppExtensions/blob/main/Apps/W1/Shopify/extensibility_examples.md). 
* Du kan kontrollere lagerinformasjonen mottatt fra Shopify på siden **Shopify-lagerfaktaboks**. I denne faktaboksen får du en oversikt over Shopify-lageret og det siste beregnede lageret i [!INCLUDE[prod_short](../includes/prod_short.md)]. Det finnes én post per lokasjon.
* Hvis lagerinformasjonen i Shopify er forskjellig fra **Beregnet disponibel saldo** i [!INCLUDE[prod_short](../includes/prod_short.md)], blir lageret oppdatert i Shopify.
* Når du legger til en ny lokasjon i Shopify, må du også legge til lagerposter for den. Shopify gjør ikke det automatisk for eksisterende produkter og varianter, og koblingen vil ikke synkronisere lagernivåer for slike varer på ny lokasjon. Hvis du vil ha mer informasjon, går du til [Tildel lager til lokasjoner](https://help.shopify.com/manual/locations/assigning-inventory-to-locations).

#### Eksempel på beregning av beregnet disponibel beholdning

Det finnes 10 stykker av varen A tilgjengelig på lager og to utestående ordrer. En for mandag med antall *én* og en for torsdag med antall *to*. Avhengig av når du synkroniserer lageret, vil systemet oppdatere lagernivået i Shopify med ulike antall:

|Når synkronisering av lageret kjøres|Verdi som brukes til å oppdatere lagernivå|Merknad|
|------|-----------------|-----------------|
|Tirsdag|9|Lager 10 minus ordre angitt til forsendelse på mandag|
|Fredag|7|Lager 10 minus begge ordrer|

## Se også

[Kom i gang med koblingen for Shopify](get-started.md)  
