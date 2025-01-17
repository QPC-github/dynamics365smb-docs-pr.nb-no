---
title: Betalingsavstemming med Envestnet Yodlee Bank Feeds-utvidelsen
description: 'Beskriver Envestnet Yodlee Bank Feeds-utvidelsen, som kobles til bankkonti, slik at du raskt kan avstemme betalinger.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'app, add-in, manifest, customize, stream, bank account link'
ms.search.form: '1450, 1451, 1452, 1453, 1454, 1458, 1460,'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="the-envestnet-yodlee-bank-feeds-extension" />Envestnet Yodlee Bank Feeds-utvidelsen

Hvis du raskt vil avstemme betalinger til bankkonti, lar tjenesten Envestnet Yodlee Bank Feeds deg koble systembankkontoen din til nettbankkontoen. Dette betyr at det siste bankkontoutdraget automatisk eller manuelt mates inn i avstemmingskladden, noe som sikrer at du alltid behandler de siste betalingene med minimal risiko for feil.

Envestnet Yodlee Bank Feeds-tjenesten støttes bare i USA og Canada.

> [!NOTE]
> Envestnet Yodlee Bank Feeds-tjenesten støttes bare i den elektroniske versjonen av Business Central. Hvis du vil bruke denne funksjonaliteten lokalt, må du hente en cobrand-konto fra Envestnet Yodlee.<br /><br />
> Envestnet Yodlee Bank Feeds-tjenesten støttes bare i USA og Canada.
> Det er bare banker som befinner seg i disse landene, som støttes, selv om banker fra andre land kan vises i vinduet for valg av bank Envestnet Yodlee Bank Feeds i [!INCLUDE[prod_short](includes/prod_short.md)].

> [!IMPORTANT]
> På grunn av det nye direktivet for betalingstjenester i Europa (PSD2), vil du ikke lenger kunne importere bankkontoutdrag fra banker i Stobritannia i [!INCLUDE[prod_short](includes/prod_short.md)] etter 14. september 2019. Vi undersøker muligheten for å tilby denne funksjonen igjen senere.

Envestnet Yodlee Bank Feeds-tjenesten gir følgende fordeler:

* Fjerner behovet for manuell registrering.
* Forbedrer effektivitet og nøyaktighet når du utfører betalingsavstemming.
* Støtter et stort antall banker.
* Gir oppdatert informasjon om banktransaksjoner fra [!INCLUDE[prod_short](includes/prod_short.md)].
* Støtter manuelle og automatiske bankfeeder.
* Tillater outsourcing av betalingsavstemming til en regnskapsfører ved å gi tilgang til bankkontoutdrag.

## <a name="available-bank-feeds" />Tilgjengelige bankfeeder

Du kan kontrollere om en bank er støttet, ved å definere og koble til Envestnet Yodlee Bank Feeds-tjenesten. Banken vil vises i oversikten hvis den støttes av Envestnet Yodlee.

Hvis du vil ha mer informasjon, kan du se [Konfigurere Envestnet Yodlee Bank Feeds-tjenesten](bank-how-setup-bank-statement-service.md).

## <a name="see-also" />Se også

[Tilpasse [!INCLUDE[prod_short](includes/prod_short.md)] ved hjelp av utvidelser](ui-extensions.md)  
[Utligne betalinger automatisk og avstemme bankkonti](receivables-apply-payments-auto-reconcile-bank-accounts.md)  
[Arbeid med [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
