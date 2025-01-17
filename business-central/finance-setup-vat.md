---
title: Definere merverdiavgift (mva)
description: 'Kontroller at du riktig beregne, postere og rapportere mva for salg og innkjøp. Vi anbefaler at du bruker den assisterte oppsettsveiledningen til å definere mva.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'VAT, posting, tax, value-added tax'
ms.search.form: '10, 118, 391, 470, 471, 472, 575, 734, 747, 748, 1877,'
ms.date: 01/31/2023
ms.author: bholtorf
---

# <a name="set-up-calculations-and-posting-methods-for-value-added-tax" />Definer beregninger og bokføringsmetoder for merverdiavgift

Forbrukere og selskaper betaler merverdiavgift (mva) når de kjøper varer eller tjenester. Mva-beløpet som skal betales, kan variere, avhengig av flere faktorer. I [!INCLUDE[prod_short](includes/prod_short.md)] konfigurerer du mva. for å angi satsene som skal brukes til å beregne mva-beløp som er basert på følgende parametere:

* Hvem du selger til  
* Hvem du kjøper fra  
* Hva du selger  
* Hva du kjøper  

Du kan definere mva-beregninger manuelt, men som kan være vanskelig og tidkrevende. Det er fordi det er svært enkelt å bruke forskjellige mva-satser ved en feiltakelse, og opprette unøyaktige mva-relaterte rapporter. For å gjøre det enklere å konfigurere mva. anbefaler vi at du bruker det assisterte oppsettet **Mva-oppsett** som du finner i produktet. 

Hvis du imidlertid vil definere mva-beregninger selv, eller bare vil lære mer om hvert trinn, inneholder denne artikkelen beskrivelser av hvert trinn:  

[!INCLUDE [finance-vat](includes/finance-vat.md)]

## <a name="set-up-vat-using-the-assisted-setup-guide-recommended" />Definer mva. ved å bruke den assisterte veiledningen for oppsett (anbefalt)

> [!NOTE]
> Du kan bare bruke veiledningen **Mva-oppsett**hvis du har opprettet et *Mitt selskap* og ikke ennå har bokført transaksjoner som inkluderer mva.

Hvis du vil oppsettguiden, gjør du følgende:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Assistert oppsett**. 
2. Velg **Angi merverdiavgift (mva.)**, og fullfør trinnene.
3. Når du har fullført det assisterte oppsettet, kan du gå til siden **Mva-bokføringsoppsett** og se om du må fylle ut flere felter i henhold til de lokale kravene i din versjon av [!INCLUDE [prod_short](includes/prod_short.md)]. Finn ut mer under [Lokal funksjonalitet i Business Central](about-localization.md).  

### <a name="check-the-vat-posting-setup" />Kontroller mva-bokføringsoppsettet

For å støtte deg i å komme raskt i gang varsler [!INCLUDE [prod_short](includes/prod_short.md)] deg hvis du mangler finanskontoer i bokføringsgrupper eller bokføringsoppsett, for eksempel på siden **Mva-bokføringsoppsett**. Du kan slå denne meldingstypen av eller på ved hjelp av varslingen *Finanskontoer mangler i bokføringsgruppe eller -oppsett* på siden **Mine varslinger**. Gå til siden **Mine innstillinger** og velg *Endre når jeg mottar varsler.* kobling.  

Hvis du velger et slikt varsel, oppretter [!INCLUDE [prod_short](includes/prod_short.md)] automatisk disse bokføringsoppsettene basert på bokføringsgruppene i dokumentet eller kladden du for øyeblikket arbeider med.  

På dette stadiet kan du bare fylle ut de manglende finanskontoene. Senere, når du begrenser oppsettet ytterligere, kan det hende du oppdager at dette første oppsettet ikke er riktig. Og [!INCLUDE [prod_short](includes/prod_short.md)] tillater ikke sletting av mva-bokføringsoppsett og generelle bokføringsoppsett når poster har blitt opprettet basert på slike konfigurasjoner. Fra lanseringsbølge 1 i 2022 kan du bruke feltet **Sperret** på siden **Mva-bokføringsoppsett** for å hindre at brukere ved en feiltakelse bruker et oppsett som ikke lenger er relevant for nye bokføringer.

