---
title: pageType
description: Kontrollera om den aktuella sidan är ett 404-fel.
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 1%

---

# pageType

Variabeln `pageType` är en flagga som används för att ange felsidor på platsen, till exempel 404 fel. Om variabeln innehåller strängen `errorPage` fylls dimensionen &quot;Sidor hittades inte&quot; i.

>[!IMPORTANT]
>
>Ange inte den här variabeln på icke-felsidor.

## Sidtyp med hjälp av taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.pageType i AppMeasurement och anpassad kodredigerare

Variabeln `s.pageType` är en sträng där värdet `errorPage` är dess enda giltiga värde. Ange den här variabeln till det här värdet på alla felsidor på webbplatsen, till exempel på 404 sidor.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Använd en eVar för att samla in felkoden så att du kan få mer information om vilka specifika fel som besökarna stöter på på din webbplats.
