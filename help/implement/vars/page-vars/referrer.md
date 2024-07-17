---
title: hänvisare
description: Åsidosätt den automatiskt insamlade referenten för en träff.
feature: Variables
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---

# hänvisare

Variabeln `referrer` åsidosätter den automatiskt insamlade referenten i rapporter. Den här variabeln är användbar i situationer där referenten kan förloras, till exempel vid omdirigeringar eller när besökaren tillfälligt vidarebefordras till en betalningsbehandlare. Den här variabeln används för att fylla i dimensionerna Referer och Refererande domän.

## Referent med Web SDK

Referenten är mappad till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webReferrer.URL`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.referrer`

Web SDK inkluderar automatiskt `web.webReferrer.URL` för varje händelse som skickas, om det är tillgängligt.

## Referent som använder Adobe Analytics-tillägget

Du kan ange referent antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Referrer].

Du kan ställa in referenten på valfritt strängvärde, inklusive dataelement.

## s.reference i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.referrer` är en sträng som innehåller URL:en för föregående sida. Den här variabeln kan lagra högst 255 byte. Värden som är större än 255 byte trunkeras. AppMeasurementet ställer automatiskt in den här variabeln till `document.referrer`. Du behöver inte ställa in den här variabeln om du inte vill åsidosätta det automatiskt insamlade värdet.

```js
s.referrer = "https://example.com";
```

Om `digitalData` [datalagret](../../prepare/data-layer.md) används:

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>Undvik att ställa in den här variabeln på värden som inte är URL-adresser. Ta inte bort URL-adressens protokoll.

## Exempel

Många organisationer hanterar implementeringar kring omdirigeringar. Du kan använda verktyget [`Util.getQueryParam()`](../functions/util-getqueryparam.md) för att hämta en referens från URL:en om webbplatsen har plats för den. Kontrollera att du URL-kodar alla värden som ingår i frågesträngen.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