## <a name="set-up-a-default-vat-date-for-documents-and-journals" />Definer en standard mva-dato for dokumenter og kladder

Mva-rapportering i [!INCLUDE [prod_short](includes/prod_short.md)] er basert på **Mva-dato** for å inkludere mva-poster i mva-rapporter i en mva-periode. Mva-datoen kan endres i alle dokumenter og kladder, men du må angi en standard verdi for mva-dato.

> [!NOTE]
> Etter bokføring av bilaget eller kladden, vises **mva-datoen** i både **mva-poster** og **finansposter** samt i det bokførte dokumentet hvis det finnes.

Følg denne fremgangsmåten for å definere en standardverdi for en mva-dato:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Finansoppsett**, og velg deretter den relaterte koblingen.  
2. På hurtigfanen **Generelt** i feltet **Standard mva-dato** velger du enten **Bokføringsdato** eller **Dokumentdato**.
3. Lukk siden.  

> [!NOTE]
> **Standard mva-dato** er som standard **bokføringsdatoen**.

### <a name="enabling-or-disabling-the-vat-date-feature" />Aktiver eller deaktiver funksjonen for mva-dato

Noen land krever at bedrifter bruker en bestemt mva-dato, mens andre land ikke gjør det. Noen land krever også at selskaper endrer mva-datoen i bestemte situasjoner etter at de har bokført dokumenter, mens andre land ikke tillater endringer i mva-datoer. Hvis du vil tillate forskjellige kontekster, kan du velge om du vil bruke denne funksjonaliteten og eventuelt i hvilken grad.

Følg denne fremgangsmåten for å definere nivået av mva-datobruk:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Finansoppsett**, og velg deretter den relaterte koblingen.  
2. På hurtigfanen **Generelt** i feltet **Mva-datobruk** angir du i hvilken grad du vil bruke funksjonen mva-dato. Du kan velge mellom et av følgende alternativer:

| Type | Beskrivelse |
|--------------------|-----------------------------------------|
| **Bruk hele funksjonaliteten for mva-dato** | Alt som er knyttet til **mva-dato** fungerer som standard, noe som gir deg den maksimal funksjonalitet for **mva-dato**. Du kan definere datoen, endre den i dokumenter, rapportere basert på den og endre datoen etter bokføringen så lenge perioden ikke er lukket eller beskyttet med tillatte datoer for bokføring. |
| **Bruk og ikke tillat endringer** | Alt som er knyttet til **mva-dato** fungerer som standard med ett unntak. Du kan ikke endre **mva-datoen** i **mva-poster**. |
| **Ikke bruk funksjonaliteten for mva-dato** | [!INCLUDE [prod_short](includes/prod_short.md)] vil skjule og gjøre **mva-datofeltene** ikke tilgjengelig for dokumenter, kladder og poster. **Standard mva-dato** blir konfigurert som **bokføringsdatoen**. |

3. Lukk siden.

> [!IMPORTANT]
> Selv om du velger alternativet **Ikke bruk funksjonaliteten for mva-dato**, bruker [!INCLUDE [prod_short](includes/prod_short.md)] **mva-datoen** i bakgrunnen. Siden **standard mva-dato** er konfigurert som **bokføringsdatoen**, og du ikke kan endre den i dette tilfellet, får du samme opplevelse som uten denne funksjonen. **Mva-datofelter** blir fjernet fra alle sider, men dette feltet vil fortsatt finnes i tabeller og rapporter vil fungere basert på den.

### <a name="limiting-periods-for-posting-and-changing-the-vat-date" />Begrens perioder for bokføring og endring av mva-dato

Du kan forhindre at andre bokfører eller endrer mva-poster i bestemte datointervaller. Du angir begrensningen ved hjelp av to innstillinger:

* Basert på lukket **mva-returperiode**
* Basert på feltene **Tillat bokføring fra** og **Tillat bokføring til**.

#### <a name="to-limit-posting-based-on-vat-return-period" />Slik begrenser du bokføring basert på mva-returperiode

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Finansoppsett**, og velg deretter den relaterte koblingen.  
2. På hurtigfanen **Generelt** i feltet **Kontroller mva-periode** angir du graden av mva-returperiodekontroll. Tabellen nedenfor beskriver alternativene.

