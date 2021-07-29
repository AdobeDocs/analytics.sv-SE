---
title: referent
description: Åsidosätt den automatiskt insamlade referenten för en träff.
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# referent

Variabeln `referrer` åsidosätter den automatiskt insamlade referenten i rapporter. Den här variabeln är användbar i situationer där referenten kan förloras, till exempel vid omdirigeringar eller när besökaren tillfälligt vidarebefordras till en betalningsbehandlare. Den här variabeln används för att fylla i dimensionerna Referer och Refererande domän.

## Referera med taggar i Adobe Experience Platform

Du kan ange referent antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Gå till avsnittet [!UICONTROL Referrer].

Du kan ställa in referenten på valfritt strängvärde, inklusive dataelement.

## s.referrer i AppMeasurement och anpassad kodredigerare

Variabeln `s.referrer` är en sträng som innehåller URL:en för föregående sida. Denna variabel kan lagra högst 255 byte. värden som är större än 255 byte trunkeras. AppMeasurement ställer automatiskt in den här variabeln på `document.referrer`; du behöver inte ange den här variabeln om du inte vill åsidosätta det automatiskt insamlade värdet.

```js
s.referrer = "https://example.com";
```

Om du använder `digitalData` [datalagret](../../prepare/data-layer.md):

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
