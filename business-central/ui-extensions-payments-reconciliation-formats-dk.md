---
title: Utvidelsen Betalinger og avstemminger (Danmark)
description: Utvidelsen gjør det enkelt å eksportere filer som er formatert på forhånd for å oppfylle bankens krav til elektroniske innsendinger.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: 'extension, bank, formats'
ms.date: 06/24/2021
ms.author: bholtorf
---

# <a name="the-payments-and-reconciliations-dk-extension" />Utvidelsen Betalinger og avstemminger (Danmark)

Betal fort og uten feil ved å eksportere filer som er formatert spesielt for utveksling med leverandører eller banken. Filene øker hastigheten til betalings- og avstemmingsprosessen, og du unngår feil som kan skje når du angir informasjonen på bankens webområde manuelt.  

Utvidelens støtter filformater for flere dansk banker. Når du eksporterer betalingsinformasjon til en fil, sørger utvidelsen for at dataen får formatet som kreves av banken. Formatene er blant annet Bankdata-V3, BEC, SDC og FIK, som brukes av mange forskjellige banker, og noen formater som er tilpasset bestemte banker, for eksempel Danske Bank og Nordea. Utvidelsen inkluderer også noen formater for import og avstemming av bankkontoutdrag.  

> [!Note]
> Hvis du vil bruke utvidelsen, må du vite formatet banken eller leverandøren krever. Noen banker eller leverandører oppgir disse opplysningene på deres nettsteder. Det kan imidlertid være nødvendig å kontakte deres kundetjeneste for å få informasjonen.  

## <a name="supported-bank-formats" />Bankformater som støttes
Utvidelsen kan bruke følgende filformater for betalingsfiler:  

* BANKDATA V3  
* BEC INDLAND  
* BEC CSV  
* DANSKEBANK CMKV  
* DANSKEBANK CMKXKSX  
* DANSKEBANK  
* FIK71  
* NORDEA-ERHVERV CSV  
* NORDEA  
* NORDEA-UNITEL V3  
* SDC  
* SDC CSV  

## <a name="to-set-up-the-extension" />Slik konfigurerer du filtypen

Det er noen trinn for å komme i gang.  

* Tillat eksport av betalingsdata. For å beskytte dataene, er ikke dette lett tilgjengelig.  
* Definere kjøps- og leverandørkonti slik at du ikke trenger eksterne bilagsnumre på fakturaer. Du kan bruke referansenummeret for å referere til en bestemt faktura ved behov.  
* Angi betalingsmåten for hver leverandør. Betalingsmåter definerer hvordan du betaler fakturaer fra leverandøren. For eksempel i banken, kontant, med sjekk eller til konto.  
* Angi formatet som skal brukes for hver av bankkontiene dine. Det kan for eksempel være NORDEA, DANSKEBANK, SDC og så videre.  

I tillegg må du tilordne leverandørene til et innenlands **Bokføringsgruppe - firma** og en **Bokføringsgruppe - leverandør**. Innstillingen land/region for leverandøren må være Danmark (dansk). Hvis du vil ha mer informasjon, kan du se [Definere bokføringsgrupper](finance-posting-groups.md).  

### <a name="to-allow-includeprodshortincludesprodshortmd-to-export-payment-data" />Tillat [!INCLUDE[prod_short](includes/prod_short.md)]å eksportere betalingsdata.

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Utbetalingskladd** og velg den relaterte koblingen.  
2. Velg **Bank**-bunken på siden **Rediger betalingskladd**.  
3. Velg avmerkingsboksen **Tillat betalingseksport**.  

### <a name="to-specify-a-payment-method-for-a-vendor" />Angi betalingsmåten for en leverandør

Tabellen nedenfor viser kombinasjoner av FIK og GIRO betalingsmåter som støttes av [!INCLUDE[prod_short](includes/prod_short.md)].

|Kombinasjon|Type 01 | Type 04 | Type 71 | Type 73 |
|----|--------|---------|---------|---------|
|Girokontonr. eller FIK kreditornr.? | Girokontonr. | Girokontonr. | FIK Kreditornr. | FIK Kreditornr.|
|Tillater melding til mottaker? | Ja |Nei |Nei | Ja |
|Inneholder et betalingsreferansenummer? | Nei | Ja, 16 sifre. | Ja, 15 sifre. | Nei|

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angir **Leverandører** og velger den relaterte koblingen.  
2. Åpne kortet, utvid **Betalinger**-kategorien, velg betalingsmåte i **Betalingsmåte** -feltet.  
3. Avhengig av hva du velger, må du fylle ut andre felt. Se i tabellen over for en beskrivelse av kombinasjonene.  

### <a name="to-specify-the-format-to-use-for-a-bank-account" />Angi formatet som skal brukes for en bankkonto.

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Bankkonti**, og velg deretter den relaterte koblingen.  
2. Åpne kortet for bankkontoen.  
3. I **Betalingseksportformat**-feltet velger du formatet for eksportfilen.  

## <a name="choosing-the-fik-or-giro-payment-information-for-vendor-invoices" />Velge FIK eller Girobetalingsinformasjon for leverandørfakturaer

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Kjøpsfakturaer**, og velg deretter den relaterte koblingen.
2. Velg leverandør. Husk at det må være en dansk leverandør med en adresse i Danmark.
3. Opprette en faktura. Feltene **Betalingsmåte** og **Leverandørnummer** er fylt ut på grunnlag av innstillingene på leverandørkortet. De kan endres.
4. I **Betalingsreferanse**-vinduet angir du nummeret med 15 sifre som står på leverandørens faktura.  

    > [!Tip]
    > Du trenger kun å legge inn de 11 siste sifrene i nummeret. [!INCLUDE[prod_short](includes/prod_short.md)] legger til fire nuller i begynnelsen av nummeret.  

5. Bokfør fakturaen.

## <a name="to-use-the-extension-to-export-payment-data" />Bruke utvidelsen til å eksportere betalingsdata

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Utbetalingskladder** og velg den relaterte koblingen.  
2. Velg **Betalingskladdforslag - leverandør**.  

    > [!Tip]
    > Hvis du vil eksportere bare bestemte betalinger, må du bruke alternativene for å filtrere data.  

3. Ved behov kan du legge til filtre for å eksportere kun bestemte betalinger.  
4. I **Bankbetalingstype**-feltet velger du **Elektronisk betaling**.  
5. Velg handlingen **Eksporter**.  

## <a name="see-also" />Se også

[Tilpasse Business Central for [!INCLUDE[prod_short](includes/prod_short.md)]med utvidelser](ui-extensions.md)  
[Innkreve betalinger med SEPA direct debit](finance-collect-payments-with-sepa-direct-debit.md)  
[Arbeid med finanskladder](ui-work-general-journals.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