| Type | Beskrivelse |
|--------------------|-----------------------------------------|
| **Blokker bokføring innenfor lukket og varsle for frigitt periode** | Forhindre at andre bokfører et dokument eller en kladd, eller endrer mva-poster, som har en mva-dato i en lukket **mva-returperiode**. [!INCLUDE [prod_short](includes/prod_short.md)] vil også vise en advarsel hvis **mva-returperioden** er åpen, men statusen for **mva-returen** er **Frigitt** eller **Sendt**. |
| **Blokker bokføring innenfor lukket periode** | Forhindre at andre bokfører et dokument eller en kladd, eller endrer mva-poster, som har en mva-dato i en lukket **mva-returperiode**. |
| **Varsle ved bokføring i lukket periode** | Vis en advarsel, men ikke blokker bokføring, hvis du vil bokføre et dokument eller en journal som har en mva-dato i en lukket **mva-returperiode**. |
| **Deaktivert** | Ikke gjør noe basert på en lukket **mva-returperiode**. |

#### <a name="to-limit-posting-based-on-allow-fromto-period" />Slik begrenser du bokføring basert på Tillatt fra/til-periode

Du kan definere begrensning på selskapsnivåer eller bestemte brukernivåer.

Slik begrenser du alle bokføringer for hele selskapet:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Finansoppsett**, og velg deretter den relaterte koblingen.  
2. På hurtigfanen **Generelt** angir du mva-datoen det kan bokføres fra, i feltet **Tillat bokføring fra**. Bokføring av et dokument eller en kladd med en mva-dato før denne datoen, er ikke tillatt.  
3. På hurtigfanen **Generelt** angir du mva-datoen det kan bokføres til, i feltet **Tillat bokføring til**. Bokføring av et dokument eller en kladd med en mva-dato etter denne datoen, er ikke tillatt.

Slik begrenser du bokføringer for en bestemt bruker:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Brukeroppsett** og velg den relaterte koblingen.  
2. I feltet **Bruker-ID** angir du brukeren du vil tillate å bokføre i en bestemt periode.  
3. Angi mva-datoen det kan bokføres fra, i feltet **Tillat bokføring fra**. Bokføring av et dokument eller en kladd med en mva-dato før denne datoen, er ikke tillatt.
4. Angi mva-datoen det kan bokføres til, i feltet **Tillat bokføring til**. Bokføring av et dokument eller en kladd med en mva-dato etter denne datoen, er ikke tillatt.

## <a name="set-up-vat-registration-numbers-for-your-country-or-region" />Definere organisasjonsnumre for landet eller området ditt

Du kan definere formater for organisasjonsnumre som brukes i land og områder som du handler med, for å sikre at det angis gyldige organisasjonsnumre. [!INCLUDE[prod_short](includes/prod_short.md)] viser en feilmelding hvis noen gjør en feil eller bruker et format som er feil for landet eller området.

Gjør følgende for å definere organisasjonsnumre:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 2.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Land/områder**.
2. Velg landet eller området, og velger deretter handlingen **Formater for org.nr.**.
3. I **Formater**-feltet definerer du formatet ved å angi én eller flere av følgende tegn:  

* **#** Krever et tall med ett siffer.  
* **@** Krever en bokstav. Det skilles ikke mellom store og små bokstaver i dette formatet.  
* **?** Tillater alle tegn.  

    > [!TIP]
    > Du kan bruke andre tegn så lenge de alltid finnes i land- eller områdeformatet. Hvis du vil inkludere et punktum eller en tankestrek mellom et sett med tall, kan du for eksempel definere formatet som ##.####.### eller @@-###-###.  

## <a name="set-up-vat-business-posting-groups" />Opprette mva-bokføringsgrupper for firma

Mva-bokføringsgrupper for firma skal representere markeder som du gjør forretninger med kunder og leverandører i, og definere hvordan du skal beregne og bokføre mva for hvert marked. Eksempler på mva-bokføringsgrupper for firma er **Innenlands** og **Den europeiske union (EU)**.  

Bruk koder som er lette å huske, og som beskriver bokføringsgruppen, for eksempel **EU**, **ikke-EU** eller **innenlands**. Hver kode må være unik, noe som betyr at du kan definere så mange koder du vil, men du kan ikke bruke samme kode mer enn én gang i en tabell.

