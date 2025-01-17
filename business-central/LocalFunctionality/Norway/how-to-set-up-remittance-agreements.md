---
title: 'Sette opp remitteringsavtaler [NO]'
description: Du må undertegne en avtale om remittering med banken når du oppretter elektroniske betalinger i den norske versjonen av Business Central.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.search.form: '15000000, 15000002, 15000004, 15000006, 15000007, 15000010'
ms.date: 06/21/2021
ms.author: edupont
---
# <a name="set-up-remittance-agreements-in-the-norwegian-version" />Sett opp remitteringsavtaler i den norske versjonen

Du må undertegne en avtale om remittering med banken når du oppretter elektroniske betalinger. Du kan sette opp mer enn én remitteringsavtale hvis du har en avtale med to eller flere banker. For hver avtale må du spesifisere én eller flere kontoer som betalingen skal utføres fra. Du må opprette en remitteringskonto for hver konto. For mer informasjon, se [Sette opp remitteringskontoer](how-to-create-remittance-accounts.md).  

## <a name="to-set-up-a-remittance-agreement" />Slik setter du opp en remitteringsavtale

1.  Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](../../media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Remitteringsavtaleoversikt**, og velg deretter den relaterte koblingen.  
2.  Velg handlingen **Ny**.  
3.  I hurtigfanen **Generelt** fyller du ut feltene som beskrevet i tabellen nedenfor.  

    |Felt|Description|  
    |---------------------------------|---------------------------------------|  
    |**Kode**|Angi avtalekoden fra banken.|  
    |**Beskrivelse**|Angi et navn for avtalen, for eksempel navnet på banken.|  
    |**Betalingssystem**|Velg hvilket betalingssystem som skal benyttes. Betalingssystemene inkluderer **DnB Telebank**, **K-LINK**, **SparNett**, **Fokus Bank**, **Postbanken**, **Annen bank**, og **BBS**.|  

4.  I hurtigfanen **Bank** fyller du ut feltene som beskrevet i tabellen nedenfor.  

    |Felt|Description|  
    |---------------------------------|---------------------------------------|  
    |**Operatørnr.**|Angi operatøropplysningene som du har mottatt fra banken.|  
    |**Foretaksnr./avtalenr.**|Angi selskapsopplysningene som du har mottatt fra banken.|  
    |**Divisjon**|Angi divisjonsopplysningene som du har mottatt fra banken.|  
    |**Seneste sekvensnr.**|Angi det siste sekvensnummeret.|  
    |**Seneste daglige sekvensnr.**|Angi det seneste daglige sekvensnummeret.|  
    |**Seneste utlesing**|Angi datoen for seneste utlesing.|  

5.  I hurtigfanen **BBS** fyller du ut feltene som beskrevet i tabellen nedenfor.  

    |Felt|Description|  
    |---------------------------------|---------------------------------------|  
    |**BBS Kundeenhet-ID**|Angi IDen til avtalen med Bankenes Betalingssentral (BBS). Denne koden formidles av BBS.|  
    |**Seneste BBS-oppdragsnr.**|Angir løpenummeret som ble brukt da betalingen ble sendt til BBS.|  

6.  I hurtigfanen **Send** fyller du ut feltet som beskrevet i tabellen nedenfor.  

    |Felt|Description|  
    |---------------------------------|---------------------------------------|  
    |**Filnavn for betalingsfil**|Angi banen til og navnet på filen som inneholder det elektroniske oppdraget som ble sendt til banken.|  

7.  I hurtigfanen **Motta** fyller du ut feltene som beskrevet i tabellen nedenfor.  

    |Felt|Description|  
    |-----------|---------------------------------------|  
    |**Lagre returfil**|Velg dette alternativet for å gi navn til returfilen automatisk etter at den er importert uten feil.|  
    |**Mottaksretur kreves**|Velg dette alternativet for å kontrollere at den første returrapporten importeres.|  
    |**Returfiler brukes ikke**|Velg dette alternativet hvis du ikke vil bruke returfiler til godkjenning og betalingsoppgjør. Du kan bruke denne funksjonen hvis du ikke vil oppdatere betalinger med returinformasjon fra banken.|  
    |**Avventkode ved avvisning**|Angi koden for å oppdatere en avvist leverandørpost. Posten merkes som **Avvent**. Dette betyr at den etter avvisning ikke legges til på nytt i remitteringsforslaget.<br /><br /> Hvis kodefeltet er tomt, merkes ikke posten som **Avvent**. Dette betyr at den etter avvisning kan legges til på nytt i et remitteringsforslag.|  

8.  I hurtigfanen **Finans** fyller du ut feltet som beskrevet i tabellen nedenfor.  

    |Felt|Description|  
    |---------------------------------|---------------------------------------|  
    |**Nytt bilag pr. felt**|Angi hvordan dokumenter nummereres når betalinger bokføres. Alternativene er **Dato**, **Leverandør**, og **Angis på konti**.|  

9. Velg handlingen **Returfiloppsett-liste**.  
10. På siden **Returfiloppsett - liste** velger du handlingen **Ny**.  
11. Skriv inn filnavnet for returfilen i feltet **Filnavn for returfil**.  

    > [!NOTE]  
    >  Du må angi minst ett filnavn for hver mottaksretur, avvist retur og avregningsretur. Kontakt banken for å finne ut hvilke navnekonvensjoner den benytter.  

12. Velg **OK**.  

## <a name="see-also" />Se også
 [Elektroniske betalinger til leverandører i Norge](electronic-payments-to-vendors-in-norway.md)   
 [Opprette remitteringskontoer](how-to-create-remittance-accounts.md)   
 [Angi leverandører for remittering](how-to-set-up-vendors-for-remittance.md)   
 [Mottakerreferansekoder](recipient-reference-codes.md)   
 [Opprette remitteringsforslag](how-to-create-remittance-suggestions.md)   
 [Opprette manuelle remitteringsoppdrag](how-to-create-manual-remittance-payments.md)   
 [Definere betalingslinjeinformasjon](how-to-set-up-payment-line-information.md)   
 [Kontrollere remitteringsoppdrag](how-to-test-remittance-payments.md)   
 [Eksportere remitteringsoppdrag](how-to-export-remittance-payments.md)   
 [Typer betalingsreturfiler](types-of-payment-returns-files.md)   
 [Importere betalingsreturdata](how-to-import-payment-return-data.md)   
 [Slette remitteringsoppdrag](how-to-delete-remittance-payment-orders.md)   
 [Remitteringsfeil](remittance-errors.md)   
 [Vise remitteringsfeilkoder](how-to-view-remittance-error-codes.md)   
 [Annullere betalinger](how-to-cancel-payments.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
