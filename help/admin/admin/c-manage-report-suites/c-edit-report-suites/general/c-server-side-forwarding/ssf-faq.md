---
description: Vanliga frågor och svar om funktioner, funktioner och problem i samband med vidarebefordran på serversidan.
title: Vanliga frågor om vidarebefordran på serversidan
feature: Report Suite Settings
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# Vanliga frågor om vidarebefordran på serversidan

Vanliga frågor och svar om funktioner, funktioner och problem i samband med vidarebefordran på serversidan.

## Spårningsservrar {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Fråga | Svar |
|--- |--- |
| F: Hur gör jag om jag för närvarande använder den äldre, spårningsfunktionen på serversidan? | Den äldre spårningsmetoden på serversidan kommer att fortsätta vidarebefordra data från Analytics till Audience Manager, men om du vill skicka Audience Manager-segment till Analytics krävs den nya rapportsvitsbaserade vidarebefordran på serversidan. Det skadar inte heller att aktivera en rapportserie för vidarebefordran på serversidan utöver spårningsserverkonfigurationen. Den nya rapportsvitens serversidesinställning används när en konflikt uppstår. |
| F: Ska jag migrera min äldre spårningsserverbaserade vidarebefordran på serversidan till den nya rapportsvitbaserade vidarebefordringen på serversidan? | Vi kommer att fortsätta att stödja vidarebefordran av serverbaserad spårning inom överskådlig framtid, men om du vill dra nytta av integreringen från Audience Manager till Analytics (segmentdelning till Analytics) måste du aktivera den nya rapportsvitsbaserade vidarebefordran på serversidan för alla tillämpliga rapportsviter. Det finns dock ingen anledning att inaktivera den äldre spårningsserverbaserade vidarebefordran på serversidan. |

## Tagga och rapportera {#section_71391BA901AC47B9A2286281644FF281}

| Fråga | Svar |
|--- |--- |
| F: Hur gör jag om jag har märkning för flera programsviter på min webbplats? Kommer vidarebefordran på serversidan att fördubbla mina serveranrop till Audience Manager? | Nej, en träff som vidarebefordras från Analytics till Audience Manager vidarebefordras endast en gång till Audience Manager, oavsett antalet rapportsviter i träffen. Om du har motsvarande datakällor i Audience Manager för var och en av rapportsviterna i träffen fylls de i korrekt från den enskilda träffen.  Tänk dock på att om du för närvarande använder datainsamling på klientsidan (DIL) och aktiverar vidarebefordran på serversidan utan att installera Audience Management Module, kommer du att fördubbla serveranropen till Audience Manager oavsett hur många rapportsviter du har i Analytics-träffen. |
| F: Vad händer om jag har taggade flerprogramsrapporteringsprogram som är mappade till separata Experience Cloud Orgs? | Du bör aldrig skicka data från en enskild Analytics-träff till två rapportsviter som tillhör separata Experience Cloud Orgs, men om detta inträffar vidarebefordrar vi bara träffen till den Experience Cloud Org som matchar konfigurationen av identitetstjänsten på sidan. |
| F: Vad händer om jag har märkning för flera programsviter och bara en av mina rapportsviter är kopplad till min Experience Cloud-organisation och den andra inte? | Vi vidarebefordrar träffen till motsvarande datainsamlingsserver för Experience Cloud Org på ditt mappade rapportpaket, men eftersom det inte finns någon associerad datakälla i Audience Manager registreras inga data för det omappade rapportsviten i Audience Manager. |
| F: Hur gör jag om jag har en rapportserie som är kopplad till flera Experience Cloud Orgs? | Rapporteringssviten kommer att betraktas som omappad och serversidans vidarebefordran kommer inte att kunna aktiveras för den här rapportsviten. Kontakta kundtjänst för att lösa mappningsproblemet. |
| F: Kommer den rapportsvitbaserade metoden för vidarebefordran på serversidan att ta längre tid än den spårningsserverbaserade vidarebefordringen? | Nej, svarstiden är densamma. |
| F: Vad händer om vi har två Experience Cloud Orgs (eller Adobe Audience Manager-instanser) och vill dela data mellan båda Experience Cloud Orgs? Kan jag skicka en enda Analytics-träff till flera Experience Cloud Orgs på serversidan? | Nej. Om du behöver dela data som samlats in under en Experience Cloud-organisation med en annan Experience Cloud-organisation rekommenderar vi att du skickar tillämpliga målgrupper från en Audience Manager-instans till en annan via målgruppens marknadsplats. |
| F: Kommer vidarebefordran på serversidan att leda till ytterligare fakturering i Audience Manager eller Analytics? | I Analytics sker ingen ytterligare fakturering. Vidarebefordrade träffar behandlas som andra träffar i Audience Manager och faktureras.  Därför är det viktigt att inte aktivera vidarebefordran på DIL och serversidan samtidigt, vilket kan leda till dubbel fakturering och dubblering av data. |

>[!MORELIKETHIS]
>
>* [Vidarebefordran på serversidan](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
