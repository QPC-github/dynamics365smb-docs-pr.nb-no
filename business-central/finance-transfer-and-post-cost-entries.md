---
title: Overføre og bokføre kostposter
description: 'Før du definerer kostfordelinger, må du forstå de ulike kildene kostposter kommer fra.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '1100, 1103, 1104, 1108, 1113, 1135'
ms.date: 06/16/2021
ms.author: edupont
---
# <a name="transferring-and-posting-cost-entries" />Overføre og bokføre kostposter

Før du definerer kostfordelinger, må du forstå hvordan kostposter kommer fra følgende kilder:  

- Automatisk overføring av finansposter.  
- Manuell kostnadsbokføring for rene kostposter, interne gebyrer og manuell fordelinger.  
- Bokføringer av automatiske fordelinger for faktiske kostnader.  
- Overføring av budsjettposter til faktiske.

## <a name="criteria-for-transferring-general-ledger-entries-to-cost-entries" />Kriterier for overføring av finansposter til kostposter

Det er viktig å forstå kriteriene for overføring av finansposter til kostposter. Under overføringen bruker kjørselen **Overfør finansposter til KR** følgende kriterier for å avgjøre om og hvordan finanspostene er overført.  

Finansposter overføres hvis følgende er tilfelle:  

- Postene har dimensjonsverdier som tilsvarer enten et kostsenter eller et kostobjekt.  
- Postene har dimensjonsverdier som tilsvarer et kostsenter og et kostobjekt. For disse postene har kostsenteret forrang. Dette bidrar til å unngå en situasjon der en kosttype vises i både et kostobjekt og et kostsenter og telles derfor to ganger i statistikken.  
- Bilagsnummeret i postene er tomt, slik at det vises med bilagsnummeret 0000 i kostpostene.  
- Postene overføres til en kosttype som tillater kombinerte poster, og disse postene overføres som en kombinert post enten månedlig eller daglig.  

Finansposter overføres ikke hvis følgende er tilfelle:  

- Postene har dimensjonsverdier som ikke tilsvarer et kostsenter eller et kostobjekt.  
- Postene har et beløp på null.  
- Postene har en finanskonto som er slettet.  
- Postene har en finanskonto som ikke er av typen **Resultatregnskap**.  
- Postene har en finanskonto som det ikke er tilordnet en kosttype for.  
- Postene har en bokføringsdato som er tidligere enn **Startdato for finansoverføring**.  
- Postene er bokført med en avslutningsdato. Dette er vanligvis poster som tilbakestiller saldoen i resultatregnskapet på slutten av året.

## <a name="transferring-general-ledger-entries-to-cost-entries" />Overføring av finansposter til kostposter

Du kan overføre finansposter til kostposter.  

Før du kjører prosessen for overføring av finansposter til kostposter, må du klargjøre overføringen for å unngå manuell korrigeringsbokføring.  

### <a name="to-prepare-the-transfer" />Klargjøre overføringen

1.  Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Kostregnskapsoppsett**, og velg deretter den relaterte koblingen.  
2.  På siden **Kostregnskapsoppsett** kontrollerer du at feltet **Startdato for finansoverføring** er satt til den riktige verdien.  
3.  Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Diagram med kosttyper** og velg deretter den relaterte koblingen.  
4.  Kontroller at feltet **Finanskto. fra/til** på siden **Kosttypekort** er riktig koblet for hver kosttype, slik at poster hentes fra finans.  
5.  Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angir **Kontoplan** og velger deretter den relaterte koblingen.  
6.  For hver relevant finanskonto på **Finanskort-siden** kontrollerer du at **Kosttypenr.** -feltet er riktig tilknyttet en kostnadstype. Hvis du vil ha mer informasjon, kan du se [Definere kostregnskap](finance-set-up-cost-accounting.md).  
7.  Kontroller at alle relevante finansposter har dimensjonsverdier som svarer til et kostsenter og et kostobjekt.  

### <a name="to-transfer-general-ledger-entries-to-cost-entries" />Slik overfører du finansposter til kostposter:

