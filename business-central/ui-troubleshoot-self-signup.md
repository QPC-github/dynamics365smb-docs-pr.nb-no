---
title: "Feilsøke registrering for Self-Service | Microsoft-dokumentasjon"
description: "Finn ut mer om de vanligste årsakene til at du kanskje ikke kan fullføre registreringen for Business Central og hvordan du kan løse dem."
author: SusanneWindfeldPedersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 1595f5020a0da7b2899ba056f135ff5e88985d38
ms.contentlocale: nb-no
ms.lasthandoff: 03/22/2018

---
# <a name="troubleshooting-self-service-sign-up"></a>Feilsøke registrering for Self-Service
Registrering for [!INCLUDE[d365fin](includes/d365fin_md.md)] er enkelt og kan gjøres svært raskt. Du kan opprette en gratis konto selv om du er en eksisterende organisasjon. Denne artikkelen beskriver problemer som kan oppstå under registrering.

## <a name="what-email-address-can-i-use-with-business-central"></a>Hvilken e-postadresse kan jeg bruke med Business Central?
[!INCLUDE[d365fin](includes/d365fin_md.md)] krever at du bruker en e-postadresse for arbeid eller skole for å registrere deg. [!INCLUDE[d365fin](includes/d365fin_md.md)] støtter ikke e-postadressene levert av e-posttjenester for forbrukere eller telekommunikasjonsleverandører. Dette inkluderer outlook.com, hotmail.com, gmail.com og andre.

Hvis du prøver å registrere deg med en personlig e-postadresse, får du en melding om å bruke en e-postadresse for arbeid eller skole.

## <a name="troubleshooting"></a>Feilsøking
I mange tilfeller kan du registrere deg for [!INCLUDE[d365fin](includes/d365fin_md.md)] ved å følge registreringsprosessen nedenfor. Det er imidlertid flere grunner til hvorfor du ikke kanskje ikke kan fullføre registrering for Self-Service. Tabellen nedenfor viser en oversikt over noen av de vanligste årsakene som du ikke kanskje kan fullføre registreringen og metoder for midlertidig løsning av disse problemene.

