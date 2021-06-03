---
title: visitorID
description: Använd ett anpassat besökar-ID.
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 1%

---

# visitorID

Adobe använder flera olika metoder för att identifiera besökare på din webbplats. Variabeln `visitorID` åsidosätter alla andra metoder för identifiering av besökare.

>[!IMPORTANT]
>
>Adobe avråder från att använda den här variabeln. Använd [Adobe Experience Cloud identitetstjänst](https://experienceleague.adobe.com/docs/id-service/using/home.html) i stället.

## Besökar-ID i Adobe Experience Platform Launch

[!UICONTROL Visitor ID] är ett fält under  [!UICONTROL Cookies] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Cookies], som visar fältet [!UICONTROL Visitor ID].

Tilldela det här fältet till dataelementet som innehåller ditt anpassade besökar-ID. Ange inte det här fältet som ett statiskt värde.

## s.visitorID i AppMeasurement och Launch custom code editor

Variabeln `s.visitorID` är en sträng som innehåller en anpassad unik identifierare för besökaren. Giltiga värden är alfanumeriska tecken upp till 100 byte. Undvik att använda streck, blanksteg, understreck och symboler i den här variabeln.

>[!WARNING]
>
>Om du ställer in variabeln `visitorID` genom ett besök resulterar data i två separata unika besökare.

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>En ogiltig implementering av anpassade besökar-ID:n kan leda till felaktiga data och dålig rapportprestanda. Om den här variabeln innehåller ett standardvärde (till exempel `"0"` eller `"NULL"`) hanterar Adobe dessa träffar som om de vore samma besökare. Detta resulterar i felaktiga data, med låga besökarantal och segment på besökarnivå som inte fungerar som förväntat. Felaktigt implementerade anpassade besökar-ID:n medför också stor belastning på bearbetningsservrar, vilket ökar [latensen](/help/technotes/latency.md) och minskar rapportprestanda.
