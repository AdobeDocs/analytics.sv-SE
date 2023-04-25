---
title: sa
description: Ändra rapportsviten när som helst i implementeringen.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# sa

The `sa()` kan du när som helst på sidan dynamiskt ändra en rapportserie. Om du vill skicka data till olika rapportsviter utan att behöva läsa in en sida igen kan du använda den här metoden.

## Hantera rapportsviter med Web SDK

Web SDK fungerar genom att data skickas till en specifik datastream som vidarebefordrar data till önskad analysrapportsvit(er). En enda datastream kan vidarebefordra data till flera rapportsviter. Det här avsnittet gäller både för Web SDK-tillägget och för att manuellt implementera Web SDK.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka **[!UICONTROL Datastreams]** till vänster.
1. Klicka på det önskade dataflödet eller klicka på **[!UICONTROL New Datastream]**.
1. Klicka **[!UICONTROL Add Service]** väljer **[!UICONTROL Adobe Analytics]**.
1. Ange önskat Report Suite-ID. Om du vill skicka samma data till flera rapportsviter klickar du på **[!UICONTROL Add Report Suite]**.
1. När du har angett alla rapporteringsprogram klickar du på **[!UICONTROL Save]**.

## Ange önskat dataström med hjälp av Web SDK-tillägget

Tillägget Web SDK innehåller en listruta för datastream för varje miljö. Du kan också ange ett dataström-ID manuellt.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** knapp under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Datastreams]väljer du önskat datastam i listrutan för varje miljö.
1. Klicka på **[!UICONTROL Save]**.

## Ange önskad dataström som ska implementera Web SDK manuellt

Ange `edgeConfigId` konfigurationsvariabel till dataström-ID. DataStream-ID:t finns till höger när du visar ett datastream i Adobe Experience Platform Data Collection.

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

Se [Konfigurera Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) i Web SDK-dokumentationen om du vill ha mer information.

## Ändra rapportsvit med Adobe Analytics-tillägget

Det finns inget flexibelt sätt att ändra rapportsviten i gränssnittet. Du kan ange rapportsviten under [!UICONTROL Library Management] när du konfigurerar Adobe Analytics-tillägget. Du kan dock inte ändra eller uppdatera rapportsviten med hjälp av regler. Om du vill uppdatera rapportsvitens värden när de har angetts använder du den anpassade kodredigeraren efter AppMeasurement-syntaxen.

## s.sa() i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Ring `s.sa()` metod för att ändra målrapportsviten. Det enda argumentet är en sträng som innehåller ett rapportsuite-ID, eller flera rapportsuite-ID:n avgränsade med kommatecken. Argumentet för rapportsvitens ID krävs. Använd inte blanksteg i strängargumentet.

```js
s.sa("examplersid");
```

Du kan till exempel ändra rapportsviten om användaren utför en viss åtgärd på webbplatsen.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
