---
title: Definere selskapskonfigurasjon | Microsoft-dokumentasjon
description: "Implementeringsprosessen starter med Business Central-løsningen som kreves. Du grupperer all denne informasjonen i konfigurasjonspakker."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/05/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: eeca45a36e38ab80a63156995a2f11466262d512
ms.contentlocale: nb-no
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-company-configuration"></a>Definere selskapskonfigurasjon
Implementeringsprosessen begynner med Microsoft-partneren. Partneren er ansvarlig for å tenke gjennom konfigurasjonsdetaljer og lage en pakke som kunden enkelt kan bruke. Før du oppretter et nytt selskap, bør du planlegge hvordan det skal konfigureres. Du må vurdere grunnleggende oppsettsdata og hvilke typer data [!INCLUDE[d365fin](includes/d365fin_md.md)]-løsningen vil kreve. Du grupperer all denne informasjonen i konfigurasjonspakker.

RapidStart Services gir deg også verktøy som du vil bruke til å overføre dine eldre data, for eksempel kunder og leverandører.  

Vi anbefaler at du oppretter konfigurasjonspakker der de fleste av oppsettstabellene allerede er utfylt, slik at kunder bare trenger å ende noen få innstillinger etter at pakken tas i bruk. Når du for eksempel oppretter et nytt selskap, blir tabellene **Nummerserie** og **Nr.serielinje** fylt ut med et sett med nummerserier og startnumre. Den tilsvarende **Nr. serie**-feltet i oppsettstabellene er fylles også ut automatisk. Du trenger ikke å utføre oppgaver som å angi nummerserier og andre grunnleggende oppsettsdata. Du kan også manuelt endre alle standarddata som brukes sammen med RapidStart Services, ved hjelp av konfigurasjonsforslaget.  

Konfigurasjonspakkene bygger på et forhåndskonfigurert selskap. Når du har definert et selskap som oppfyller dine behov, kan du opprette en konfigurasjonspakke som inneholder relevante data fra dette selskapet. Deretter kan du bruke den når du oppretter et nytt selskap som skal konfigureres på samme måte.  

For å forenkle import av hoveddata, for eksempel kunde- og leverandørinformasjon, kan du bruke konfigurasjonsmaler. Konfigurasjonsmaler inneholder et sett med standardinnstillinger, som tilordnes automatisk til postene som importeres til [!INCLUDE[d365fin](includes/d365fin_md.md)].

Tabellen nedenfor beskriver en sekvens av oppgaver, og har koblinger til emner som beskriver dem.

|**Hvis du vil**|**Se**|  
|------------|-------------|  
|Planlegge en selskapskonfigurasjon ved å fylle ut konfigurasjonsforslaget.|[Behandle selskapskonfigurasjon i et forslag](admin-how-to-manage-company-configuration-in-a-worksheet.md)|  
|Opprett en konfigurasjonspakke, tilpass en pakke, tilordne tabeller til en pakke, se gjennom eller rediger eksisterende kundedata, opprette det nye selskapet og flytt deretter testdata til produksjonsmiljøet.|[Klargjøre en konfigurasjonspakke](admin-how-to-prepare-a-configuration-package.md)| 

## <a name="see-also"></a>Se også  
[Konfigurere et selskap med RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administrasjon](admin-setup-and-administration.md)
