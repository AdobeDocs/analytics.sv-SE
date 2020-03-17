---
title: pageType
description: Kontrollera om den aktuella sidan är ett 404-fel.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# pageType

Variabeln `pageType` är en flagga som används för att ange felsidor på webbplatsen, till exempel 404 fel. Om variabeln innehåller strängen `errorPage`fylls dimensionen &quot;Sidor hittades inte&quot; i.

> [!IMPORTANT] Ange inte den här variabeln på icke-felsidor.

## Sidtyp i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.pageType i AppMeasurement och Launch custom code editor

Variabeln `s.pageType` är en sträng där värdet `errorPage` är dess enda giltiga värde. Ange den här variabeln till det här värdet på alla felsidor på webbplatsen, till exempel på 404 sidor.

```js
s.pageType = "errorPage";
```

> [!TIP] Använd en eVar för att samla in felkoden så att du kan få mer information om vilka specifika fel som besökarna stöter på på din webbplats.
