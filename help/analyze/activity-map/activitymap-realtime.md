---
description: Med sidanalys i realtid (Live-läge) kan du få resultat med minimal granularitet i realtid.
title: Sidanalys i realtid (live)
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 29ccd89e-d82b-41d4-a940-addc6656b5ec
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 1%

---

# Sidanalys i realtid (Live-läge)

Med sidanalys i realtid (Live-läge) kan du få resultat med minimal granularitet i realtid.

Activity Map visar nu analysdata i steg om 1 minut till 15 minuter för att övervaka länkpopulariteten baserat på mikrotrender för utvalda sidor. Detta är särskilt viktigt för förlag när det gäller att följa upp och reagera på ökat eller minskat intresse för berättelser och för att övervaka trafikflödet i realtid.

Som ägare av webbplatsinnehåll är en del av ditt jobb att förstå när vi ska marknadsföra och ta bort innehåll och behålla vår upplevelse konstant relevant. Realtidsdata är livsnerven i detta ansvar. Om ni förstår vilka länkar och vilket innehåll som trendar just nu kan ni agera snabbt och beslutsamt för att hålla läsarna och kunderna engagerade med ert varumärke.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

Om du vill kontrollera vilket element som klickas mest i Live-läge:

1. Välj tidsperioden på verktygsfältets **[!UICONTROL Live Mode]** trendlinje som du vill analysera.
1. Klicka på ikonen &quot;Öga&quot; i verktygsfältet för att öppna tabellen Länkar.
1. Ordna tabellen efter länken.

## Datalatens som ett resultat av A4T-konfiguration

När [A4T-integreringen](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) har aktiverats i Adobe Target får du ytterligare 5-10 minuters fördröjning i Adobe Analytics. Den här fördröjningsökningen gör att data från Analytics och Target kan lagras på samma träff, vilket gör att ni kan bryta ned tester per sida och webbplatsavsnitt.

Ökningen återspeglas i alla Adobe Analytics tjänster och verktyg, inklusive liveströmmen och realtidsrapporter, och gäller i följande scenarier:

* För liveströmmar, realtidsrapporter och API-begäranden samt aktuella data för trafikvariabler fördröjs bara träffar med ett extra data-ID.
* För aktuella data om konverteringsmått, slutförda data och dataflöden fördröjs alla träffar ytterligare 5-7 minuter.

Tänk på att latensökningen börjar efter att du har implementerat [identitetstjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html), även om du inte har implementerat den här integreringen fullständigt.

Mer information [här](/help/analyze/activity-map/activitymap-standard-live.md).
