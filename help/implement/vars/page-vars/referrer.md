---
title: hänvisare
description: Åsidosätt den automatiskt insamlade referenten för en träff.
feature: Variables
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
source-git-commit: a37d6b26c2789211a9ed5602b708ef72768e289c
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# hänvisare

The `referrer` variabeln åsidosätter den automatiskt insamlade referenten i rapporter. Den här variabeln är användbar i situationer där referenten kan förloras, till exempel vid omdirigeringar eller när besökaren tillfälligt vidarebefordras till en betalningsbehandlare. Den här variabeln används för att fylla i dimensionerna Referer och Refererande domän.

## Referent med Web SDK

Referenten är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fältet `web.webReferrer.URL`.

Web SDK innehåller den här dimensionen vid varje händelsemöte.

## Referent som använder Adobe Analytics-tillägget

Du kan ange referent antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Referrer] -avsnitt.

Du kan ställa in referenten på valfritt strängvärde, inklusive dataelement.

## s.reference i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.referrer` variabeln är en sträng som innehåller URL:en för föregående sida. Den här variabeln kan lagra högst 255 byte. Värden som är större än 255 byte trunkeras. AppMeasurementet ställer automatiskt in variabeln till `document.referrer`; du behöver inte ange den här variabeln om du inte vill åsidosätta det automatiskt insamlade värdet.

```js
s.referrer = "https://example.com";
```

Om du använder `digitalData` [datalager](../../prepare/data-layer.md):

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>Undvik att ställa in den här variabeln på värden som inte är URL-adresser. Ta inte bort URL-adressens protokoll.

## Exempel

Många organisationer hanterar implementeringar kring omdirigeringar. Du kan använda [`Util.getQueryParam()`](../functions/util-getqueryparam.md) kan du hämta en referens från URL:en om webbplatsen passar den. Kontrollera att du URL-kodar alla värden som ingår i frågesträngen.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
