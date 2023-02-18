---
title: kampanj
description: Fyll i dimensionen 'Spårningskod'.
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
source-git-commit: e46b15eedda78303e6e29faceea6db8483eee277
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# kampanj

The `campaign` variabeln används för att samla in spårningskoder på din webbplats. I tidigare versioner av Adobe Analytics hade programmet en speciell behandling där det kunde användas som en uppdelning på de flesta dimensioner. I den aktuella versionen av Adobe Analytics fungerar den likadant som en eVar.

Den här variabeln fyller i [Spårningskod](/help/components/dimensions/tracking-code.md) dimension. Det hämtar vanligtvis sitt värde från en frågesträng med [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) utility-metod. Din organisation bestämmer dock exakt hur variabeln ska ställas in.

## Campaign med Web SDK

Campaign är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fältet `marketing.trackingCode`.

## Campaign med Adobe Analytics-tillägget

Du kan ange kampanj antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Campaign] -avsnitt.

Du kan ställa in kampanjen på ett värde eller en frågesträngsparameter.

## s.campaign i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

The `s.campaign` variabeln är en sträng som vanligtvis innehåller en spårningskod som används i marknadsföringsaktiviteter. Dess största längd är 255 byte. värden som är längre än 255 byte trunkeras automatiskt när de skickas till Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