Hvis du vil definere en mva-bokføringsgruppe for bedrifter, gjør du følgende:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 3.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Mva-bokføringsgrupper – firma**, og velg deretter den relaterte koblingen.  
2. Fyll ut feltene etter behov.

Du kan opprette standard mva-bokføringsgrupper for firma ved å knytte dem til firmabokføringsgrupper. [!INCLUDE[prod_short](includes/prod_short.md)] tilordner automatisk mva-bokføringsgruppen for firma når du knytter firmabokføringsgruppen til en kunde, leverandør eller finanskonto.

## <a name="set-up-vat-product-posting-groups" />Opprette mva-bokføringsgrupper for varer

Mva-bokføringsgrupper for produkter representerer varer og ressurser du kjøper eller selger, og du kan finne ut hvordan du skal beregne og bokføre mva i henhold til hvilken type vare eller ressurs.

Det er lurt å bruke koder som er lette å huske og som beskriver satsen, for eksempel **Ingen mva.** eller **Null**, **MVA10** eller **Redusert** for 10 prosent mva., og **MVA25** eller **Standard** for 25 prosent.

Hvis du vil definere en mva-bokføringsgruppe for bedrifter, gjør du følgende:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 4.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Mva-bokføringsgrupper – produkt**, og velg deretter den relaterte koblingen.  
2. Fyll ut feltene etter behov.

## <a name="combine-vat-posting-groups-in-vat-posting-setups" />Kombinere mva-bokføringsgrupper i mva-bokføringsoppsett

[!INCLUDE[prod_short](includes/prod_short.md)] beregner mva-beløp for salg og innkjøp som er basert på mva-posteringsoppsett, som er kombinasjoner av mva-bokføringsgrupper for firma og varer. For hver kombinasjon kan du angi mva-prosenten, mva-beregningstypen og finanskontoene for bokføring av mva i forbindelse med salg, kjøp og snudd avregning. Du kan også angi om mva skal beregnes på nytt når en kontantrabatt brukes eller mottas.  

Du kan definere så mange kombinasjoner du vil. Hvis du vil gruppere kombinasjoner av mva-bokføringsoppsett med lignende attributter, kan du definere en **mva-type** for hver gruppe og tilordne typen til gruppemedlemmene.

Hvis du vil kombinere mva-bokføringsoppsett, følger du denne fremgangsmåten:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 5.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Mva-bokføringsoppsett**, og velg deretter den relaterte koblingen.
2. Fyll ut feltene etter behov. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## <a name="assign-vat-posting-groups-by-default-to-multiple-entities" />Tilordne mva-bokføringsgrupper som standard til flere enheter

Hvis du vil bruke samme mva-bokføringsgrupper til flere enheter, kan du definere [!INCLUDE[prod_short](includes/prod_short.md)] å gjøre det som standard. Det er et par måter å gjøre dette på:

* Du kan tilordne mva-bokføringsgrupper for firma til firmabokføringsgruppen grupper eller maler for kunde eller leverandør
* Du kan tilordne mva-bokføringsgrupper for varer på varebokføringsgruppene  

Mva-bokføringsgruppe for firma eller vare tilordnes når du velger en bokføringsgruppe for firma eller vare for en kunde, leverandør, vare eller ressurs.

## <a name="assign-vat-posting-groups-to-accounts-customers-vendors-items-and-resources" />Tilordne mva-bokføringsgrupper til kontoer, kunder, leverandører, varer og ressurser

De følgende delene beskriver hvordan du tilordner du mva-bokføringsgrupper til enkeltenheter.

### <a name="to-assign-vat-posting-groups-to-individual-general-ledger-accounts" />Tilordne mva-bokføringsgrupper til individuelle finanskonti

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 6.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angir **Kontoplan** og velger deretter den relaterte koblingen.  
2. Åpner **Finans**-kortet for kontoen.  
3. På hurtigfanen **Bokføring** i feltet **Bokføringstype** velger du enten **Salg** eller **Kjøp**.  
4. Velg mva-bokføringsgruppene for å bruke for salgs- eller kjøpskontoen.  

### <a name="to-assign-vat-business-posting-groups-to-customers-and-vendors" />Tilordne mva-bokføringsgrupper for firma til kunder og leverandører

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 7.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Kunde** eller **Leverandør** og velg den relaterte koblingen.  
2. På kortet **Kunde** eller **Leverandør** utvider du hurtigfanen **Fakturering**.  
3. Velg mva-bokføringsgruppen for firma.  

