---
title: Feilsøking av Shopify- og Business Central-synkronisering
description: Lær hva du gjør hvis noe går galt under synkroniseringen av data mellom Shopify og Business Central
ms.date: 08/19/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 30118, 30119, 30120,
author: edupont04
ms.author: andreipa
ms.reviewer: solsen
ms.openlocfilehash: 47b0d72283b4d017bb522c3e71f6c61501b59d5b
ms.sourcegitcommit: 38b1272947f64a473de910fe81ad97db5213e6c3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/29/2022
ms.locfileid: "9361945"
---
# <a name="troubleshooting-shopify-and-business-central-synchronization"></a>Feilsøking av Shopify- og Business Central-synkronisering

Det er mulig å støte på situasjoner der du må feilsøke problemer når du synkroniserer data mellom Shopify og [!INCLUDE[prod_short](../includes/prod_short.md)]. Denne siden definerer feilsøkingstrinnene for enkelte vanlige scenarioer som kan oppstå.

## <a name="logs"></a>Logger

Hvis en synkroniseringsoppgave mislykkes, kan du aktivere loggføring ved å aktivere/deaktiver **Loggposter** på siden **Shopify-butikkort**. Deretter kan du manuelt utløse synkroniseringen av oppgaver og se gjennom logger.

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-loggposter**. Velg deretter den relaterte koblingen.
2. Velg den tilknyttede loggposten, og åpne siden **Shopify-loggpost**.
3. Gå gjennom forespørsel, statuskode og beskrivelse og svarverdier.

Husk senere å slå av logging for å unngå negativ innvirkning på ytelsen og øke størrelsen på databasen.

Fra siden **Shopify-loggposter** kan du utløse sletting av alle loggposter eller de som er eldre enn sju dager.

## <a name="data-capture"></a>Dataregistrering

Uavhengig av innstillingene **Logg aktivert** blir noen Shopify-svar alltid loggførte slik at du kan undersøke eller laste dem ned ved hjelp av siden **Dataregistreringsliste**.

Velg handlingen **Hentede Shopify-data** på en av følgende sider:

- **Shopify-ordre**
- **Shopify-ordreoppfyllelse**
- **Shopify-ordreleveringskostnader**
- **Shopify-ordretransaksjoner**
- **Shopify-utbetalinger**
- **Shopify-betalingstransaksjoner**
- **Shopify-transaksjoner**

## <a name="reset-sync"></a>Tilbakestill synkronisering

For optimal ytelse importerer koblingen bare kunder, produkter og ordrer som er opprettet eller endret siden siste synkronisering. På siden **Shopify-butikkort** finnes det funksjoner som endrer dato/klokkeslett for siste synkronisering, eller tilbakestille den fullstendig. Denne funksjonen sikrer at alle data synkroniseres i stedet for bare endringer siden forrige synkronisering, når synkroniseringen kjøres.

Denne funksjonen gjelder bare synkroniseringer fra Shopify til [!INCLUDE[prod_short](../includes/prod_short.md)]. Den kan være nyttig hvis du må gjenopprette slettede data, for eksempel produkter, kunder eller slettede ordrer.

## <a name="request-the-access-token"></a>Be om tilgangstokenet

Hvis [!INCLUDE[prod_short](../includes/prod_short.md)] ikke vil koble til Shopify-kontoen, kan du prøve å be om tilgangstokenet fra Shopify. Denne forespørselen kan være nødvendig hvis det er en rotasjon av sikkerhetsnøkler eller endringer i nødvendige tillatelser (omfang).

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-butikker**. Velg den relaterte koblingen.
2. Velg butikken du vil hente tilgangstokenet for for å åpne siden **Shopify-butikkort**.
3. Velg handlingen **Be om tilgang**.
4. Hvis du blir bedt om det, logger du deg på Shopify-kontoen.

**Har tilgangsnøkkel**-veksleknappen blir aktivert.

### <a name="verify-and-enable-permissions-to-make-http-requests-when-running-in-a-non-production-environment"></a>Kontroller og aktiver tillatelser for å foreta HTTP-forespørsler når du kjører i et ikke-produksjonsmiljø

Shopify-koblingsutvidelsen krever tillatelse til å utføre HTTP-forespørsler for å fungere skikkelig. Når du tester i en sandkasse, er HTTP-forespørslene forbudt for alle utvidelser.

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **utvidelsesbehandling**, og velg den relaterte koblingen.
2. Velg utvidelsen *Shopify-kobling*.
3. Velg handlingen **Konfigurer** for å åpne siden **Utvidelsesinnstilling**.
4. Kontroller at vekslebryteren **Tillat HTTPClient-forespørsler** er aktivert.

## <a name="rotate-the-shopify-access-token"></a>Roter Shopify-tilgangstokenet

De følgende fremgangsmåtene beskriver hvordan du roterer tilgangstokenet som brukes av Shopify-koblingen for å få tilgang til Shopify-nettbutikken.

### <a name="in-shopify"></a>I Shopify

1. Fra **Shopify-administratoren** går du til [Apper](https://www.shopify.com/admin/apps).
2. Velg **Slett** i raden med **Dynamics 365 Business Central**-appen.
3. Velg **Slett** i meldingen som vises.

### <a name="in-prod_short"></a>I [!INCLUDE[prod_short](../includes/prod_short.md)]

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Shopify-butikker**. Velg den relaterte koblingen.
2. Velg butikken du vil rotere tilgangstokenet for for å åpne siden **Shopify-butikkort**.
3. Velg handlingen **Be om tilgang**.
4. Hvis du blir bedt om det, logger du deg på Shopify-kontoen, ser gjennom personvern og tillatelser, og deretter velger du knappen **Installer app**.

## <a name="known-issues"></a>Kjente problemer

*Bokføringsgruppe – firma* kan ikke være null eller tom. Det må finnes en verdi i kundefeltet. Slik korrigerer du:

På siden **Shopify-butikkort** fyller du ut feltet **Kundemalkode** med malen som har **Bokføringsgruppe – firma** fylt ut. Kundemalen brukes ikke bare til oppretting av kunder, men også for beregning av salgspris og oppretting av salgsdokumenter.

### <a name="importing-data-to-your-shopify-shop-isnt-enabled-go-to-the-shop-card-to-enable-it"></a>Import av data til Shopify-butikk er ikke aktivert. Gå til butikkortet for å aktivere det

I vinduet **Shopify-butikkort** aktiverer du veksleknappen **Tillat datasynkronisering til Shopify**.  Denne vekslingen er ment å beskytte nettbutikken fra å motta demodata fra [!INCLUDE[prod_short](../includes/prod_short.md)].

## <a name="see-also"></a>Se også

[Kom i gang med koblingen for Shopify](get-started.md)