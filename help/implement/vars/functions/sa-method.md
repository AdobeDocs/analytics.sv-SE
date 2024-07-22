---
title: sa
description: Ändra rapportsviten när som helst i implementeringen.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
role: Admin, Developer
source-git-commit: bfafc1f8eddf82b34fb45e3d6197213f0cee0d97
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---

# sa

Med metoden `sa()` kan du dynamiskt ändra en rapportsserie när som helst på sidan. Om du vill skicka data till olika rapportsviter utan att behöva läsa in en sida på nytt kan du använda den här metoden.

## Hantera rapportsviter med Web SDK

Web SDK fungerar genom att data skickas till en specifik datastream som vidarebefordrar data till önskad analysrapportsvit(er). En enda datastream kan vidarebefordra data till flera rapportsviter. Det här avsnittet gäller både för Web SDK-tillägget och för att manuellt implementera Web SDK.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på **[!UICONTROL Datastreams]** till vänster.
1. Klicka på det önskade dataflödet eller klicka på **[!UICONTROL New Datastream]**.
1. Klicka på **[!UICONTROL Add Service]** och välj sedan **[!UICONTROL Adobe Analytics]**.
1. Ange önskat Report Suite-ID. Om du vill skicka samma data till flera rapportsviter klickar du på **[!UICONTROL Add Report Suite]**.
1. Klicka på **[!UICONTROL Save]** när alla önskade rapportsviter har angetts.

## Ange önskat dataström med hjälp av Web SDK-tillägget

Tillägget Web SDK innehåller en listruta för datastream för varje miljö. Du kan också ange ett dataström-ID manuellt.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Datastreams] väljer du önskad dataström i listrutan för varje miljö.
1. Klicka på **[!UICONTROL Save]**.

## Ange önskad dataström som ska implementera Web SDK manuellt

Ställ in konfigurationsvariabeln `datastreamId` till DataStream ID. DataStream-ID:t finns till höger när du visar ett dataström i Adobe Experience Platform Data Collection.

```js
alloy("configure", {
  datastreamId: "example-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Mer information finns i [Konfigurera Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) i Web SDK-dokumentationen.

## Ändra rapportsvit med Adobe Analytics-tillägget

Det finns inget flexibelt sätt att ändra rapportsviten i gränssnittet. Du kan ställa in rapportsviten under dragspelet [!UICONTROL Library Management] när du konfigurerar Adobe Analytics-tillägget. Du kan dock inte ändra eller uppdatera rapportsviten med hjälp av regler. Om du vill uppdatera rapportsvitens värden när de har angetts använder du den anpassade kodredigeraren efter AppMeasurementets syntax.

## s.sa() i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Anropa metoden `s.sa()` om du vill ändra målrapportsviten. Det enda argumentet är en sträng som innehåller ett rapportsuite-ID, eller flera rapportsuite-ID:n avgränsade med kommatecken. Argumentet för rapportsvitens ID krävs. Använd inte blanksteg i strängargumentet.

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
