---
description: Med sidanalys i realtid (Live-läge) kan du få resultat med minimal granularitet i realtid.
title: Realtidsanalys (Live)
topic: Activity map
uuid: a3faa9bd-73d8-48b3-be2b-f818ed7456fb
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Realtidsanalys (Live)

Med sidanalys i realtid (Live-läge) kan du få resultat med minimal granularitet i realtid.

Activity Map visar nu analysdata i steg om 1 till 15 minuter för att övervaka länkpopulariteten baserat på mikrotrender för valda sidor. Detta är särskilt viktigt för förlag när det gäller att följa upp och reagera på ökat eller minskat intresse för berättelser och för att övervaka trafikflödet i realtid.

Som ägare av webbplatsinnehåll är en del av ditt jobb att förstå när vi ska marknadsföra och ta bort innehåll och behålla vår upplevelse konstant relevant. Realtidsdata är livsnerven i detta ansvar. Om ni förstår vilka länkar och vilket innehåll som trendar just nu kan ni agera snabbt och beslutsamt för att hålla läsarna och kunderna engagerade med ert varumärke.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

## Datalatens som ett resultat av A4T-konfiguration {#section_806CE36354FC4C539A0DED9266A5C704}

När A4T-integreringen har aktiverats i Adobe Target får du ytterligare 5-10 minuters fördröjning i Adobe Analytics. Den här fördröjningsökningen gör att data från Analytics och Target kan lagras på samma träff, vilket gör att ni kan bryta ned tester per sida och webbplatsavsnitt.

Ökningen återspeglas i alla Adobe Analytics-tjänster och -verktyg, inklusive liveströmmen och realtidsrapporter, och gäller i följande scenarier:

* För liveströmmar, realtidsrapporter och API-begäranden samt aktuella data för trafikvariabler fördröjs bara träffar med ett extra data-ID.
* För aktuella data om konverteringsmått, slutförda data och dataflöden fördröjs alla träffar ytterligare 5-7 minuter.

Tänk på att latensökningen börjar efter att du har implementerat [identitetstjänsten](https://marketing.adobe.com/resources/help/en_US/mcvid/), även om du inte har implementerat den här integreringen fullständigt.
