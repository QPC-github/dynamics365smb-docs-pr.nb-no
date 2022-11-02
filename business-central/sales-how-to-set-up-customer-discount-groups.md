---
title: Definer kunderabattgrupper
description: Lær hvordan du definerer kunderabattgrupper og oppretter salgslinjerabatter for disse gruppene.
author: rubenseishima
ms.service: dynamics365-business-central
ms.topic: article
ms.date: 06/08/2022
ms.author: a-reishima
ms.openlocfilehash: fc2e5af5792a4c212c56b2e8a8a28b3b48ecff33
ms.sourcegitcommit: 7b6d70798b4da283d1d3e38a05151df2209c2b72
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/12/2022
ms.locfileid: "8950525"
---
# <a name="set-up-customer-discount-groups"></a>Definer kunderabattgrupper

Du kan definere salgslinjerabatter for en gruppe kunder i stedet for å bruke dem enkeltvis.

**Kunderabattgrupper** fungerer på samme måte som [kundeprisgrupper](sales-how-to-set-up-customer-price-groups.md), men de kan kombineres med varerabattgrupper for å kunne sette linjerabatter til mange varer for utvalgte kunder på en rask måte.

## <a name="create-sales-line-discounts-for-a-customer-group"></a>Opprett salgslinjerabatter for en kundegruppe

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Kunderabattgrupper**, og velg deretter den relaterte koblingen.
2. På siden **Kunderabattgrupper** velger du **Ny** for å opprette en ny rabattgruppe og gir den et navn under kolonnen **Kode** og legger til en beskrivelse.
3. Velg **Naviger**-handlingen, og velg **Salgslinjerabatter**.
4. Fyll ut kolonnen **Salgskode** med rabattgruppen du opprettet på forrige side.
5. Fyll ut feltene **Type** (vare eller varerabattgruppe), **Kode**, **Enhetskode** og **Linjerabatt-%**.
6. Hvis kundegruppen må kjøpe et minimumsantall for å få rabatten som er avtalt, fyller du ut feltet **Minimumsantall**.
7. Hvis det er nødvendig, angir du **Startdato** og **Sluttdato** for rabattgruppen.
8. Hvis det er relevant, kan du også angi **valutakoden** eller **variantkoden** etter at du har [tilpasset kolonnene](ui-personalization-user.md).

Gjenta trinn 4 til 8 for hver vare eller varerabattgruppe du vil opprette en salgslinjerabatt for.

## <a name="assign-a-customer-to-a-discount-group"></a>Tildel en kunde til en rabattgruppe

Når du har definert kunderabattgruppene, kan du angi kunderabattgruppekodene på kundekortene.

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angir **Kunder** og velger den relaterte koblingen.
2. Åpne **kundekortet** for en kunde du vil skal være del av en kunderabattgruppe.
3. Velg gruppekoden i feltet **Kunderabattgruppe** på hurtigfanen **Fakturering**.

## <a name="see-also"></a>Se også

[Salg](sales-manage-sales.md)  
[Sette opp salg](sales-setup-sales.md)  
[Registrering av spesielle salgspriser og rabatter](sales-how-record-sales-price-discount-payment-agreements.md)  
[Konfigurering av kundeprisgrupper](sales-how-to-set-up-customer-price-groups.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]