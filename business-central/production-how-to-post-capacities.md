---
title: Bokføre kapasiteter
description: 'Bokfør brukte kapasiteter som ikke er tilordnet produksjonsordren, i kapasitetskladden, og vis bokførte kapasiteter på siden for kapasitetsposter.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '5832, 99000802, 99000820'
ms.date: 03/08/2023
ms.author: edupont
---
# <a name="post-capacities" />Bokføre kapasiteter

I kapasitetskladden bokfører du brukte kapasiteter som ikke er tilordnet produksjonsordren. Vedlikeholdsarbeid må for eksempel tilordnes kapasitet, men ikke en produksjonsordre.  

## <a name="to-post-capacities" />Slik bokfører du kapasiteter

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Kapasitetskladder** og velg den relaterte koblingen.  
2. Fyll ut feltene **Bokføringsdato** og **Bilagsnr.**.  
3. I feltet **Type** angir du kapasitetstypen, enten **Produksjonsressurs** eller **Arbeidssenter**, du bokfører.  
4. I feltet **Nr.** angir du nummeret på produksjonsressursen eller arbeidssenteret.  
5. Skriv inn relevante opplysninger i de andre feltene, for eksempel **Starttidspunkt**, **Sluttidspunkt**, **Antall** og **Vrak**.  
6. Velg handlingen **Bokfør** for å bokføre kapasitetene.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## <a name="to-view-work-center-ledger-entries" />Slik viser du arbeidssenterposter:

På sidene **Arbeidssenterkort** og **Maskinsenterkort** kan du vise bokførte kapasiteter som et resultat av ferdige produksjonsordrer.    
1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Arbeidssentre**, og velg deretter den relaterte koblingen.  
2. Åpne det aktuelle **Arbeidssenter**-kortet fra listen, og velg handlingen **Kapasitetsposter**.  

    **Kapasitetsposter**-siden viser de bokførte postene fra arbeidssenteret i den rekkefølgen de ble bokført.   

## <a name="see-also" />Se også

[Produksjon](production-manage-manufacturing.md)  
[Definere produksjon](production-configure-production-processes.md)  
[Planlegging](production-planning.md)  
[Lager](inventory-manage-inventory.md)  
[Innkjøp](purchasing-manage-purchasing.md)  
[Arbeid med [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
