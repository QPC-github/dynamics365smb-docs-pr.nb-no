---
title: Tilordne dokumentoppsett til kunder eller leverandører
description: Bruk dokumentoppsett til å kontrollere utseendet og formatet til dokumenter som fakturaer og ordrer du sender til kunder og leverandører.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'customized report, document layout, logo, personalize'
ms.search.form: '21, 9650'
ms.date: 04/07/2022
ms.author: edupont
---
# <a name="define-document-layouts-for-customers-and-vendors" />Definere dokumentoppsett for kunder og leverandører

Dokumentoppsett bruker rapportoppsett til å definere utseendet til dokumenter du sender til kunder og leverandører. Business Central tilbyr standardoppsett, men du kan også skreddersy egendefinerte oppsett for hver av forretningspartnerne dine. Hvis du vil ha mer informasjon, kan du se [Opprette og endre et egendefinert rapportoppsett](ui-how-create-custom-report-layout.md). Du velger standard og egendefinerte dokumentoppsett fra kunde- og leverandørkort ved å velge handlingen **Dokumentoppsett**. Verdien i **Bruk**-feltet definerer prosessen som dokumentoppsettet brukes for. For kunder kan du for eksempel bruke typene **Purring**, **Levering** og **Bekreftelse** for dokumentoppsett.

Ved hjelp av dokumentoppsett kan du også spare tid når du sender dokumenter til kunde- eller leverandørkontakter via e-post. For hvert oppsett du tilordner til kunden eller kontakten, kan du angi en eller flere e-postadresser for kontakter. Du kan for eksempel sende en faktura til kundens kjøps- og lagerkontakter. Det er enkelt å legge til e-postadresser for kontakter. På siden **Dokumentoppsett** lar handlingen **Velg e-post fra kontakter** deg velge fra en liste over e-postadresser for kontakter som du registrerte for kunden eller leverandøren. Du kan også legge til e-postadresser manuelt. Hvis du skriver inn flere adresser, skiller du dem med et semikolon og legger ikke til mellomrom mellom adressene.

Før du kan definere hvilket dokumentoppsett du vil bruke for hvilke prosesser, og hvilken kontakt du skal sende dokumentet til, må du laste alle tilgjengelige rapporter (dokumenter) fra siden **Rapportvalg**. Du kan raskt laste inn dokumentene ved hjelp av handlingen **Kopier fra rapportvalg** på siden **Dokumentoppsett**.

Trinnene nedenfor beskriver hvordan du definerer salgsdokumentoppsett fra siden **Kundekort**. For leverandører er trinnene de samme fra siden **Leverandørkort**.

## <a name="to-load-the-standard-document-layouts-for-sales-documents-for-a-customer" />Slik laster du inn standard dokumentoppsett for salgsdokumenter for en kunde

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angir **Kunder** og velger den relaterte koblingen.
2. Åpne siden **Kundekort** for kunden, og velg deretter handlingen **Dokumentoppsett**.
3. På siden **Dokumentoppsett** velger du handlingen **Kopier fra Rapportutvalg**.

Siden **Dokumentoppsett** viser alle oppsett som er tilgjengelige for salgsdokumenter. 

## <a name="to-select-a-custom-report-layout-to-use-for-the-sales-document-layout" />Slik velger du et egendefinert rapportoppsett som skal brukes for salgsdokumentoppsettet

Hvis du ikke allerede har opprettet et egendefinert rapportoppsett for dokumenttypen, må du gjøre det først. Hvis du vil ha mer informasjon, kan du se [Opprette og endre et egendefinert rapportoppsett](ui-how-create-custom-report-layout.md).

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angir **Kunder** og velger den relaterte koblingen.
2. Åpne siden **Kundekort** for kunden, og velg deretter handlingen **Dokumentoppsett**.
3. På siden **Dokumentoppsett**, på linjen for et rapportoppsett som du vil bruke et egendefinert oppsett for, velger du feltet **Beskrivelse av egendefinert oppsett**.
4. På siden **Egendefinerte rapportoppsett** velger du dokumentoppsettet du vil bruke for salgsdokumenttypen. Hvis du vil ha mer informasjon, kan du se [Opprette og endre et egendefinert rapportoppsett](ui-how-create-custom-report-layout.md).

## <a name="to-specify-which-contact-will-receive-which-document-layout-for-a-customer" />Slik angir du hvilken kontakt som mottar et dokumentoppsett for en kunde

Hvis du vil spare tid når du sender dokumenter til kunde- og leverandørkontakter via e-post, angir du e-postadressene i dokumentoppsett. Du kan for eksempel alltid sende kundeutdrag til regnskapskontaktene og salgsordrene til innkjøperne, eller bestillinger til leverandørselgere.

1. På siden **Dokumentoppsett**, på linjen for rapportoppsett som du vil sende til en bestemt kontakt for kunden, velger du handlingen **Velg e-post fra kontakter**.
2. På siden **Kontakter** velger du en eller flere kontakter, og deretter klikker du på **OK**.

## <a name="see-related-microsoft-trainingtrainingmoduleschange-documents-dynamics-365-business-central" />Se relatert [Microsoft-opplæring](/training/modules/change-documents-dynamics-365-business-central/)

## <a name="see-also" />Se også

[Oppdater egendefinerte rapportoppsett](ui-update-report-layouts.md)  
[Opprett og endre et egendefinert rapportoppsett](ui-how-create-custom-report-layout.md)  
[Importere og eksportere en egendefinert rapport eller et egendefinert dokumentoppsett](ui-how-import-and-export-report-layout.md)  
[Send dokumenter i e-post](ui-how-send-documents-email.md)  
[Håndtere rapportoppsett](ui-manage-report-layouts.md)  
[Arbeid med rapporter, satsvise jobber og XMLport-er](ui-work-report.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