1.  Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og skriv inn **Overfør finansposter til KR**, og velg deretter den relaterte koblingen.  
2.  Velg **Ja**-knappen for å starte overføringen. Prosessen overfører alle finansposter som ikke allerede er overført.  

Under overføringen oppretter prosessen forbindelser i postene i tabellen **Kostpost** og i tabellen **Kostjournal**. Dette gjør det mulig å spore kilden til kostposter.

## <a name="automatic-transfer-and-combined-entries" />Automatisk overføring og sammensatte poster

I kostnadsregnskap kan du overføre finansposter til en kosttype ved å bruke en kombinert bokføring. Du kan angi om en kosttype mottar kombinerte poster i feltet **Kombiner poster** i kosttypedefinisjonen. Tabellen nedenfor beskriver de ulike alternativene.  

|Kombiner poster|Description|  
|---------------------|-----------------|  
|Ingen|Hver finanspost overføres individuelt til tilsvarende kosttype.|  
|Dag|Finansposter med samme bokføringsdato overføres som én post til tilsvarende kosttype.|  
|Måned|Alle finansposter som har samme kalendermåned, overføres som én post til den tilsvarende kosttypen.|  

> [!IMPORTANT]  
>  Hvis du har merket av for **Overfør automatisk fra Finans** på siden **Kostregnskapsoppsett**, oppdaterer [!INCLUDE[prod_short](includes/prod_short.md)] kostregnskapet etter hver bokføring i finans. Kombinerte poster er ikke mulig.

## <a name="results-of-transferring-general-ledger-entries-to-cost-entries" />Resultater av overføring av finansposter til kostposter

Under overføring av finansposter til kostposter oppretter [!INCLUDE[prod_short](includes/prod_short.md)] forbindelser i postene i tabellen **Finanspost**, **Kostpri.** og **Kostjournal** for å gjøre det mulig å spore forbindelsene mellom kostposter og finansposter.  

### <a name="general-ledger-entries" />Finansposter

For hver finanspost som overføres til kostregnskap, fyller [!INCLUDE[prod_short](includes/prod_short.md)] ut feltet **Postnr.**-feltet for kost.  

### <a name="cost-entries" />Kostposter

For hver kostpost lagrer [!INCLUDE[prod_short](includes/prod_short.md)] postnummeret for tilsvarende finanspost i feltet **Finansløpenr.** i tabellen **Kostpri.**  

For kombinerte kostposter lagrer [!INCLUDE[prod_short](includes/prod_short.md)] postnummeret på den siste finansposten, som er posten med det høyeste postnummeret.  

Feltet **Finanskonto** i tabellen **Kostpri.**-tabellen inneholder nummeret på finanskontoen som kostposten kom fra.  

Når det gjelder enkeltkostposter, overfører [!INCLUDE[prod_short](includes/prod_short.md)] bokføringsteksten fra finansposten til **Beskrivelse**-tekstfeltet. Når det gjelder kombinerte poster, viser tekstfeltet at disse postene overføres som kombinerte poster. For en kombinert post for oktober i 2013 kan for eksempel teksten være **Kombinerte poster, oktober 2013**.  

### <a name="cost-register" />Kostjournal

I **Kostjournal**-tabellen oppretter [!INCLUDE[prod_short](includes/prod_short.md)] en post med kildeoverføringen fra finans. Posten registrerer det første og det siste løpenummeret for finanspostene som overføres, i tillegg til det første og det siste løpenummeret for kostpostene som opprettes.

## <a name="see-related-microsoft-trainingtrainingmodulestransfer-gl-entries-dynamics-365-business-central" />Se relatert [Microsoft-opplæring](/training/modules/transfer-gl-entries-dynamics-365-business-central/)

## <a name="see-also" />Se også

 [Om kostregnskap](finance-about-cost-accounting.md)  
 [Definer kostregnskap](finance-set-up-cost-accounting.md)  
 [Definere og fordele kostnader](finance-define-and-allocate-costs.md)  
 [Gjøre rede for kostnader](finance-manage-cost-accounting.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
