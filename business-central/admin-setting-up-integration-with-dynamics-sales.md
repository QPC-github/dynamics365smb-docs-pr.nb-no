---
title: Sette opp brukerkontoer for integrasjon med Microsoft Dataverse | Microsoft Docs
description: 'Lær hvordan du definerer brukerkontoene som appene bruker til å utveksle data, og som brukes til å få tilgang til og synkronisere data i appene.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 04/01/2021
ms.author: bholtorf
---
# Sette opp brukerkontoer for integrasjon med Microsoft Dataverse

Denne artikkelen gir en oversikt over hvordan du definerer brukerkontoene som er nødvendige for å integrere [!INCLUDE[prod_short](includes/cds_long_md.md)] med [!INCLUDE[prod_short](includes/prod_short.md)].

## Sette opp administratorbrukerkontoen

Når du skal definere tilkoblingen mellom [!INCLUDE[prod_short](includes/prod_short.md)] og [!INCLUDE[prod_short](includes/cds_long_md.md)], må du logge deg på [!INCLUDE[prod_short](includes/prod_short.md)] med en brukerkonto som er tildelt lisensen [!INCLUDE[prod_short](includes/prod_short.md)] Essential eller [!INCLUDE[prod_short](includes/prod_short.md)] Premium. Vi bruker denne kontoen én gang til å installere og konfigurere noen nødvendige komponenter.

> [!IMPORTANT]
> Under installasjonen blir du bedt om å oppgi legitimasjon for [!INCLUDE[prod_short](includes/cds_long_md.md)]-miljøet. Oppgi legitimasjonen for en konto som er en lisensiert bruker og tildelt til sikkerhetsrollen **Systemadministrator** i [!INCLUDE[prod_short](includes/cds_long_md.md)]-miljøet og den globale administratoren for leieren som miljøet tilhører. Denne kontoen trenger ikke lisens for [!INCLUDE[prod_short](includes/prod_short.md)] fordi den bare skal brukes til å gjøre installasjonsoppgaver i [!INCLUDE[prod_short](includes/cds_long_md.md)]-miljøet.
>
> Når tilkoblingsoppsettet er fullført, kan du fjerne denne [!INCLUDE[prod_short](includes/cds_long_md.md)]-brukeren. Integrasjonen fortsetter å bruke brukerkontoen som automatisk er opprettet spesielt for integrasjonen.

## Tillatelser og sikkerhetsroller for brukerkontoer i [!INCLUDE[prod_short](includes/cds_long_md.md)]

Baseintegrasjonsløsningen oppretter følgende roller i [!INCLUDE[cds_long](includes/cds_long_md.md)] for integreringen:

* **Integrasjonsadministrator**: Gjør at brukere kan administrere forbindelsen mellom [!INCLUDE[prod_short](includes/prod_short.md)] og [!INCLUDE[cds_long](includes/cds_long_md.md)]. Vanligvis bare dette bare tilordnet til den automatisk opprettede brukerkontoen for synkronisering.
* **Integrasjonsbruker**: Gjør at brukere får tilgang til synkroniserte data. Normalt tilordnes dette til den automatisk opprettede brukerkontoen for synkronisering og andre brukere som har behov for å vise eller få tilgang til de synkroniserte dataene.

> [!NOTE]
>
> Rollene **Integrasjonsadministrator** og **Integrasjonsbruker** må bare brukes av programbrukeren som kjører integreringen. Programbrukeren trenger ikke å ha lisensene [!INCLUDE[prod_short](includes/prod_short.md)] eller [!INCLUDE[cds_long](includes/cds_long_md.md)] tilordnet.

Når du installerer den grunnleggende løsningen, konfigurerer den tillatelser for integrasjonsbrukerkontoen. Hvis disse tillatelsene endres manuelt, kan du tilbakestille dem. Velg siden **Distribuer integreringsløsning på nytt** på siden **Dataverse-tilkoblingsoppsett** for å installere baseintegreringsløsningen på nytt. Dette trinnet distribuerer sikkerhetsrollen Business Central-integrasjon.

<!--
The following tables list the minimum permissions for the user accounts in [!INCLUDE[prod_short](includes/cds_long_md.md)].

### Minimum Permissions for the Administrator
The following table displays the minimum permissions on each tab for each security role that is required for the administrator user.

##### Customization
|Security Role|Access Level|Dynamics NAV 2018 and Earlier|Business Central <br> October 2018|Business Central <br> April 2019|
|----|----|-----|----|----|
|Model Driven App|Global|||Read|
|Plugin Assembly|Global|Read|Read|Read|
|Plugin Type|Global|Read|Read|Read|
|Relationship|Global|||Read|
|SDK Message|Global|Read|Read|Read|
|SDK Message Proessing Step|Global|Read|Read|Read|
|SDK Message Proessing Step Image|Global|Read|Read|Read|
|System From|Global|||Write|

