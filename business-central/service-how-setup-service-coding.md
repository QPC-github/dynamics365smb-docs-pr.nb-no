---
title: Definere koder for standardservicer
description: Lær hvordan du definerer koder for jevnlig utførte serviceaktiviteter med et forhåndsdefinert sett med servicelinjer.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'service, service item, service order, repairs, maintenance'
ms.date: 06/23/2021
ms.author: edupont
---

# <a name="set-up-standard-service-codes" />Definere standard servicekoder

Når du utfører typisk service, må du ofte opprette servicedokumenter som bruker servicelinjer som inneholder omtrent samme opplysninger. Hvis du vil gjøre det enkelt å opprette disse linjene, kan du definere standard servicekoder som er et forhåndsdefinert sett med servicelinjer. Når du velger koden i et servicedokument, angis linjene automatisk. Du kan angi så mange standard servicekoder du vil, og hver kode kan ha et ubegrenset antall servicelinjer av ulike typer, inkludert vare, ressurs, kostnad eller standardtekst, knyttet til seg. Det kan opprettes servicelinjer for hver standard servicekode i korter **Standard servicekode**. Du tilordner deretter standard servicekoder til servicevaregrupper på siden **Standard servicevaregruppekoder**. Senere, når du oppretter et servicedokument, kan du bruke handlingen **Hent standard servicekoder** for å legge til servicelinjer.  
  
> [!Tip]
> Du kan bruke samme metode for å opprette linjer i salgs- og kjøpsdokumenter. Hvis du vil ha mer informasjon, kan du se [Opprette gjentakende salgs- og kjøpslinjer](sales-how-work-standard-lines.md).  
  
## <a name="to-set-up-a-standard-service-code" />Slik definerer du standard servicekoder

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Standard servicekoder**, og velg deretter den relaterte koblingen.  
2. Fyll ut feltene etter behov. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Fyll ut servicelinjene som er koblet til denne servicekoden.  

## <a name="to-assign-a-standard-service-code-to-a-service-item-group" />Slik knytter du en standard servicekode til en servicevaregruppe

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Servicevaregrupper**, og velg deretter den relaterte koblingen.  
2. Fyll ut feltene etter behov. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Fyll ut servicelinjene som er koblet til denne servicekoden.  

## <a name="see-also" />Se også

[Servicebehandling](service-service.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
