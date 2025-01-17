---
title: Definer betingelser og grader for purringer
description: 'Finn ut hvordan du konfigurerer Business Central slik at du kan sende en påminnelse til en kunde om en betaling som er forfalt, og legge gebyrer til betalingen på grunn av forsinkelsen.'
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'payment due, debt, overdue, fee, charge, reminder'
ms.search.form: '431, 432, 436, 478'
ms.date: 02/09/2022
ms.author: edupont
---
# <a name="set-up-reminder-terms-and-levels" />Definer betingelser og grader for purringer

Du kan bruke purringer til å minne kunder på forfalte beløp. [!INCLUDE [reminder-terms](includes/reminder-terms.md)]

## <a name="reminder-terms" />Purrebetingelser

Hvis kunder har forfalte betalinger, må du angi når og hvordan du vil sende purring. I tillegg vil du kanskje belaste kundekontiene med renter eller gebyr. Du kan opprette så mange purrebetingelser du vil.  

> [!NOTE]
> Hvis du vil beregne rente på forfalte betalinger, kan du gjøre det når du oppretter purringer. Hvis du imidlertid bare vil beregne rente og informere kundene om dette uten å sende purringer, bør du bruke [rentenotaer](finance-setup-finance-charges.md). Du finner mer informasjon under [Purringer](receivables-collect-outstanding-balances.md#reminders) eller [Rentenotaer](receivables-collect-outstanding-balances.md#finance-charges).

### <a name="to-set-up-reminder-terms" />Slik definerer du purrebetingelser

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Purrebetingelser**, og velg deretter den relaterte koblingen.  
2. Fyll ut feltene etter behov. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  
3. Hvis du vil bruke flere kombinasjoner av purrebetingelser, definerer du en kode for hver kombinasjon.

## <a name="reminder-levels" />Purregrader

For hver purrebetingelseskode kan du definere et ubegrenset antall purregrader. Innstillingen fra grad 1 brukes første gang det opprettes en purring for en kunde. Når purringen utstedes, registreres gradnummeret i purrepostene som opprettes og kobles til de individuelle kundepostene. Hvis det er nødvendig å sende kunden en ny purring, kontrolleres alle purreposter som er koblet til åpne kundeposter, for å finne det høyeste gradnummeret. Betingelsene fra neste gradnummer vil deretter bli brukt i den nye purringen.

Hvis du oppretter flere purringer enn du har definert grader for, brukes betingelsene for den høyeste graden. Du kan opprette så mange purringer som er tillatt i henhold til feltet **Høyeste purregrad** i purrebetingelsene.

### <a name="to-set-up-reminder-levels" />Slik definerer du purregrader

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Purrebetingelser**, og velg deretter den relaterte koblingen.  
2. På siden **Purrebetingelser** velger du linjen med betingelsene du vil definere grader for, og deretter velger du **Grader**.  
3. Fyll ut feltene etter behov. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

    > [!TIP]
    > Innstillingen for feltet **Beregn renter** bestemmer om renter skal vises på purringen når purringen utstedes. Feltet **Bokfør rente** på siden **Purrebetingelsene** bestemmer imidlertid om den beregnede renten skal bokføres til finans- og kundekonti.
    >
    > Hvis du vil angi at renter skal beregnes, velger du feletet **Beregn renter**.

    For hver purregrad kan du også angi tilleggsgebyr både i LV og i utenlandsk valuta. Du kan definere mange tilleggsgebyr i fremmed valuta for hver kode på siden **Purregrad**.  

    Tilleggsgebyrene kan beregnes på tre ulike måter, som er definert av verdien i feltet **Tilleggsgebyr beregningstype**.  

    - **Fast**

        Gebyr beregnes basert på verdiene i feltene **Tilleggsgebyr** på linjen for selve purregraden.  
    - **Enkel dynamisk**

        Gebyr beregnes basert på verdiene i feltene på den relevante linjen på siden **Oppsett av tilleggsgebyr** for purregraden.
    - **Akkumulert dynamisk**

        Gebyr beregnes basert på verdiene i feltene på de kombinerte linjene på siden **Oppsett av tilleggsgebyr** for purregraden.

4. Velg handlingen **Valutaer**.
5. På siden **Valutaer for purregrad** definerer du en valutakode og et tilleggsgebyr for hver purregradskode og tilhørende purregradsnummer.

    > [!NOTE]  
    > Når du oppretter purringer i en fremmed valuta, brukes betingelsene for den fremmede valutaen du definerer her, til å opprette purringer. Hvis det ikke er definert noen betingelser for purringer i fremmed valuta, brukes purrebetingelsene for LV som er definert på siden **Purregrader**, og deretter konverteres de til den relevante valutaen.

    For hver purregrad kan du spesifisere tekst som skal skrives ut før (**Starttekst**) eller etter (**Sluttekst**), i postene i purringen.

6. Velg henholdsvis handlingen **Starttekst** eller **Sluttekst**, og fyll ut **Purretekst**-siden.
7. Hvis du vil sette inn beslektede verdier automatisk i den resulterende purreteksten, angir du plassholderne nedenfor i **Tekst** feltet.  

    |Plassholder|Verdi|  
    |-----------------|-----------|  
    |%1|Innholdet i **Bilagsdato**-feltet i purrehodet|  
    |%2|Innholdet i **Forfallsdato**-feltet i purrehodet|  
    |%3|Innholdet i feltet **Rentesats** på de relaterte rentenotabetingelsene|  
    |%4|Innholdet i **Restbeløp**-feltet i purrehodet|  
    |%5|Innholdet i **Rentebeløp**-feltet i purrehodet|  
    |%6|Innholdet i **Tilleggsgebyr**-feltet i purrehodet|  
    |%7|Purringens totalbeløp.|  
    |%8|Innholdet i **Purregrad**-feltet i purrehodet|  
    |%9|Innholdet i **Valutakode**-feltet i purrehodet|  
    |%10|Innholdet i **Bokføringsdato**-feltet i purrehodet|  
    |%11|Selskapsnavnet|  
    |%12|Innholdet i **Tilleggsgebyr per linje**-feltet i purrehodet|  

    Hvis du for eksempel skriver **Du skylder %9 %7, som forfaller den %2.**, vil den resulterende påminnelsen inneholde følgende tekst: **Du skylder 1 200,50 LV, som forfaller 02-02-2014.**

    > [!NOTE]
    > Forfallsdatoen beregnes i henhold til datoformelen som du angir. Hvis du vil ha mer informasjon, kan du se [Bruk datoformler](ui-enter-date-ranges.md#use-date-formulas).

Når du har definert purrebetingelsene (med tilleggsgrader og tekst), registrerer du én av kodene på hvert kundekort. Hvis du vil ha mer informasjon, kan du se [Registrere nye kunder](sales-how-register-new-customers.md).  

## <a name="see-related-microsoft-trainingtrainingmodulessend-reminders-dynamics-365-business-central" />Se relatert [Microsoft-opplæring](/training/modules/send-reminders-dynamics-365-business-central/)

## <a name="see-also" />Se også

[Innkreve utestående saldi](receivables-collect-outstanding-balances.md)  
[Send purringer om utestående saldoer](receivables-send-reminders.md)  
[Definer rentenotabetingelser](finance-setup-finance-charges.md)  
[Konfigurere finans](finance-setup-finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
