---
title: Konfigurere ny selskaper | Microsoft-dokumentasjon
description: "Du kan konfigurere og tilpasse et nytt selskap som du har opprettet. Hvis du vil finjustere implementeringen, fortsetter du i tre faser for å fullføre konfigurasjonen."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/06/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: b9e701f102f1a2fc7ccbd4882dfec37f65cfe3b7
ms.contentlocale: nb-no
ms.lasthandoff: 03/22/2018

---
# <a name="configure-new-companies"></a>Konfigurere nye selskaper
Hvis du vil konfigurere et nytt selskap i løsningsimplementeringen, følger du vanligvis tre faser. I den første fasen importerer du konfigurasjonspakken, som er en .rapidstart-fil med konfigurasjonsinformasjon. I den andre fasen endrer du konfigurasjonsinformasjonen og bruker den deretter på det nye selskapet. Du ser gjennom og retter eventuelle feil i siste fase.  

Fremgangsmåtene nedenfor forutsetter at du har opprettet og lagret en konfigurasjonspakke. Hvis du vil ha mer informasjon, kan du se [Klargjøre en konfigurasjonspakke](admin-how-to-prepare-a-configuration-package.md).  

Fremgangsmåtene nedenfor forutsetter at du har initialisert og åpnet det nye selskapet og at du bruker rollesenteret for RapidStart Services-implementerer.

## <a name="to-import-a-configuration-package"></a>Slik importerer du en konfigurasjonspakke:  
1. Åpne det nye selskapet i [!INCLUDE[d365fin](includes/d365fin_md.md)]-databasen.  
2. Velg ikonet ![Søk etter side eller rapport](media/ui-search/search_small.png "Ikonet Søk etter side eller rapport"), angi **Konfigurasjonspakker**, og velg deretter den relaterte koblingen.  
3. Velg handlingen **Importer pakke**.  
4. Naviger til plasseringen hvor du har lagret pakkefilen for .rapidstart-konfigurasjonen, og velg deretter **Åpne**.  
5. Velg ikonet ![Søk etter side eller rapport](media/ui-search/search_small.png "Søk etter side eller rapport"), angi **Selskapsopplysninger**, og velg deretter den relaterte koblingen. Skriv inn informasjon om firmaet på kortet med selskapsopplysninger. Ta med informasjon, for eksempel bankinformasjon. Du kan også angi en logo for selskapet.  

Alle tabeller som du har angitt for inkludering i det nye selskapet, importeres. På dette tidspunktet kan du bruke pakkedataene i databasen eller justere og endre tabelldataene for å oppfylle kundespesifikasjonene.  

## <a name="to-apply-package-data"></a>Slik bruker du pakkedata:  
1. Velg ikonet ![Søk etter side eller rapport](media/ui-search/search_small.png "Ikonet Søk etter side eller rapport"), angi **Konfigurasjonsforslag**, og velg deretter den relaterte koblingen.  
2. Velg en tabell du vil endre data for, og velg deretter handlingen **Bruk data**. Velg **Ja**-knappen for å bekrefte.
3. For å bekrefte at dataene nå er i databasen og at programmet er fullført går du tilbake til vinduet **Konfigurer forslag**, og velg handlingen **Databasedata**.  

> [!NOTE]  
>  Når du bruker data, kan du bare se dem i databasen. De er ikke lenger i pakken.  

## <a name="to-modify-and-apply-package-data"></a>Endre og bruke pakkedata  
1. Velg ikonet ![Søk etter side eller rapport](media/ui-search/search_small.png "Ikonet Søk etter side eller rapport"), angi **Konfigurasjonsforslag**, og velg deretter den relaterte koblingen.  
2. Velg en tabell du vil endre data for, og velg deretter handlingen **Pakkedata**.  
3. Utfør endringene i vinduet **Konfigurer pakkeposter**. Du kan for eksempel slette alternativer som ikke gjelder.  
4. Velg **Bruk data**-handlingen, og velg deretter **OK**-knappen.  
5. For å bekrefte at dataene nå er i databasen og at programmet er fullført går du tilbake til vinduet **Konfigurer forslag**, og velg handlingen **Databasedata**.  

## <a name="to-locate-and-identify-a-configuration-error"></a>Slik finner og identifiserer du en konfigurasjonsfeil:  
Det finnes visse typer feil som kan oppstå når du bruker dataene på en database. Den vanligste feilen er at nødvendige relaterte tabeller ikke ble inkludert. Du løser slike feil i konfigurasjonsforslaget.

1. Velg ikonet ![Søk etter side eller rapport](media/ui-search/search_small.png "Ikonet Søk etter side eller rapport"), angi **Konfigurasjonspakker**, og velg deretter den relaterte koblingen.  
2. Velg pakken du vil se gjennom, og velg deretter den **Rediger**-handlingen.  

    Enhver tabell som inneholder feil, er uthevet. Antall pakkefeil vises i feltet **Antall pakkefeil**.  

3. Velg feltet **Antall pakkefeil** for å åpne vinduet **Konfigurer pakkeposter**, som viser postene med feil.  

### <a name="to-fix-an-error"></a>Slik retter du en feil:  
1. Åpne selskapet som er basert på konfigurasjonspakkenå.  
2. Velg ikonet ![Søk etter side eller rapport](media/ui-search/search_small.png "Ikonet Søk etter side eller rapport"), angi **Konfigurasjonsforslag**, og velg deretter den relaterte koblingen.  
3. Rett feil, for eksempel å legge til manglende relaterte tabeller i forslaget.  
4. Legg til tabellene i den eksisterende konfigurasjonspakken, eller opprett en ny pakke som bare inneholder de nye tabellene. Hvis du vil ha mer informasjon, kan du se [Klargjøre en konfigurasjonspakke](admin-how-to-prepare-a-configuration-package.md).  
5. Åpne det nye selskapet som du implementerer konfigurasjonen for.  
6. Importere konfigurasjonspakken.  

    > [!NOTE]  
    >  Hvis du importerer den samme pakken på nytt, kan du overskrive eventuelle endringer av data du allerede har gjort. Derfor vil du kanskje legge til nye tabeller i en ny pakke og importere denne i stedet.  

7. Bruke dataene i databasen, som beskrevet i delen Endre og bruke pakkedata.

## <a name="see-also"></a>Se også  
[Bruke konfigurasjoner for nye selskaper](admin-apply-configuration-to-new-companies.md)  
[Konfigurere et selskap med RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administrasjon](admin-setup-and-administration.md)
