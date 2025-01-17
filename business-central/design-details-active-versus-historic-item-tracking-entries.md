---
title: Designdetaljer – Aktive kontra historiske varesporingsposter
description: 'Når deler av et dokumentlinjeantall bokføres, overføres bare dette antallet til varepostene og varesporingsnumrene.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/15/2021
ms.author: edupont
---
# <a name="design-details-active-versus-historic-item-tracking-entries" />Designdetaljer: Aktive kontra historiske varesporingsposter
Når deler av et dokumentlinjeantall bokføres, overføres bare dette bestemte antallet til varepostene og varesporingsnumrene. Du vil imidlertid ha tilgang til all relevant varesporingsinformasjon direkte fra den aktive dokumentlinjen. Det vil si at ikke bare vil du se postene som er knyttet til restantallet, men du vil også ha informasjon om enhetene som er bokført. Når du viser eller endrer siden **Varesporingslinjer**, vises det samlede innholdet i **Sporingsspesifikasjon**-tabellen (T336) og **Reservasjonspost**-tabellen (T337) i en midlertidig versjon av T336. Dette sikrer at historiske og aktive varesporingsdata er tilgjengelige som ett element.  

 Tabellen nedenfor viser hvordan T336 og T337 brukes i et scenario med kjøp. Tallene i fet representerer verdier som brukeren angir manuelt på siden **Varesporingslinjer**.  

 Trinn 1: Opprett en bestillingslinje med sju stykker med varesporingsnumre.  

||**Antall (lagerenhet)**|**Ant. som skal håndt.**|**Ant. som skal fakt. (l.enh.)**|**Håndtert antall (l.enh.)**|**Fakturert antall (l.enh.)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**T337**|7|0|0|0|0|  
|**T336**|0|0|0|0|0|  

 Trinn 2: Motta fire stykker.  

||**Antall (lagerenhet)**|**Ant. som skal håndt.**|**Ant. som skal fakt. (l.enh.)**|**Håndtert antall (l.enh.)**|**Fakturert antall (l.enh.)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Varesporingslinjer**-siden|7|**4**|**0**|0|0|  
|**T337**|3|0|0|0|0|  
|**T336**|4|0|0|4|0|  

 Trinn 3: Motta to stykker, og fakturer to stykker.  

||**Antall (lagerenhet)**|**Ant. som skal håndt.**|**Ant. som skal fakt. (l.enh.)**|**Håndtert antall (l.enh.)**|**Fakturert antall (l.enh.)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Varesporingslinjer**-siden|7|**2**|**2**|4|0|  
|**T337**|1|0|0|0|0|  
|**T336**|6|0|0|6|2|  

 Trinn 4: Motta ett stykk.  

||**Antall (lagerenhet)**|**Ant. som skal håndt.**|**Ant. som skal fakt. (l.enh.)**|**Håndtert antall (l.enh.)**|**Fakturert antall (l.enh.)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Varesporingslinjer**-siden|7|**1**|**0**|6|2|  
|**T336**|7|0|0|7|2|  

 Fakturere 5 enheter.  

||**Antall (lagerenhet)**|**Ant. som skal håndt.**|**Ant. som skal fakt. (l.enh.)**|**Håndtert antall (l.enh.)**|**Fakturert antall (l.enh.)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Varesporingslinjer**-siden|7|0|**5**|7|2|  
|**T336**|7|0|0|7|7|  

## <a name="see-also" />Se også
 [Designdetaljer: Varesporing](design-details-item-tracking.md)   
 [Designdetaljer: Side for varesporingslinjer](design-details-item-tracking-lines-window.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
