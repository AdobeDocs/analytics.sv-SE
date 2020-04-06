---
title: Util.getQueryParam
description: Returnerar värdet för en frågesträngsparameter.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Util.getQueryParam

Frågesträngsparametrar i en webbläsarURL innehåller ofta viktiga data för Analytics. Använd `Util.getQueryParam()` metoden för att hämta data från frågesträngen.

## Hämta frågesträngsparameterdata i Adobe Experience Platform Launch

Du kan hämta parameterdata för frågesträngar genom att ange värden i dataelement.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Data Elements] fliken och klicka sedan på det önskade dataelementet (eller skapa ett dataelement).
4. Ställ in [!UICONTROL Extension] listrutan till [!UICONTROL Core]och [!UICONTROL Data Element Type] till [!UICONTROL Query String Parameter].
5. Ange frågesträngsparametern i textfältet.

Frågesträngens parametervärde lagras i dataelementet. Du kan sedan referera till dataelementet i regler för att tilldela Analytics-variabler.

## s.Util.getQueryParam() i AppMeasurement och Launch, anpassad kodredigerare

Anropa `s.Util.getQueryParam()` metoden för att hämta ett frågesträngsvärde från webbläsarens URL. Strängargumentet som innehåller en frågesträngsparameter krävs. Den här metoden returnerar en sträng som du kan tilldela Analytics-variabler:

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

Med ett andra valfritt argument kan du ange strängen för att kontrollera frågesträngsparametrar. Verktyget söker som standard på webbläsarens URL.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

Med ett tredje valfritt argument kan du anpassa frågesträngsavgränsaren. Dess standardvärde är `&`. Du kan ändra det här värdet om frågesträngen använder en annan avgränsare.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP] Det finns ett liknande plugin-program med namnet [`s.getQueryParam`](../plugins/getqueryparam.md) . Detta plugin-program innehåller mer avancerade funktioner, men är också mer komplext och ingår inte i AppMeasurement som standard.
