---
title: Dimensjonssettposter – oversikt
description: 'I denne artikkelen får du en oversikt over hvordan dimensjonssettposter lagres som dimensjonssettposter, og hvordan de bokføres.'
author: SorenGP
ms.topic: overview
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: dimension
ms.date: 06/14/2021
ms.author: edupont
---
# <a name="dimension-set-entries-overview" />Dimensjonssettposter – oversikt
Dette emnet beskriver hvordan dimensjonssettposter lagres og bokføres i [!INCLUDE[prod_short](includes/prod_short.md)].  

## <a name="dimension-sets" />Dimensjonssett
Et dimensjonssett er en unik kombinasjon av dimensjonsverdier. Det lagres som dimensjonssettposter i databasen. Hver dimensjonssettpost representerer én enkelt dimensjonsverdi. Dimensjonssettet identifiseres av en felles dimensjonssett-ID som tilordnes hver dimensjonssettpost som tilhører dimensjonssettet.  

Eksempelet nedenfor viser et dimensjonssett som har tre dimensjonssettposter. Dimensjonssettet identifiseres av en dimensjonssett-ID, som er 108.  

|Dimensjonssett-ID|Dimensjonskode|Dimensjonsverdikode|Navn på dimensjonsverdi|  
|----------------------|--------------------|--------------------------|--------------------------|  
|108|OMRÅDE|70|Amerika – nord|  
|108|FIRMATYPE|HOME|Hjem|  
|108|AVDELING|SALG|Salg|  

## <a name="dimension-set-entries" />Dimensjonssettposter
Dimensjonssett lagres i tabellen med **Dimensjonssettpost** som dimensjonssettposter med samme ID for dimensjonssett.  

![Flyt for dimensjonssettposter.](media/dimensionentrynav7.png "Flyt for dimensjonssettposter")  

Når du oppretter en ny kladdelinje, et nytt dokumenthode eller en ny dokumentlinje, kan du angi en kombinasjon av dimensjonsverdier. I stedet for at hver dimensjonsverdi lagres eksplisitt i databasen, tilordnes en dimensjonssett-ID til kladdelinjen, dokumenthodet eller dokumentlinjen for å angi dimensjonssettet.  

Når du redigerer og lukker siden **Rediger dimensjonssettposter**, blir det utført en kontroll for å se om kombinasjonen av dimensjonsverdier eksisterer som et dimensjonssett i tabellen. Hvis kombinasjonen forekommer i tabellen, tilordnes den tilsvarende dimensjonssett-IDen til kladdelinjen, dokumenthodet eller dokumentlinjen. Ellers legges et nytt dimensjonssett til i tabellen, og den nye dimensjonssett-IDen tilordnes til kladdelinjen, dokumenthodet eller dokumentlinjen.

## <a name="codeunit-408-dimension-management" />Dimensjonsbehandling for codeunit 408
Codeunit 408, dimensjonsbehandling, er et funksjonsbibliotek som håndterer vanlige oppgaver som er knyttet til dimensjoner, for eksempel kopiering fra én tabell til en annen eller fra ett dokument til et annet.

## <a name="performance-improvement" />Ytelsesforbedring
Ved å lagre dimensjonssett én gang i databasen beholdes databaseplassen, og den generelle ytelsen blir forbedret.  

## <a name="see-also" />Se også
[Designdetaljer: Søke etter dimensjonskombinasjoner](design-details-searching-for-dimension-combinations.md)   
[Designdetaljer: Tabellstruktur](design-details-table-structure.md)   
[Designdetaljer: Dimensjonssettposter](/dynamics365/business-central/design-details-dimension-set-entries-overview)   


[!INCLUDE[footer-include](includes/footer-banner.md)]
