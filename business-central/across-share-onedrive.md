---
title: Bruk av OneDrive for Business med Business Central
description: Du kan bruke OneDrive for Business til å lagre, behandle og dele filer, for eksempel rapporter eller filvedlegg.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.workload: na
ms.search.keywords: ''
ms.date: 06/11/2021
ms.author: bholtorf
ms.openlocfilehash: 92896af6888ef5c39288d511e61d343d3e384a83
ms.sourcegitcommit: 6ad0a834fc225cc27dfdbee4a83cf06bbbcbc1c9
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/01/2021
ms.locfileid: "7589470"
---
# <a name="opening-business-central-files-in-onedrive"></a>Åpne Business Central-filer i OneDrive
[!INCLUDE[prod_short](includes/prod_short.md)] gjør det enkelt å lagre, behandle og dele filer med andre personer via OneDrive for Business. På de fleste sider der filer er tilgjengelige, for eksempel rapportinnboksen eller filer som er knyttet til poster, finner du en **Åpen i OneDrive**-handling.

:::image type="content" source="media/Open in OneDrive.PNG" alt-text="Åpne i OneDrive-handlingen":::

 
:::image type="content" source="media/OneDrive attachment.PNG" alt-text="Del fil vedlegg i OneDrive":::

## <a name="working-with-different-types-of-files"></a>Arbeid med forskjellige filtyper
Når du velger **Åpne i OneDrive**, identifiserer [!INCLUDE[prod_short](includes/prod_short.md)] Excel-, Word- og PowerPoint-filer og åpner dem i nettprogrammene, det vil si Excel online, Word online og PowerPoint online. Du kan sette inn merknader, redigere og samarbeide med andre uten å forlate nettleseren. 

For andre populære filtyper, for eksempel PDF-filer, tekstfiler og bilder inneholder OneDrive filvisningsprogrammer som tilbyr funksjoner for utskrift, deling og mer. Hvis en fil ikke kan vises i OneDrive, kan det hende du blir bedt om å laste den ned. 

## <a name="managing-multiple-copies-of-a-file"></a>Behandle flere kopier av en fil
Når du velger **Åpne i OneDrive**, kopieres filen fra [!INCLUDE[prod_short](includes/prod_short.md)] til mappen i OneDrive. Hvis du redigerer filen i OneDrive, vil kopiene av filen være forskjellig. Hvis du vil oppdatere [!INCLUDE[prod_short](includes/prod_short.md)] med den siste filen, fjerner du den eksisterende filen fra [!INCLUDE[prod_short](includes/prod_short.md)], og deretter laster du opp den siste kopien.

Når du i tillegg bruker åpne i OneDrive-handlingen og en fil med dette navnet finnes allerede i OneDrive, får du et valg i [!INCLUDE[prod_short](includes/prod_short.md)] om å erstatte filen eller beholde begge filene. Hvis du velger å beholde begge filene, kopieres den nye filen til OneDrive og filnavnet får et suffiks, for eksempel Varer (2).xlsx, og den opprinnelige filen endres ikke. 

Hvis du velger å erstatte filen, legges den nye filen til i versjonsloggen for denne filen. Den opprinnelige filen går ikke tapt, og du kan vise eller gjenopprette tidligere versjoner av filen. 

## <a name="accessing-your-onedrive"></a>Tilgang til OneDrive
Du får tilgang til OneDrive fra **Mine innstillinger**-siden ved å velge koblingen i **Skylagring**-feltet.

:::image type="content" source="media/my-settings-cloud-storage.PNG" alt-text="Skylagring-feltet i Mine innstillinger":::

<!--## Extending the Connection to OneDrive
You can create an extension and connect it to... For more information, see...-->

## <a name="see-also"></a>Se også
[Business Central og OneDrive-integrering](across-onedrive-overview.md)  
[Administrere OneDrive-integrering med Business Central](admin-onedrive-integration.md)  
[Vanlige spørsmål om OneDrive](admin-onedrive-faq.md)