---
title: Util.getQueryParam
description: Returnerar värdet för en frågesträngparameter.
feature: Variables
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# Util.getQueryParam

Frågesträngsparametrar i en webbläsarURL innehåller ofta viktiga data för Analytics. Använd `Util.getQueryParam()` metod för att hämta data från frågesträngen.

## Hämta frågesträngsparameterdata med Adobe Analytics-tillägget och Web SDK-tillägget

Du kan hämta parameterdata för frågesträngar genom att ange värden i dataelement.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Data Elements] och sedan klicka på det önskade dataelementet (eller skapa ett dataelement).
4. Ange [!UICONTROL Extension] nedrullningsbar lista till **[!UICONTROL Core]** och [!UICONTROL Data Element Type] till **[!UICONTROL Query String Parameter]**.
5. Ange frågesträngsparametern i textfältet.

Frågesträngens parametervärde lagras i dataelementet. Du kan sedan referera till dataelementet i regler för att tilldela önskade variabler.

## s.Util.getQueryParam() i AppMeasurementet och i den anpassade kodredigeraren för Analytics-tillägget

Ring `s.Util.getQueryParam()` metod för att hämta ett frågesträngsvärde från webbläsarens URL. Strängargumentet som innehåller en frågesträngsparameter krävs. Den här metoden returnerar en sträng som du kan tilldela Analytics-variabler:

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

Med ett tredje valfritt argument kan du anpassa frågesträngsavgränsaren. Standardvärdet är `&`. Du kan ändra det här värdet om frågesträngen använder en annan avgränsare.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP]
>
>Ett liknande plugin-program med namnet [`s.getQueryParam`](../plugins/getqueryparam.md) är tillgängligt. Detta plugin-program innehåller mer avancerade funktioner, men är också mer komplext och ingår inte i AppMeasurementet som standard.
