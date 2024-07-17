---
title: visitorID
description: Använd ett anpassat besökar-ID.
feature: Variables
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# visitorID

Adobe använder flera olika metoder för att identifiera besökare på din webbplats. Variabeln `visitorID` åsidosätter alla andra metoder för besöksidentifiering.

>[!IMPORTANT]
>
>Adobe avråder från att använda den här variabeln. Använd [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) i stället.

## Besökar-ID som använder Adobe Analytics-tillägget

[!UICONTROL Visitor ID] är ett fält under dragspelet [!UICONTROL Cookies] när Adobe Analytics-tillägget konfigureras.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Cookies] som visar fältet [!UICONTROL Visitor ID].

Tilldela det här fältet till dataelementet som innehåller ditt anpassade besökar-ID. Ange inte det här fältet som ett statiskt värde.

## s.visitorID i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

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

## Besökar-ID som använder Web SDK

Med Adobe Experience Platform Edge Network kan du tillhandahålla flera identifierare med hjälp av XDM:s [identitetskarta](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html#using-identitymap). Varje identitet i en identitetskarta har ett eget namnutrymme. Du kan ange vilket namnutrymme som ska användas för Visitor-ID som en del av [datastream-konfigurationen](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#analytics). När detta är konfigurerat används den automatiskt som besökar-ID i Analytics när du skickar en händelse med ett värde angivet för det här namnutrymmet.
