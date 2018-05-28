---
title: Opprette varekort for varer eller tjenester | Microsoft-dokumentasjon
description: "Du kan opprette varekort for tjenester du selger som timer, og for fysiske produkter, for eksempel monteringsvarer, ferdigvarer, komponenter eller råvarer, du selger fra lageret."
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: item, finished good, component, raw material, assembly item
ms.date: 08/31/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: ea9b4a6310df319df06d02c53b9d6156caaee24f
ms.openlocfilehash: ac7664480d5a2db4642ecc2cb830c4d7022fb53b
ms.contentlocale: nb-no
ms.lasthandoff: 03/28/2018

---
# <a name="register-new-items"></a>Registrere nye varer
Varer, blant andre produkter, er grunnlaget for virksomheten din, varene eller tjenestene du handler med. Hver vare må være registrert som et varekort.

Varekort inneholder informasjonen som er nødvendig for å kjøpe, lagre, selge, levere og gjøre rede for varer.

Varekortet kan være av typen **Beholdning** eller **Tjeneste** for å angi om varen er en fysisk enhet eller arbeidstidsenhet. Bortsett fra noen av feltene som er relatert til de fysiske aspektene av en vare, fungerer alle felt på et varekort på samme måte for lagervarer og tjenester. Hvis du vil ha mer informasjon om hvordan du selger en vare, kan du se [Selge produkter](sales-how-sell-products.md) eller [Fakturere salg](sales-how-invoice-sales.md).

En vare kan struktureres som en overordnet vare med underliggende underordnede varer i en stykkliste. I [!INCLUDE[d365fin](includes/d365fin_md.md)] kan en stykkliste være en monteringsstykkliste eller en produksjonsstykkliste, avhengig av bruken. Hvis du vil ha mer informasjon, kan du se [Arbeide med stykklister](inventory-how-work-BOMs.md).

> [!NOTE]  
>   Hvis det finnes varemaler for ulike varetyper, vises et vindu når du oppretter et nytt kundekort der du kan velge en passende mal. Hvis det bare finnes én varemal, brukes alltid denne malen i nye varekort.

Hvis du kjøper den samme varen fra flere leverandører, kan du knytte disse leverandørene til varekortet. Leverandørene vises deretter i vinduet **Vare/leverandør-katalog**, slik at du enkelt kan velge en annen leverandør.

## <a name="to-create-a-new-item-card"></a>Opprette et nytt varekort
1. Velg ikonet ![Søk etter side eller rapport](media/ui-search/search_small.png "Søk etter side eller rapport"), angi **Varer**, og velg deretter den relaterte koblingen.  
2. I vinduet **Varer** velger du handlingen **Ny**.

    Hvis det bare finnes én varemal, åpnes et nytt varekort med noen felt som er fylt ut med informasjon fra malen.
3. I vinduet **Velg en mal for en ny vare** velger du malen som du vil bruke for det nye varekortet.
4. Velg **OK**. Det åpnes et nytt varekort med noen felt som er fylt ut med informasjon fra malen.
5. Fortsette med å fylle ut eller endre feltet på varekortet etter behov. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> I feltet **Lagermetode** kan du definere hvordan varens enhetskost beregnes, ved å lage prognoser over vareflyten i selskapet. Fem lagermetoder er tilgjengelige, avhengig av varetypen. Hvis du vil ha mer informasjon, kan du se [Designdetaljer: Kostmetoder](design-details-costing-methods.md).
>
> Hvis du velger **Gjennomsnitt**, blir enhetskosten for en vare beregnet som den gjennomsnittlige enhetskosten på hvert tidspunkt etter et kjøp. Lageret verdisettes basert på antakelsen om at alle beholdninger selges samtidig. Med denne innstillingen kan feltet **Enhetskost** for å vise en historikk over transaksjoner som gjennomsnittskosten beregnes fra, i vinduet **Oversikt over beregning av gjennomsnittskost**.

I hurtigfanen **Pris og bokføring** kan du vise spesialpriser eller rabatter som skal gis for varen hvis bestemte kriterier oppfylles, for eksempel kunde, minimumsordreantall eller sluttdato. Hver rad representerer en spesialpris eller linjerabatt. Hver kolonne representerer et vilkår som må brukes for å garantere spesialprisen du angir i feltet **Enhetspris**, eller linjerabatten du angir i feltet **Linjerabatt-%**. Hvis du vil ha mer informasjon, kan du se [Registrere avtaler om salgspris, rabatt og betaling](sales-how-record-sales-price-discount-payment-agreements.md).

Varen er nå registrert, og varekortet er klart til å brukes på kjøps- og salgsdokumenter.

Hvis du vil bruke dette varekortet som en mal når du oppretter nye varekort, kan du lagre det som en mal. Hvis du vil ha mer informasjon, kan du se følgende avsnitt:

## <a name="to-save-the-item-card-as-a-template"></a>Lagre varekortet som en mal
1. I vinduet **Varekort** velger du handlingen **Lagre som mal**. **Varemal**  -vinduet åpnes og viser varekortet som en mal.
2. Fyll ut feltene etter behov. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Hvis du vil bruke dimensjoner i maler, velger du handlingen **Dimensjoner**. **Dimensjonsmaler**-vinduet åpnes med alle dimensjonskoder som er definert for varen.
4. Rediger eller angi dimensjonskoder som skal gjelde for nye varekort som opprettes ved hjelp av malen.
5. Når du har fullført den nye varemalen, kan du velge **OK**-knappen.

Varemalen legges til i listen over varemaler, slik at du kan bruke den til å opprette nye varekort.

## <a name="to-set-up-multiple-vendors-for-an-item"></a>Slik definerer du flere leverandører for varer  
Hvis du kjøper den samme varen fra flere leverandører, må du angi opplysninger om hver enkelt leverandør av varen, for eksempel priser, leveringstid, rabatter og så videre.  

1.  Velg ikonet ![Søk etter side eller rapport](media/ui-search/search_small.png "Søk etter side eller rapport"), angi **Varer**, og velg deretter den relaterte koblingen.  
2.  Velg den aktuelle varen, og velg deretter handlingen **Rediger**.  
3.  Velg handlingen **Leverandører**.  
4.  Velg feltet **Leverandørnr.**, og velg leverandøren du vil definere for varen.  
5.  Fyll eventuelt ut de gjenværende feltene.  
6.  Gjenta trinn 2 til 5 for hver leverandør som du vil kjøpe varen fra.

Leverandørene vises nå i vinduet **Vare/leverandør-katalog**, som du åpner fra varekortet, slik at du enkelt kan velge en annen leverandør.

## <a name="see-also"></a>Se også
[Opprette nummerserier](ui-create-number-series.md)  
[Lager](inventory-manage-inventory.md)  
[Innkjøp](purchasing-manage-purchasing.md)  
[Salg](sales-manage-sales.md)  
[Arbeide med [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
