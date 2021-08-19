---
title: Juster og avstem kostnader med finans ved hjelp av jobbkø
description: Finn ut hvordan du kan bruke jobbkøen til å flytte aktivitetene for å justere lagerkost eller avstemme den sammen med Finans til bakgrunnen. Hvis selskapet for eksempel kjører mange oppgaver eller behandler mange transaksjoner.
author: AndreiPanko
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.date: 07/28/2021
ms.author: andreipa
ms.openlocfilehash: e44936d9d9ec39d9232285d7293c152c57ab0a56
ms.sourcegitcommit: 769d20d299155cba30c35636d02b2ef021e4ecc1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/29/2021
ms.locfileid: "6688466"
---
# <a name="adjust-and-reconcile-inventory-cost-with-general-ledger-with-job-queue"></a>Juster og avstem lagerkost med finans med jobbkø

For å optimalisere opplevelsen er automatisk kostjustering og bokføring i finans aktivert som standard. Ettersom dataene akkumuleres over tid, kan det imidlertid påvirke ytelsen. For å redusere belastningen på programmet er det ofte nyttig å bruke oppføringer i jobbkø til å flytte oppgaver slik at de kjører i bakgrunnen.

## <a name="move-the-task-of-adjusting-item-costs-to-the-background-with-the-help-of-assisted-setup"></a>Flytt oppgaven for å justere varekostnader til bakgrunnen ved hjelp av assistert oppsett

Det kan være vanskelig å opprette postene for jobbkø, selv for en erfaren konsulent, så vi har en veiledning for assistert oppsett for å gjøre prosessen enklere for justering av varekostnader. 

1. Velg ikonet ![lyspære som åpner Fortell meg-funksjonen](media/ui-search/search_small.png "Fortell hva du vil gjøre"), angi **Lageroppsett**, og velg deretter den relaterte koblingen.  
2. På siden **Lageroppsett** aktiverer/deaktiverer du feltet **Automatisk kostbokføring** eller angir **Aldri** i feltet **Automatisk kostjustering**.  
3. I varselet som nå vises øverst på siden, velger du koblingen **Planlegg jobbkøpost**.
4. Angi oppgaven du vil planlegge.  

  > [!NOTE]
  > Du kan ikke opprette en ny jobbkøpost hvis det allerede finnes en jobbkøpost for den angitte oppgaven. 
5. Velg feltet **Vis jobbkøposter når fullført** for å gå gjennom og justere innstillingene. Hvis du vil ha mer informasjon, kan du se [Bruk jobbkøer til å planlegge oppgaver](admin-job-queues-schedule-tasks.md).  

## <a name="to-create-a-job-queue-entry-for-adjusting-and-reconciling-inventory-cost-manually"></a>Slik oppretter du en jobbkøpost for justering og avstemming av lagerkost manuelt

Du kan også opprette jobbkøposter manuelt. Følgende fremgangsmåte viser hvordan du angir at kjørselen **Juster kostverdi – vareposter** skal kjøre daglig automatisk, men den samme fremgangsmåten gjelder kjørselen **Bokfør lagerkost i finans**. 

1. Velg ikonet ![Lyspære som åpner Fortell meg-funksjonen](media/ui-search/search_small.png "Fortell hva du vil gjøre"), angi **Poster i jobbkø**, og velg deretter den relaterte koblingen.  
2. Velg handlingen **Ny**.  
3. I feltet **Objekttype som skal kjøres** velger du *Rapport*.  
4. I feltet **Objekt-ID som skal kjøres** velger du *795*, **Juster kostverdi – vareposter**.  
5. I feltet **Datoformel for neste kjøring** angir du *1D*.
6. I feltet **Starttidspunkt** angir du *02:00*.
7. Velg **Sett status til Klar**-handlingen.

Nå oppdateres lagerkosten hver natt.  

Hvis du vil planlegge en oppgave for avstemming av lager med finans, velger du Codeunit 2846 **Bokfør lagerkost til finans**.


> [!NOTE]
> Du unngår låsing ved ikke å planlegge oppgaver for kjørselen **Juster kostverdi – vareposter**, codeunit **Bokfør lagerkost til finans** og oppgaver for bokføring av salgs-eller kjøpstransaksjoner samtidig, og kontrollere at de bruker samme jobbkøkategori.

## <a name="see-also"></a>Se også

[Justere varekost](inventory-how-adjust-item-costs.md)  
[Avstem lagerkost med finans](finance-how-to-post-inventory-costs-to-the-general-ledger.md)  
[Bruk jobbkøer til å planlegge oppgaver](admin-job-queues-schedule-tasks.md)  
[Finne sider og informasjon med Fortell meg](ui-search.md)  
[Arbeide med [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  