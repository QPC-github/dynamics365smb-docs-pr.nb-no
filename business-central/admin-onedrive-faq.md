---
title: Vanlige spørsmål om OneDrive for Business
description: Få svar på enkelte vanlige spørsmål om å arbeide med OneDrive for Business og Business Central.
author: brentholtorf
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'OneDrive, integration, share, browser'
ms.date: 09/09/2022
ms.author: bholtorf
---
# <a name="onedrive-for-business-faq" />Vanlige spørsmål om OneDrive for Business

[!INCLUDE [online_only](includes/online_only.md)]

Denne artikkelen besvarer noen av spørsmålene du kan ha om å arbeide med OneDrive og [!INCLUDE [prod_short](includes/prod_short.md)].

## <a name="does-this-work-with-all-includeprodshortincludesprodshortmd-clients" />Fungerer dette med alle [!INCLUDE[prod_short](includes/prod_short.md)]-klienter?

Ja. Du kan åpne filer i OneDrive fra [!INCLUDE[prod_short](includes/prod_short.md)]-mobilappene når du viser kortopplysninger i Microsoft Teams, eller til og med fra Outlook-tillegget.  

## <a name="is-onedrive-the-same-as-sharepoint-for-storing-files" />Er OneDrive det samme som SharePoint for lagring av filer?

Som en del av Microsoft 365-abonnementet ditt, gir organisasjonen deg OneDrive, din fillagring i skyen. OneDrive er privat som standard, der du organiserer innholdet og velger hvilke filer eller mapper som skal deles og med hvem. I SharePoint gir imidlertid et filbasert repositorium i skyen som deles med andre i organisasjonen.  

## <a name="does-includeprodshortincludesprodshortmd-support-consumer-onedrive" />Støtter [!INCLUDE[prod_short](includes/prod_short.md)] OneDrive for forbruker?

Nei. Denne integreringen er utelukkende beregnet for OneDrive for Business og støtter bare arbeidskontoen din. 

## <a name="are-all-onedrive-for-business-plans-supported" />Støttes alle OneDrive for Business-planer?