| Symptom/feilmelding | Årsak og løsning |
| --- | --- |
| For e-postadresser for Office 365 som ikke er registrert i et land som støttes, kan du få en melding som følgende, under registrering:<br /><br />**Dette fungerte ikke. Vi støtter ikke landet eller området ennå.** |[!INCLUDE[d365fin](includes/d365fin_md.md)] støtter for øyeblikket bare e-postkontoer for Office 365 som er registrert i et begrenset antall markeder. Hvis du vil ha mer informasjon, kan du se [Tilgjengelighet i områder](#regional-availability). |
| Personlige e-postadresser, som nancy@gmail.com, støttes ikke. Du får en feilmelding som følgende, under registrering:<br /><br />**Du har angitt en personlig e-postadresse: Skriv inn e-postadressen for arbeid, slik at vi kan lagre firmaets data på en sikker måte.**<br> eller <br> **Dette ser ut som en personlig e-postadresse. Skriv inn adressen til arbeid, slik at vi kan koble til andre i firmaet. Og ikke bekymre deg. Vi deler ikke adressen din med andre.** |[!INCLUDE[d365fin](includes/d365fin_md.md)] støtter ikke e-postadressene levert av e-posttjenester for forbrukere eller telekommunikasjonsleverandører. Hvis du vil fullføre registreringen, kan du prøve på nytt med en e-postadresse som er tilordnet arbeid eller skole. Hvis du fremdeles ikke kan registrere deg og er villig til å fullføre et mer avansert oppsett, kan du registrere for et nytt prøveabonnement for Office 365 og bruke den e-postadressen til å registrere deg. |
| .gov- eller .mil e-postadresser Du mottar en melding som følgende, under registrering:<br /><br />**[!INCLUDE[d365fin](includes/d365fin_md.md)] ikke tilgjengelig: [!INCLUDE[d365fin](includes/d365fin_md.md)] er ikke tilgjengelig for brukere med e-postadressene .gov eller .mil på dette tidspunktet. Bruk en annen e-postadresse for arbeid eller kom tilbake senere.** <br>eller <br>**Vi kan ikke fullføre registreringen din. Det ser ut som [!INCLUDE[d365fin](includes/d365fin_md.md)] ikke er tilgjengelig for arbeid eller skole.** |[!INCLUDE[d365fin](includes/d365fin_md.md)] støtter ikke .gov- eller .mil-adresser på dette tidspunktet. |
| Registrering for Self-service er ikke aktivert. Du får en feilmelding som følgende, under registrering:<br /><br />**Vi kan ikke fullføre registreringen din. IT-avdelingen har deaktivert registrering for [!INCLUDE[d365fin](includes/d365fin_md.md)]. Kontakt dem for å fullføre registreringen.** <br>eller <br> **Dette ser ut som en personlig e-postadresse. Skriv inn adressen til arbeid, slik at vi kan koble til andre i firmaet. Og ikke bekymre deg. Vi deler ikke adressen din med andre.** |Organisasjonens systemansvarlige har deaktivert registrering for Self-service for [!INCLUDE[d365fin](includes/d365fin_md.md)]. Hvis du vil fullføre registreringen, kontakter du systemansvarlig og ber om å følge instruksjonene på siden nedenfor, slik at eksisterende brukere kan registrere seg for [!INCLUDE[d365fin](includes/d365fin_md.md)] og nye brukere kan bli med i eksisterende leietaker. Du kan også oppleve dette problemet hvis du registrerte deg for Office 365 via en partner. |
| E-postadressen er ikke en Office 365-ID. Du får en feilmelding som følgende, under registrering:<br /><br />**Vi finner deg ikke på contoso.com. Bruker du en annen ID på arbeid eller skole? Prøv å logge på med denne, og hvis det ikke fungerer, kan du kontakte IT-avdelingen.** |Organisasjonen din bruker ID-er til å logge på Office 365 og andre Microsoft-tjenester, som er forskjellig fra e-postadressen din. E-postadressen kan for eksempel være Nancy.Smith@contoso.com, men ID-en er nancys@contoso.com. For å fullføre registreringen bruker du ID-en organisasjonen har tilordnet for å logge på Office 365 eller andre Microsoft-tjenester. Hvis du ikke vet hva dette er, kontakter du systemansvarlig. Hvis du fremdeles ikke kan registrere deg og kan fullføre et mer avansert oppsett, kan du registrere for et nytt prøveabonnement for Office 365 og bruke den e-postadressen til å registrere deg. |
| Hvis Office 365-kontoen er registrert i et land som støttes og du registrerer deg for [!INCLUDE[d365fin](includes/d365fin_md.md)] når du er i et annet land, vises en melding under registreringen:<br /><br />**Dette fungerte ikke. Vi støtter ikke landet eller området ennå.**| Organisasjonens Office 365-abonnement er registrert i et bestemt land i administrasjonsportalen for Office 365. Registreringsopplevelsen for [!INCLUDE[d365fin](includes/d365fin_md.md)] bruker språket og de nasjonale innstillingene som gjeldende nettleser bruker, og derfor kan du få du feilmelding selv om du er i et land som støttes. Be IT-ansvarlig om å kontrollere landet som er angitt i organisasjonsprofilen i [Office 365administrasjonsportalen](https://portal.office.com/adminportal/home#/companyprofile). Det kan hende du må bruke en annen konto for [!INCLUDE[d365fin](includes/d365fin_md.md)].|

## <a name="regional-availability"></a>Tilgjengelighet i området
[!INCLUDE[d365fin](includes/d365fin_md.md)] er for øyeblikket tilgjengelige i følgende markeder:

*   Europa:
  * Østerrike
  * Belgia
    * Danmark
  * Tyskland
  * Finland
  * Frankrike
  * Italia
  * Nederland
  * Spania
  * Sverige
  * Sveits
  * Storbritannia
*   Nord-Amerika:
  * Canada
  * USA


## <a name="see-also"></a>Se også
[Velkommen til [!INCLUDE[d365fin](includes/d365fin_long_md.md)]](index.md)  
[Arbeide med [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