##### Custom Entities
|Security Role|Access Level|Dynamics NAV 2018 and Earlier|Business Central <br> October 2018|Business Central <br> April 2020|
|----|----|-----|----|----|
|Business Central Account Statistics|Global|Read|Read|Read|
|Business Central Connection|Global|Create, Read, Write, Delete|Create, Read, Write, Delete|Create, Read, Write, Delete|
|Post Configuration|Global|||Write|

### Minimum Permissions for automatically created [!INCLUDE[prod_short](includes/prod_short.md)] Integration application user
The following table displays the minimum permissions on each tab for each security role that is required for the automatically created [!INCLUDE[prod_short](includes/prod_short.md)] Integration application user.

##### Core Records
|Security Role|Access Level|Dynamics NAV 2018 and Earlier|Business Central <br> October 2018|Business Central <br> April 2019|
|----|----|-----|----|----|
|Account|Global|Create, Read, Write, Append, Append To, Assign|Create, Read, Write, Append, Append To, Assign|Create, Read, Write, Append, Append To, Assign|
|Action Card|Global||Read|Read|
|Connection|Global|Read|Read|Read|
|Contact|Global|Create, Read, Write, Append, Append To|Create, Read, Write, Append, Append To|Create, Read, Write, Append, Append To|
|Note|Global|||Create, Read, Write, Delete Append, Assign|
|Opportunity|Global||Create, Read, Write, Append, Append To|Create, Read, Write, Append, Append To|
|Post|Global|||Create, Read, Append To|
|User Entity UI|User|Create, Read, Write|Create, Read, Write|Create, Read, Write|

##### Sales
|Security Role|Access Level|Dynamics NAV 2018 and Earlier|Business Central <br> October 2018|Business Central <br> April 2019|
|----|----|-----|----|----|
|Invoice|Global|Create, Read, Write, Append, Append To|Create, Read, Write, Append, Append To|Create, Read, Write, Append, Append To|
|Order|Global|Read, Write, Append To|Read, Write, Append To|Read, Write, Append, Append To, Assign|
|Product|Global|Create, Read, Write, Append, Append To|Create, Read, Write, Append, Append To|Create, Read, Write, Append, Append To|
|Property|Global|Read|Read|Read|
|Property Association|Global|Read|Read|Read|
|Property Option Set Item|Global|Read|Read|Read|
|Quote|Global|Read|Read|Read|

##### Service
|Security Role|Access Level|Dynamics NAV 2018 and Earlier|Business Central <br> October 2018|Business Central <br> April 2019|
|----|----|-----|----|----|
|Case|Global|Read|Read|Read|

##### Business Management
|Security Role|Access Level|Dynamics NAV 2018 and Earlier|Business Central <br> October 2018|Business Central <br> April 2019|
|----|----|-----|----|----|
|Currency|Global|Create, Read, Write|Create, Read, Write|Create, Read, Write|
|Organization|Global|Read, Write|Read, Write|Read, Write|
|Security Role|Global|||Read|
|User|Global|Create, Read, Write, Append, Append To|Create, Read, Write, Append, Append To|Create, Read, Write, Append, Append To|
|User Settings|Global|Create, Read, Write, Delete, Append To|Create, Read, Write, Delete, Append To|Create, Read, Write, Delete, Append To|
|Act on Behalf of Another User|Global|Yes|Yes|Yes|

##### Customization
|Security Role|Access Level|Dynamics NAV 2018 and Earlier|Business Central <br> October 2018|Business Central <br> April 2019|
|----|----|-----|----|----|
|Field|Global||Read|Read|
|Plug-in Assembly|Global|Read|Read|Read|
|Plug-in Type|Global|Read|Read|Read|
|SDK Message|Global|Read|Read|Read|
|SDK Message Processing Step|Global|Read|Read|Read|
|Web Resource|Global|Read|Read|Read|

##### Custom Entities
|Security Role|Access Level|Dynamics NAV 2018 and Earlier|Business Central <br> October 2018|Business Central <br> April 2019|
|----|----|-----|----|----|
|Dynamics 365 Business Central Account Statistics|Global|Create, Read, Write, Append To|Create, Read, Write, Append To|Create, Read, Write, Append To|
|Dynamics 365 Business Central Connection|Global|Read|Read|Read|

### Product Availability User
You can allow sales people to view inventory levels for the items they sell by granting them the permissions described in the following table.

##### Custom Entities
|Security Role|Access Level|Dynamics NAV 2018 and Earlier|Business Central <br> October 2018|Business Central <br> April 2019|
|----|----|-----|----|----|
|Dynamics 365 Business Central Account Statistics|Global|Create, Read, Write, Append To|Create, Read, Write, Append To|Create, Read, Write, Append To|
|Dynamics 365 Business Central Connection|Global|Read|Read|Read|

-->

## Se også

[Integrere med Microsoft Dataverse](admin-common-data-service.md)  
[Integrere med Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