[!INCLUDE[prod_short](includes/prod_short.md)] støtter ikke frittstående planer for OneDrive for Business. OneDrive må kjøpes som en del av en Microsoft 365 Business- eller Enterprise-plan. Hvis du vil ha mer informasjon, kan du se [Sammenlign priser og planer på skybasert OneDrive-lagring](https://www.microsoft.com/microsoft-365/onedrive/compare-onedrive-plans?market=af&activetab=tab:primaryr2).  

## <a name="where-can-i-see-onedrive-service-health" />Hvor kan jeg se tilstanden til OneDrive-tjenesten?

Administratorer kan få tilgang til instrumentbordet for tjenestetilstand som en del av Microsoft 365-administrasjonssenteret. Instrumentbordet omfatter OneDrives tjenestetilgjengelighet. Gå til [https://admin.microsoft.com/Adminportal/Home?#/servicehealth](https://admin.microsoft.com/Adminportal/Home?#/servicehealth).
 
## <a name="is-onedrive-integration-available-to-includeprodshortincludesprodshortmd-on-premises" />Er OneDrive-integrering tilgjengelig for [!INCLUDE[prod_short](includes/prod_short.md)] lokalt?

Ja, men i motsetning til [!INCLUDE[prod_short](includes/prod_short.md)] online krever det tilleggsoppsett. Hvis du vil ha mer informasjon, kan du se [Konfigurering av Business Central On-Premises](admin-onedrive-integration-onpremises.md).  

## <a name="does-includeprodshortincludesprodshortmd-on-premises-connect-with-sharepoint-server" />Bruker [!INCLUDE[prod_short](includes/prod_short.md)] lokalt tilkobling med SharePoint Server?

Nr. Denne distribusjonskombinasjonen støttes ikke selv om SharePoint Server har Mine områder aktivert.  

## <a name="does-includeprodshortincludesprodshortmd-online-connect-with-sharepoint-server" />Bruker [!INCLUDE[prod_short](includes/prod_short.md)] online tilkobling med SharePoint Server?

Nr. Denne distribusjonskombinasjonen støttes ikke selv om SharePoint Server har Mine områder aktivert.  

## <a name="how-does-this-work-in-an-organization-with-multiple-environments" />Hvordan fungerer dette i en organisasjon med flere miljøer?

Integreringen antar at selskapsnavn er unike i alle [!INCLUDE[prod_short](includes/prod_short.md)]-miljøer. Når selskapsnavn er unike på tvers av organisasjonen, kopierre OneDrive filen til en mappe som er oppkalt etter det gjeldende selskapet når du åpner en fil. Hvis selskapsnavn ikke er unike i miljøer, blir filer fra identiske selskapsnavn plassert i samme mappe.  

## <a name="weve-changed-company-name-what-happens-to-my-previous-files" />Vi har endret selskapsnavnet. Hva skjer med mine tidligere filer?

[!INCLUDE[prod_short](includes/prod_short.md)] overfører ikke filer du har åpnet tidligere, automatisk i OneDrive til den nye mappen. Når du har gitt nytt navn til selskapet, kopierer handlingen Åpne i OneDrive filer til en mappe med det nye selskapsnavnet.   

## <a name="when-attaching-files-to-includeprodshortincludesprodshortmd-how-do-i-pick-a-file-from-onedrive" />Når jeg legger ved filer i [!INCLUDE[prod_short](includes/prod_short.md)], hvordan jeg velger jeg en fil fra OneDrive?

[!INCLUDE[prod_short](includes/prod_short.md)] inneholder ikke en skyfilvelger. Du må laste ned filen fra OneDrive til enheten og deretter laste den opp til [!INCLUDE[prod_short](includes/prod_short.md)]. 

## <a name="i-want-to-open-files-in-sharepoint-instead-how-do-i-do-this" />Jeg vil åpne filer i SharePoint i stedet. Hvordan gjør jeg dette?

[!INCLUDE[prod_short](includes/prod_short.md)] inneholder ikke funksjoner for å kopiere filer til SharePoint og åpne dem fra et SharePoint-bibliotek. Kontakt Microsoft-partneren din for å forstå alternativene, eller søk etter apper på AppSource.  

## <a name="how-do-i-turn-off-integration-to-onedrive" />Hvordan slår jeg av integrering med OneDrive?

Kjør veiledningen for assistert oppsett for **OneDrive-oppsett**, og slå av bryterne for **Bruk OneDrive for appfunksjoner** og **Bruk OneDrive for systemfunksjoner**. 

## <a name="should-i-use-the-sharepoint-connection-setup-page-to-connect-to-sharepoint" />Skal jeg bruke siden Tilkoblingsoppsett for SharePoint til å koble til SharePoint?

Dette er en eldre funksjon der alle [!INCLUDE[prod_short](includes/prod_short.md)]-filer fra alle brukere sendes til én enkelt SharePoint-mappe. Vi anbefaler at du ikke konfigurerer hurtigfanen for delte dokumenter på siden for **Oppsett for SharePoint-tilkobling**, fordi denne siden er [avskrevet](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#microsoft-sharepoint-connection-setup) og vil bli fjernet i lanseringsbølge 2 for 2023, versjon 23.0.  Vi anbefaler at du bruker **OneDrive-oppsettet** i stedet.  

## <a name="which-version-of-includeprodshortincludesprodshortmd-supports-onedrive" />Hvilken versjon av [!INCLUDE[prod_short](includes/prod_short.md)] støtter OneDrive?

Integrering med OneDrive ble tilgjengelig i lanseringsbølge 2 for 2021.  

## <a name="a-namefeaturesawhich-features-are-affected-by-onedrive-integration" /><a name="features"></a>Hvilke funksjoner påvirkes av OneDrive-integrasjon?

I assistert oppsettsveiledning for **OneDrive-oppsett** for oppsett av OneDrive-integrasjon kan du aktivere eller deaktivere funksjoner for håndtering av Business Central-filer i OneDrive. Funksjonene deles mellom to alternativer:

|Alternativ|Description|
|------|----------|
|**Bruk OneDrive for appfunksjoner**|Hvis du aktiverer dette alternativet, gjøres handlingene **Åpne i OneDrive** og **Del** tilgjengelige på filer i Business Central, for eksempel filer som er knyttet til dokumenter eller i innboksen i rapporten. Med disse handlingene kan brukerne kopiere, åpne og dele filer i OneDrive. Hvis du vil ha mer informasjon, kan du se [Åpne og dele Business Central-filer i OneDrive](across-share-onedrive.md).
|**Bruk OneDrive for systemfunksjoner**|Hvis du aktiverer dette alternativet, aktiveres følgende funksjoner:<ul><li> Handlingene **Åpne i Excel** og **Rediger i Excel** på listesider kopierer automatisk Excel-filen til OneDrive og åpner den deretter i Excel Online. Hvis du vil ha mer informasjon, kan du se [Vis og rediger i Excel](across-work-with-excel.md).</li><li> Sending av en rapport til en Excel- eller Word-fil, kopieres filen automatisk til OneDrive, og deretter åpnes den i Excel eller Word på nettet. Hvis du vil ha mer informasjon, kan du se [Lagre en rapport til en fil](ui-work-report.md#saving-a-report-to-a-file).|

## <a name="will-microsoft-continue-to-improve-the-integration-to-onedrive" />Vil Microsoft fortsette å forbedre integreringen til OneDrive?

Hos Microsoft hører vi konstant på tilbakemelding fra våre mange brukerfellesskap og agerer på de mest populære forslagene. Hvis du vil vite mer om hva som kommer for integreringer med Microsoft 365-apper, kan du se [Lanseringsplanen for Dynamics 365](/dynamics365-release-plan/2021wave1).  

Hvis du ønsker å delta i å forbedre OneDrive-forbedring , eller hvis du har et forslag som vil forbedre fildeling og samarbeid i [!INCLUDE[prod_short](includes/prod_short.md)], kan du legge til et forslag eller stemme på eksisterende forslag på [https://aka.ms/BusinessCentralIdeas](https://aka.ms/BusinessCentralIdeas).

## <a name="troubleshooting" />Feilsøking

Denne delen gir informasjon om hvordan du kan identifisere og løse problemer som kan oppstå når du bruker OneDrive med [!INCLUDE[prod_short](includes/prod_short.md)].  

### <a name="business-central-cant-find-my-onedrive" />Business Central finner ikke min OneDrive

Når du får meldingen «Finner ikke plasseringen til OneDrive for Business. Kontakt partneren din for å konfigurere dette»., må du kontrollere om brukeren har åpnet OneDrive minst én gang. Hvis brukeren ikke har det, kan du be vedkommende om å gå til portal.office.com/onedrive for å konfigurere det. Det kan ta litt tid. Hvis meldingen fremdeles vises etter 24 timer, kontakter du kundestøtte.  
 
### <a name="im-having-problems-sharing-from-outlook" />Jeg har problemer med å dele fra Outlook

Se [Kan ikke dele OneDrive-filer fra Outlook.com](https://support.microsoft.com/en-us/office/can-t-share-onedrive-files-from-outlook-com-05d4cb21-40a2-40e3-b111-82cddb82d22f) på Microsoft Kundestøtte.

### <a name="actions-open-in-onedrive-and-share-are-missing" />Handlinger som er åpne i OneDrive og del, mangler

Det finnes et par ting du kan kontrollere:

- Kontroller at programfunksjonene for OneDrive er aktivert i assistert oppsettveiledninge for **OneDrive-oppsett**. Se [Konfigurer OneDrive ved hjelp av OneDrive-oppsett](admin-onedrive-integration.md#configure-onedrive-using-onedrive-setup).
- Kontroller at Microsoft OneDrive er sett til **Godta** på siden **Status for personvernerklæringer**. Se [Status for personvernerklæringer](privacy-notices-status.md).

## <a name="see-also" />Se også

[Business Central og OneDrive-integrering](across-onedrive-overview.md)  
[Administrere OneDrive-integrering med Business Central](admin-onedrive-integration.md)  
[Åpne Business Central-filer i OneDrive](across-share-onedrive.md)  
