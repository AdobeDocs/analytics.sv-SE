---
description: Visar länkar som besökare föredrar på din webbplats. Hemsidan för din webbplats har till exempel förmodligen flera länkar som visar samma sida. Kanske finns det både en grafik- och textlänk som båda länkar till samma sida. Den här rapporten visar hur många procent av besökarna som använde den grafiska länken jämfört med textlänken.
title: Egen länk
topic: Reports
uuid: 2e0d0175-d5e4-4919-b601-3f488ef3e090
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Egen länk

Visar länkar som besökare föredrar på din webbplats. Hemsidan för din webbplats har till exempel förmodligen flera länkar som visar samma sida. Kanske finns det både en grafik- och textlänk som båda länkar till samma sida. Den här rapporten visar hur många procent av besökarna som använde den grafiska länken jämfört med textlänken.

De specifika länkar som du vill spåra måste ändras med specialtaggar, se [Länkspårning](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html).

Du kan använda [!UICONTROL Custom Links Report] till att:

* Optimera webbplatsens design genom att veta vilka typer av länkar besökarna föredrar
* Validera behovet av redundanta länkar till enstaka sidor

## Mobile SDK-länknamn {#section_70C91FE794104B5FBF289B19CC02EA8E}

SDK:erna för [mobilen](https://marketing.adobe.com/resources/help/en_US/mobile/home.html) använder anpassade länkar för att spåra åtgärder och livscykelvärden. I rapportsviter som används för att mäta mobilappar kan du se följande länknamn som angetts av SDK:

| ADBINTERNAL:Lifecycle | Skickas av livscykelanropet i 4.x SDK:er. |
|---|---|
| AMACTION:[åtgärdsnamn] | Skickas av metoden trackAction() i 4.x-SDK:erna, där åtgärdsnamnet är det namn som angavs när metoden anropades. |
| ADMS BP-händelse | Skickas av livscykelanropet i 3.x SDK:er. |

