---
title: Läge
description: Fyll i 'Visitor State Report' i Reports and Analytics.
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# tillstånd

>[!IMPORTANT]
>
>Den här variabeln har tagits bort och är inte en tillgänglig dimension i Analysis Workspace. Använd dimensionen &#39;USA&#39; i stället, som AppMeasurement automatiskt samlar in baserat på besökarens plats.

I tidigare versioner av Adobe Analytics `state` variabeln användes när besökarna fyllde i leveransinformation på butikssajter. Den är funktionellt identisk med en prop, men är inte tillgänglig i Analysis Workspace.

## Läge som använder taggar i Adobe Experience Platform

Du kan ange tillstånd antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL State] -avsnitt.

Du kan ange tillstånd till valfritt strängvärde eller dataelement.

## s.state i AppMeasurement och anpassad kodredigerare

The `s.state` variabeln är en sträng som vanligtvis innehåller besökarens delstat eller provins. Fulla lägesnamn eller tvåbokstavskoder är båda giltiga. Den får innehålla högst 50 byte. längre värden trunkeras. Dess standardvärde är en tom sträng.

```js
s.state = "Utah";
```