### <a name="to-assign-vat-product-posting-groups-to-individual-items-and-resources" />Tilordne mva-bokføringsgrupper for vare til individuelle varer og ressurser

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 8.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Vare** eller **Ressurs** og velg den relaterte koblingen.  
2. Gjør ett av følgende:  

    * På **Vare**-kortet utvider du hurtigfanen **Pris og bokføring** og velger deretter **Vis mer** for å vise feltet **Mva-bokføringsgruppe - vare**.  
    * På kortet **Ressurs** utvider du hurtigfanen **Fakturering**.  
3. Velg mva-bokføringsgruppen for vare.  

## <a name="set-up-clauses-to-explain-vat-exemption-or-non-standard-vat-rates" />Definere setninger for å forklare mva-fritak eller ikke-standard mva-satser

Du kan definere en mva-setningsdel til å beskrive informasjon om hvilken type mva som brukes. Informasjonen kan være nødvendig ifølge bestemmelser fra myndighetene. Når du har definert en mva-setning, og knyttet den til et mva-bokføringsoppsett, vises mva-setningen på utskrevne salgsdokumenter som bruker gruppen for mva-bokføringsoppsett.

Hvis det er nødvendig, kan du også angi hvordan du kan oversette mva-setningsdeler til andre språk. Deretter, når du oppretter og skriver ut et salgsdokument som inneholder en mva-type, vil det oversatte dokumentet inkludere mva-setningen. Språkkoden som er angitt på kundekortet bestemmer språket.

Når ikke-standard mva-satser brukes i forskjellige typer dokumenter, for eksempel fakturaer eller kreditnotaer, må selskaper vanligvis inkludere en unntakstekst (mva-setning) som angir hvorfor en redusert mva eller null mva-sats er beregnet. Du kan definere forskjellige mva-setninger som skal være med i forretningsdokumenter i henhold til dokumenttypen, for eksempel faktura eller kreditnota. Dette gjør du på siden **Mva-setninger etter dokumenttype**.

Du kan endre eller slette en mva-setning, og endringene gjenspeiles i genererte rapporter. [!INCLUDE[prod_short](includes/prod_short.md)] beholder i imidlertid ikke historikk av endringen. Mva-setningsbeskrivelsene skrives ut på rapporten og vises for alle linjene i rapporten ved siden av mva-beløpet og mva-grunnlagsbeløpet. Hvis det ikke er definert en mva-setning for alle linjene i salgsdokumentet, utelates hele delen når rapporten skrives ut.

### <a name="to-set-up-vat-clauses" />Opprette mva-setninger

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 9.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Mva-setninger** og velg deretter den relaterte koblingen.  
2. På siden **Mva-setninger** oppretter du en ny linje.  
3. Angi en ID for setningen i **KCode**-feltet. Du bruker denne koden til å knytte setningen til mva-bokføringsgrupper.  
4. I feltet **Beskrivelse** angir du mva-fritaksteksten som du vil vise på dokumenter som kan inkludere mva. I feltet **Beskrivelse 2** angir du mer tekst om nødvendig. Teksten vises på nye dokumentlinjer.
5. Velg handlingen **Beskrivelse etter dokumenttype**.
6. På siden **Mva-setninger etter dokumenttype** fyller du ut feltene for å definere hvilken mva-fritakstekst som skal vises for hvilken dokumenttype.  
7. Valgfritt: Hvis du vil tilordne mva-setningsdelen til en mva-bokføringsoppsettet umiddelbart, velger du **Oppsett**, og deretter velge setningen. Hvis du vil vente, kan du tilordne setningsdelen senere på siden **mva-bokføringsoppsett**.  
8. Valgfritt: Hvis du vil angi hvordan du vil oversette mva-setningen, velger du **Oversettelser**.

### <a name="to-assign-a-vat-clause-to-a-vat-posting-setup" />Slik tilordner du en mva-setning til et mva-bokføringsoppsett

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 10.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Mva-bokføringsoppsett**, og velg deretter den relaterte koblingen.  
2. I kolonnen **Mva-setning** velger du setningen som skal brukes for hvert mva-bokføringsoppsett den gjelder for.  

