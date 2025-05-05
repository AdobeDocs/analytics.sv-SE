---
title: Vanliga frågor om implementering
description: Vanliga frågor om implementering och länkar till mer information.
feature: Implementation Basics
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
role: Admin, Developer, Leader, User
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 33%

---

# Vanliga frågor om implementering av Analytics

Vanliga frågor om implementering och länkar till mer information.

## Vad är skillnaden mellan besökar-ID:t för Experience Cloud och besökar-ID:t för Analytics?

Identitetstjänsten tilldelar en unik, beständig identifierare som kan delas till andra lösningar i Experience Cloud. Analytics besökar-ID används bara av Analytics. Adobe rekommenderar att du använder Experience Clouds besökar-ID i din implementering.

## Hur implementerar jag videospårning med pulsslag?

Se [Mäta ljud och video i Adobe Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=sv-SE).

## Kan ett avbrott i tjänsten i Adobe påverka prestanda?

Nej. JavaScript-filen finns inte på Adobes servrar, så ett driftavbrott hos Adobe påverkar inte ditt AppMeasurement-biblioteket. Om du använder taggar i Adobe Experience Platform lagras JavaScript-filen av Akamai eller på en serverplats som bestäms av din organisation.

## Kan överföringen av data från webbläsaren till Adobes tjänster minska prestandan?

AppMeasurement skapar ett bildobjekt på HTML-sidan och webbläsaren begär sedan bildobjektet från Adobes datainsamlingsservrar. Om datainsamlingsservrarna är långsamma eller inte svarar, kommer tråden som hanterar den aktuella begäran att fördröjas tills bilden returneras eller en timeout inträffar. Eftersom webbläsare hanterar bilder med flera trådar, får ett driftavbrott hos Adobe minimal inverkan på sidans inläsningstid, eftersom bara en tråd drabbas medan de andra fortsätter att fungera.

## Hur gör jag en Analytics-implementering ogiltig eller tar bort den?

Ibland vill en organisation ta bort en implementering på grund av kontraktets förfallodatum eller minska antalet serversamtal.

* **Implementeringar med Adobe Experience Platform Data Collection**: Inaktivera eller avinstallera det tillämpliga tillägget Adobe Analytics, Web SDK eller Mobile SDK på fliken [!UICONTROL Extensions] och publicera sedan.
* **Implementeringar av tidigare AppMeasurement**: Ersätt hela innehållet i `s_code.js`-filen med följande kodrad:

```js
var s = new Object();
```

>[!WARNING]
>
>Gör inte:
>
>* Ändra rapportsviten till ett ogiltigt värde, eftersom den skapar onödig belastning på Adobe-servrar.
>* Ta bort filen `s_code.js` helt, såvida du inte också tar bort alla referenser till filen på varje sida.
>* Ändra variabeln `trackingServer` så att den pekar bort från Adobe. AppMeasurementet skickar fortfarande bildbegäranden som returnerar 404 fel.

## Jag körde AppMeasurement via en kodanalys och flaggade användningen av `Math.random()` som en potentiell säkerhetsrisk. Används `Math.random()` med känsliga data?

Nej. Siffrorna som använder `Math.random()` används inte för att maskera, skicka eller ta emot känsliga data. Data som skickas till datainsamlingsservrar för Adobe är beroende av säkerheten för den underliggande HTTPS-anslutningen. <!-- AN-173590 -->

AppMeasurementet använder `Math.random()` i tre huvudområden:

* **Exempel**: Beroende på implementeringen kan viss information samlas in för endast en liten andel av besökarna på webbplatsen. `Math.random()` används för att avgöra om en viss besökare ska skicka data. I de flesta implementeringar används inte samplingar.
* **Återställningsbesökar-ID**: Om besökar-ID inte kan hämtas från cookies genereras ett slumpmässigt besökar-ID. Den här delen av AppMeasurementet använder två anrop till `Math.random()`.
* **Cachepublicering**: Ett slumpmässigt tal läggs till i slutet av URL:er för bildbegäran för att förhindra webbläsarcachelagring.
