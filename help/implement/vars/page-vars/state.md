---
title: Läge
description: Fyll i 'Rapport om besökartillstånd' i Rapporter och Analytics.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 1%

---


# tillstånd

>[!IMPORTANT]
>
>Den här variabeln tas bort och är inte en tillgänglig dimension i Analysis Workspace. Använd dimensionen &#39;USA&#39; i stället, som AppMeasurement automatiskt samlar in baserat på besökarens plats.

I tidigare versioner av Adobe Analytics användes variabeln när besökarna fyllde i leveransinformation på `state` detaljhandelsplatser. Den är funktionellt identisk med en prop, men är inte tillgänglig i Analysis Workspace.

## State in Adobe Experience Platform Launch

Du kan ange tillstånd antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan [!UICONTROL Extension] på Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL State] avsnittet.

Du kan ange tillstånd till valfritt strängvärde eller dataelement.

## s.state in AppMeasurement and Launch custom code editor

Variabeln `s.state` är en sträng som vanligtvis innehåller besökarens delstat eller provins. Fulla lägesnamn eller tvåbokstavskoder är båda giltiga. Den får innehålla högst 50 byte. längre värden trunkeras. Dess standardvärde är en tom sträng.

```js
s.state = "Utah";
```