### <a name="to-specify-translations-for-vat-clauses" />Angi oversettelser for mva-setninger

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 11.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Mva-setninger** og velg deretter den relaterte koblingen.  
2. Velg handlingen **Oversettelser**.  
3. I feltet **Språkkode** velger du hvilket språk du skal oversette til.  
4. I feltene **Beskrivelse** og **Beskrivelse 2** skriver du inn oversettelsen av beskrivelsene. Denne teksten vises i de oversatte mva-rapportdokumentene.  

### <a name="to-specify-extended-text-for-vat-clauses" />For å angi utvidet tekst for mva-setninger

> [!NOTE]  
> Hvis landet eller området krever lengre tekst for mva-setningene enn standardversjonen støtter, kan du angi den lengre teksten for mva-setningene som *utvidet tekst* slik at den blir skrevet ut på salgs- og kjøpsrapportene.  

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 11.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Mva-setninger** og velg deretter den relaterte koblingen.  
2. Velg handling for **Utvidede tekster**.  
3. Velg handlingen **Ny**.  
4. Fyll ut feltene **Språkkode** og **Beskrivelse**.  
5. Velg eventuelt **Alle språkkoder** eller spesifiser det relevante språket i **Språkkode**-feltet hvis du bruker språkkoder.  
6. Fyll ut feltene **Startdato** og **Sluttdato** hvis du vil begrense perioden for bruk av den utvidete teksten.  
7. Skriv den utvidede teksten for mva-setningene i **tekstlinjene**.  
8. Velg de relevante feltene for de aktuelle dokumenttypene du vil at de utvidete tekstene skal skrives ut på.  
9. Lukk siden.  

## <a name="create-a-vat-posting-setup-to-handle-import-vat" />Opprette et mva-bokføringsoppsett for å håndtere import-mva

Du bruker funksjonen for *import-mva* når du skal bokføre et dokument der hele beløpet er mva. Dette bruker du hvis du mottar en faktura fra skattemyndighetene for mva for importerte varer.  

Følg disse trinnene for å opprette koder for import-mva:  

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 12.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Mva-bokføringsgrupper – produkt**, og velg deretter den relaterte koblingen.  
2. Gå til siden Mva-bokføringsgrupper - vare. Definer en ny mva-varebokføringsgruppe for import-mva.  
3. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 13.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Mva-bokføringsoppsett**, og velg deretter den relaterte koblingen.  
4. Gå til siden Mva-bokføringsoppsett. Opprett en ny linje, eller bruk en eksisterende mva-bokføringsgruppe for firma sammen med den nye mva-varebokføringsgruppen for import-mva.  
5. I feltet **Mva-beregningstype** velger du **Full mva**.  
6. I feltet **Inngående mva-konto** angir du hvilken finanskonto som skal brukes til å bokføre import-mva. Alle andre kontoer er valgfrie.  

## <a name="use-reverse-charge-vat-for-trade-between-eu-countries-or-regions" />Bruk snudd avregning for handel mellom EU-land eller -områder

Enkelte selskaper må bruke snudd avregning ved handel med andre selskaper. Denne regelen gjelder for eksempel for kjøp fra EU-land og -regioner og salg til EU-land og -regioner.  

> [!NOTE]  
> Denne regelen gjelder ved handel med selskaper som er registrert som mva-pliktige i andre EU-land/-regioner. Hvis du handler direkte med forbrukere i andre EU-land/-regioner, så bør du kontakte skattemyndighetene for å høre hvordan gjeldende mva-regler er.  

> [!TIP]  
> Du kan kontrollere at et selskap er registrert som mva-pliktig i et annet EU-land, ved hjelp av tjenesten for validering av EU-organisasjonsnummer. Tjenesten er tilgjengelig gratis i [!INCLUDE[prod_short](includes/prod_short.md)]. Hvis du vil ha mer informasjon, kan du se [Bekrefte organisasjonsnumre](finance-how-validate-vat-registration-number.md).

### <a name="sales-to-eu-countries-or-regions" />Salg til EU-land eller -regioner

Mva beregnes ikke på salg til mva-pliktige selskaper i andre EU-land/-regioner. Du må rapportere verdien av slike salg til EU-land/-regioner separat i mva-oppgaven.  

