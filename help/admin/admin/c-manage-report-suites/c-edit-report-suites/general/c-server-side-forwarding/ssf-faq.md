---
description: Vanliga frågor och svar om funktioner, funktioner och problem i samband med vidarebefordran på serversidan.
title: Vanliga frågor om vidarebefordran på serversidan
feature: Server-Side Forwarding
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 1%

---

# Vanliga frågor om vidarebefordran på serversidan

Vanliga frågor och svar om funktioner, funktioner och problem i samband med vidarebefordran på serversidan.

## Spårningsservrar {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Fråga | Svar |
|--- |--- |
| F: Vad händer om jag för närvarande använder den äldre, spårningsfunktionen på serverbaserade vidarebefordringsmetoder? | Den äldre spårningsserverbaserade metoden för servervidarebefordran fortsätter att vidarebefordra data från Analytics till Audience Manager, men om du vill skicka Audience Manager-segment till Analytics krävs den nya rapportsvitsbaserade vidarebefordran på serversidan. Det skadar inte heller att aktivera en rapportserie för vidarebefordran på serversidan utöver spårningsserverkonfigurationen. Den nya rapportsvitens serversidesinställning används när en konflikt uppstår. |
| F: Ska jag migrera min äldre spårningsserverbaserade vidarebefordran på serversidan till den nya rapportsvitbaserade vidarebefordringen på serversidan? | Vi kommer att fortsätta att stödja vidarebefordran av serverbaserad spårning inom överskådlig framtid, men om du vill dra nytta av integreringen från Audience Manager till Analytics (segmentdelning till Analytics) måste du aktivera den nya rapportsvitsbaserade vidarebefordran på serversidan för alla tillämpliga rapportsviter. Det finns dock ingen anledning att inaktivera den äldre spårningsserverbaserade vidarebefordran på serversidan. |

## Tagga och rapportera {#section_71391BA901AC47B9A2286281644FF281}

| Fråga | Svar |
|--- |--- |
| F: Vad händer om jag har flera programsviter på min webbplats? Kommer vidarebefordran på serversidan att fördubbla mina serveranrop till Audience Manager? | Nej, en träff som vidarebefordras från Analytics till Audience Manager vidarebefordras endast en gång till Audience Manager, oavsett antalet rapportsviter i träffen. Om du har motsvarande datakällor i Audience Manager för var och en av rapportsviterna i träffen fylls de i korrekt från den enskilda träffen.  Tänk dock på att om du för närvarande använder datainsamling på klientsidan (DIL) och aktiverar vidarebefordran på serversidan utan att installera Audience Management Module, kommer du att fördubbla serveranropen till Audience Manager oavsett hur många rapportsviter du har i Analytics-träffen. |
| F: Vad händer om jag har taggade flerprogramsrapportsviter som är mappade till olika Experience Cloud Orgs? | Du bör aldrig skicka data från en enskild Analytics-träff till två rapportsviter som tillhör separata Experience Cloud Orgs, men om detta inträffar vidarebefordrar vi bara träffen till Experience Cloud Org som matchar konfigurationen för identitetstjänsten på sidan. |
| F: Vad händer om jag har märkning för flera programsviter och bara en av mina rapportsviter mappas till min Experience Cloud-organisation och den andra inte? | Vi vidarebefordrar träffen till motsvarande datainsamlingsserver för Experience Cloud Org i din mappade rapportsvit, men eftersom den icke mappade rapportsviten inte har någon associerad datakälla i Audience Manager registreras inga data för den omappade rapportsviten i Audience Manager. |
| F: Vad händer om jag har en rapportsserie som är kopplad till flera Experience Cloud Orgs? | Rapporteringssviten kommer att betraktas som omappad och serversidans vidarebefordran kommer inte att kunna aktiveras för den här rapportsviten. Kontakta kundtjänst för att lösa mappningsproblemet. |
| F: Kommer den rapportsvitbaserade serversidans vidarebefordringsmetod att vara långsammare än den spårningsserverbaserade serversidans vidarebefordran? | Nej, svarstiden är densamma. |
| F: Vad händer om vi har två Experience Cloud-organisationer (eller Adobe Audience Manager-instanser) och vill dela data mellan båda Experience Cloud Orgs? Kan jag skicka en enda Analytics-träff till flera Experience Cloud Orgs på serversidan? | Nej. Om ni behöver dela data som samlats in under en Experience Cloud-organisation med en annan Experience Cloud-organisation rekommenderar vi att ni skickar tillämpliga målgrupper från en Audience Manager-instans till en annan via målgruppens marknadsplats. |
| F: Kommer vidarebefordran på serversidan att resultera i någon ytterligare fakturering i Audience Manager eller Analytics? | I Analytics sker ingen ytterligare fakturering. I Audience Manager behandlas vidarebefordrade träffar som alla andra träffar och faktureras.  Därför är det viktigt att inte ha vidarebefordran på DIL och serversidan aktiverad samtidigt, vilket kan leda till dubbel fakturering och dubblering av data. |

>[!MORELIKETHIS]
>
>* [Vidarebefordran på serversidan](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
