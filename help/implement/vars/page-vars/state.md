---
title: tillstånd
description: Fyll i 'Visitor State Report' i Reports and Analytics.
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---

# tillstånd

>[!IMPORTANT]
>
>Den här variabeln har tagits bort och är inte en tillgänglig dimension i Analysis Workspace. Använd dimensionen &#39;USA&#39; i stället, som AppMeasurement automatiskt samlar in baserat på besökarens plats.

I tidigare versioner av Adobe Analytics `state` variabeln användes när besökarna fyllde i leveransinformation på butikssajter. Den är funktionellt identisk med en prop, men är inte tillgänglig i Analysis Workspace.

## Läge som använder Adobe Analytics-tillägget

Du kan ange tillstånd antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL State] -avsnitt.

Du kan ange tillstånd till valfritt strängvärde eller dataelement.

## s.state in AppMeasurement and the Analytics extension custom code editor

The `s.state` variabeln är en sträng som vanligtvis innehåller besökarens delstat eller provins. Fulla lägesnamn eller tvåbokstavskoder är båda giltiga. Den får innehålla högst 50 byte. längre värden trunkeras. Dess standardvärde är en tom sträng.

```js
s.state = "Utah";
```