For å beregne riktig mva på salg til EU-land /-regioner bør du:  

* Definere en linje for salg med samme informasjon for kjøp. Hvis du allerede har definert linjer på siden **Mva-bokføringsoppsett** for kjøp fra EU-land/-regioner, kan du også bruke disse linjene for salg.  
* Tilordne mva-bokføringsgruppene for firma i feltet **Mva-bokføringsgruppe – firma** på hurtigfanen **Fakturering** på kundekortet for hver EU-kunde. Du må også angi kundens organisasjonsnummer i feltet **Organisasjonsnr.** på hurtigfanen **Utenrikshandel**.  

Når du bokfører et salg til en kunde i andre EU-land/-regioner, beregnes mva-beløpet, og det opprettes en mva-post ved hjelp av informasjon om snudd avregning og mva-grunnlaget, som er beløpet som brukes til å beregne mva-beløpet. Ingen poster bokføres til mva-konti i Finans.

Hvis du vil bruke kombinasjonen av mva-bokføringsgruppe – firma og mva-bokføringsgruppe – vare til rapportering som tjenester i de periodiske mva-rapportene, merker du feltet **EU-tjeneste**.

> [!NOTE]  
> Feltet **EU-tjeneste** gjelder bare mva-rapporter. Feltet er ikke relatert til funksjonene **Tjenesteerklæring** eller **Intrastat for tjenester**.

## <a name="vat-rounding-for-documents" />Mva-avrunding for dokumenter

Beløp i dokumenter som ikke er bokført ennå, rundes av og vises på en måte som tilsvarer den endelige avrundingen av beløp som faktisk er bokført. Mva beregnes for et fullstendig dokument, som betyr at mva beregnes basert på summen av alle linjer med samme mva-type i dokumentet.  

## <a name="set-up-vat-reporting" />Konfigurer mva-rapportering

Du må definere informasjon om hvordan skattemyndighetene i ditt land eller område krever at du sender mva-rapporter. Fremgangsmåten nedenfor illustrerer den mest brukte informasjonen. Det kan imidlertid hende at landet eller området krever andre trinn. Hvis du vil ha mer informasjon, kan du se den relevante artikkelen i *delen Lokale funksjoner* i panelet til venstre.

[!INCLUDE [vat-report-setup](includes/vat-report-setup.md)]

## <a name="see-related-microsoft-trainingtrainingpathsprocess-vat-dynamics-365-business-central" />Se relatert [Microsoft-opplæring](/training/paths/process-vat-dynamics-365-business-central/)

## <a name="see-also" />Se også

[Definer mva-oppgavemaler og mva-oppgavenavn](finance-how-setup-vat-statement.md)  
[Definer urealisert merverdiavgift](finance-setup-unrealized-vat.md)  
[Rapportere mva til skattemyndighetene](finance-how-report-vat.md)  
[Arbeide med mva på kjøp og salg](finance-work-with-vat.md)  
[Arbeide med verktøyet for endring av mva-sats](finance-how-use-vat-rate-change-tool.md)  
[Bekrefte organisasjonsnumre](finance-how-validate-vat-registration-number.md)  
[Lokal funksjonalitet i Business Central](about-localization.md)  
[Mva-rapportering i den tyske versjonen](LocalFunctionality/Germany/vat-reporting.md)  
[Belgisk mva](LocalFunctionality/Belgium/belgian-vat.md)  
[Italiensk mva](LocalFunctionality/Italy/italian-vat.md)  
[Definere elektroniske mva- og ICP-deklareringer i den nederlandske versjonen](LocalFunctionality/Netherlands/how-to-set-up-electronic-vat-and-icp-declarations.md)  
[Mva-rapporter i den spanske versjonen](LocalFunctionality/Spain/vat-reports.md)  
[Definer mva-postering for varer og tjenester i den australske versjonen](LocalFunctionality/Australia/how-to-set-up-goods-and-service-tax-posting.md)  
[Mva i den tsjekkiske versjonen](LocalFunctionality/Czech/finance-vat.md)  
[Mva-rapportering i den norske versjonen](LocalFunctionality/Norway/norwegian-vat-reporting.md)  
[Rapporter avgift for varer/tjenester og harmonisert merverdiavgift i Canada](LocalFunctionality/Canada/sales-tax-goods-services.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
