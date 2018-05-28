---
title: "Feilsøke integrering med Microsoft Flow| Microsoft-dokumentasjon"
description: "Feilsøke hvordan du kan gjøre Financials-dataene tilgjengelige som en datakilde og angi en OData-URL-adresse til webtjenestene dine for å utvikle automatisk arbeidsflyt."
documentationcenter: 
author: SusanneWindfeldPedersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: workflow, Odata, Power App, SOAP
ms.date: 01/25/2018
ms.author: solsen
ms.translationtype: HT
ms.sourcegitcommit: e7dcdc0935a8793ae226dfc2f9709b5b8f487a62
ms.openlocfilehash: 68355bc0b4afe4fcdd92f9cdb190d4b5c0d845df
ms.contentlocale: nb-no
ms.lasthandoff: 03/22/2018

---
# <a name="troubleshooting-integration-with-microsoft-flow---request-url-too-long"></a>Feilsøke integrering med Microsoft Flow – URL-forespørselen er for lang
Du kan bruke dine [!INCLUDE[d365fin](includes/d365fin_md.md)]-data som en del av en arbeidsflyt i Microsoft Flow.  

> [!NOTE]  
>   Du må ha en gyldig konto med [!INCLUDE[d365fin](includes/d365fin_md.md)] og med Flow.  

Hvis du oppretter en Microsoft Flow ved hjelp av [!INCLUDE[d365fin](includes/d365fin_md.md)]-kontakten, kan du få en feilmelding som angir at den forespurte URL-adressen er for lang når du har opprettet flyten, slik som dette: **RequestUriTooLong**.

## <a name="cause"></a>Årsak
En flyt ser etter endringer i dataene dine, slik at den kan utløses. Når du fastslår om dataene er endret, sammenligner koblingene hurtigbufferdata med de nye dataene som forespørres fra kilden.  

Hvis dataforespørselen oppretter en URL-adresse som er for lang, vil den mislykkes. Vanlige årsaker kan være:
- Vanligvis kildetabeller med flere enn 250 rader
- Kildetabeller som inneholder flere tusen poster

## <a name="workaround"></a>Løsning
Følg denne fremgangsmåten for å unngå dette.
1. Velg å redigere flyten som mislykkes.
2. Vis **Vis avanserte alternativer** på flytutløser.
3. I feltet **Hopp over antall** angir du antall poster som skal utelates.  
Hvis tabellen du bruker for eksempel har 4 000 poster, angir du 4 000 som antall poster å hoppe over.
4. Oppdater flyten.

> [!NOTE]  
> Koblingen er for øyeblikket i betaversjon. Oppdateringer for hvordan dataendringer er rettet for fremtidige versjoner.


## <a name="see-also"></a>Se også
[Bruke [!INCLUDE[d365fin](includes/d365fin_md.md)] i en automatisk arbeidsflyt](across-how-use-financials-data-source-flow.md)  
[Komme i gang](product-get-started.md)  
[Importere forretningsdata fra andre økonomisystemer](upload-data.md)  
[Administrere brukere og tillatelser](ui-how-users-permissions.md)    
[Konfigurere [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Finans](finance.md)  
