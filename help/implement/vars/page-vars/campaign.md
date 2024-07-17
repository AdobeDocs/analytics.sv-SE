---
title: kampanj
description: Fyll i dimensionen 'Spårningskod'.
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---

# kampanj

Variabeln `campaign` är dedikerad till att samla in spårningskoder på din webbplats. I tidigare versioner av Adobe Analytics hade programmet en speciell behandling där det kunde användas som en uppdelning på de flesta dimensioner. I den nuvarande versionen av Adobe Analytics fungerar den likadant som en eVar.

Den här variabeln fyller i dimensionen [Spårningskod](/help/components/dimensions/tracking-code.md). Det hämtar vanligtvis sitt värde från en frågesträng med verktygsmetoden [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md). Din organisation bestämmer dock exakt hur variabeln ska ställas in.

## Campaign med Web SDK

Campaign mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `marketing.trackingCode`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.campaign` eller `data.__adobe.analytics.v0`

## Campaign med Adobe Analytics-tillägget

Du kan ange kampanj antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Campaign].

Du kan ställa in kampanjen på ett värde eller en frågesträngsparameter.

## s.campaign in AppMeasurement and the Analytics extension custom code editor

Variabeln `s.campaign` är en sträng som vanligtvis innehåller en spårningskod som används i marknadsföringsaktiviteter. Dess största längd är 255 byte. Värden som är längre än 255 byte trunkeras automatiskt när de skickas till Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
