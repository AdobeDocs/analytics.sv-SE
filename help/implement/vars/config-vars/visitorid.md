---
title: visitorID
description: Använd ett anpassat besökar-ID.
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: de98bf68c57f5453b6662f6e6e57312d8fd3e642
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# visitorID

Adobe använder flera olika metoder för att [identifiera besökare](../../id/overview.md) på din webbplats. **Variabeln `visitorID` åsidosätter alla andra metoder för identifiering av besökare.**

>[!IMPORTANT]
>
>Adobe rekommenderar att du inte använder variabeln. Använd [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) i stället.

## Så här använder Analytics `visitorID`

Den här variabeln är en manuell åsidosättning av besökar-ID som ersätter alla andra former av besökaridentifiering. För att räknas som en enskild besökare måste varje träff för en person använda samma `visitorID`-värde.

* Träffar som utelämnas `visitorID` återgår till en annan metod för identifiering av besökare och behandlas som en separat besökare.
* Träffar som använder mer än ett `visitorID`-värde behandlas som separata besökare.
* Adobe sammanfogar inte träffar som använder olika besökar-ID:n.

Se [Besökaridentifiering i Adobe Analytics](../../id/overview.md) för mer information om identifieringsprioritet och varför blandning av identifierare kan generera besökarantal.

>[!WARNING]
>
>Ange bara `visitorID` om du kan garantera att den anges för varje träff för den personen och att värdet aldrig ändras. Om du bara ställer in det på vissa träffar, introducerar det på en resa (t.ex. vid autentisering) eller ändrar det mellan träffar delas en besökares aktivitet upp i flera besökare.

>[!CAUTION]
>
>Ogiltiga värden för anpassade besökar-ID kan leda till felaktiga data och dålig rapportprestanda. Om den här variabeln innehåller ett standard- eller platshållarvärde (till exempel `"0"` eller `"NULL"`) hanterar Adobe dessa träffar som om de vore samma besökare. Detta resulterar i felaktiga data, med artificiellt lågt antal besökare och segment på besökarnivå som inte fungerar som förväntat. Felaktigt implementerade anpassade besökar-ID:n kan även medföra hög belastning på bearbetningsservrar, vilket ökar [latensen](/help/technotes/latency.md) och minskar rapportprestanda.

## Besökar-ID som använder Adobe Analytics-tillägget

[!UICONTROL Visitor ID] är ett fält under dragspelet [!UICONTROL Cookies] när Adobe Analytics-tillägget konfigureras.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Välj önskad taggegenskap.
3. Gå till fliken [!UICONTROL Extensions] och välj sedan knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Cookies] som visar fältet [!UICONTROL Visitor ID].

Tilldela det här fältet till dataelementet som innehåller ditt anpassade besökar-ID. **Ange inte det här fältet som ett enda statiskt värde för alla besökare.** Använd ett dataelement som löses per besökare och förblir konstant i alla träffar.

## s.visitorID i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.visitorID` är en sträng som innehåller en anpassad unik identifierare för besökaren. Giltiga värden är alfanumeriska tecken upp till 100 byte. Undvik att använda streck, blanksteg, understreck och symboler i den här variabeln.

```js
s.visitorID = "abc123";
```

## Besökar-ID som använder Web SDK

Med Adobe Experience Platform Edge Network kan du tillhandahålla flera identifierare med hjälp av XDM:s [identitetskarta](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html#using-identitymap). Varje identitet i en identitetskarta har ett eget namnutrymme. Du kan ange vilket namnutrymme som ska användas för besökar-ID som en del av [datastream-konfigurationen](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#analytics). När det här fältet har konfigurerats används den automatiskt som besökar-ID i Analytics när du skickar en händelse med ett värde som anges för det här namnutrymmet.
