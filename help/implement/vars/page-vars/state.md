---
title: läge
description: (Borttaget) Fyllde i 'Visitor State Report', som inte längre är tillgänglig.
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# läge

>[!IMPORTANT]
>
>Den här variabeln har tagits bort och är inte en tillgänglig dimension i Analysis Workspace. Använd dimensionen [USA](/help/components/dimensions/us-states.md) i stället, som AppMeasurementet automatiskt samlar in baserat på besökarens plats.

I tidigare versioner av Adobe Analytics användes variabeln `state` när besökare fyllde i leveransinformation på butikssajter. Den är funktionellt identisk med en prop, men är inte tillgänglig i Analysis Workspace.

## Läge som använder Adobe Analytics-tillägget

Du kan ange tillstånd antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL State].

Du kan ange tillstånd till valfritt strängvärde eller dataelement.

## s.state in AppMeasurement and the Analytics extension custom code editor

Variabeln `s.state` är en sträng som vanligtvis innehåller besökarens delstat eller provins. Fulla lägesnamn eller tvåbokstavskoder är båda giltiga. Den har ett maxvärde på 50 byte. De längre värdena trunkeras. Dess standardvärde är en tom sträng.

```js
s.state = "Utah";
```
