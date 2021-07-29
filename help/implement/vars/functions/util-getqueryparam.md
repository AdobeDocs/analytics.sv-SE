---
title: Util.getQueryParam
description: Returnerar värdet för en frågesträngsparameter.
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Util.getQueryParam

Frågesträngsparametrar i en webbläsarURL innehåller ofta viktiga data för Analytics. Använd metoden `Util.getQueryParam()` för att hämta data från frågesträngen.

## Hämta frågesträngsparameterdata med hjälp av taggar i Adobe Experience Platform

Du kan hämta parameterdata för frågesträngar genom att ange värden i dataelement.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Data Elements] och klicka sedan på det önskade dataelementet (eller skapa ett dataelement).
4. Ställ in listrutan [!UICONTROL Extension] till [!UICONTROL Core] och [!UICONTROL Data Element Type] till [!UICONTROL Query String Parameter].
5. Ange frågesträngsparametern i textfältet.

Frågesträngens parametervärde lagras i dataelementet. Du kan sedan referera till dataelementet i regler för att tilldela Analytics-variabler.

## s.Util.getQueryParam() i AppMeasurement och anpassad kodredigerare

Anropa metoden `s.Util.getQueryParam()` för att hämta ett frågesträngsvärde från webbläsarens URL. Strängargumentet som innehåller en frågesträngsparameter krävs. Den här metoden returnerar en sträng som du kan tilldela Analytics-variabler:

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

>[!TIP]
>
>Det finns ett liknande plugin-program med namnet [`s.getQueryParam`](../plugins/getqueryparam.md). Detta plugin-program innehåller mer avancerade funktioner, men är också mer komplext och ingår inte i AppMeasurement som standard.
