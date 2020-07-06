---
title: zip
description: Fyll i dimensionen 'Postnummer' manuellt om inställningarna för rapportsviten tillåter det.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 1%

---


# zip

Med `zip` variabeln kan du manuellt fylla i dimensionen &#39;Postnummer&#39; om inställningarna [!UICONTROL Zip Option] i rapportsviten tillåter det. I tidigare versioner av Adobe Analytics kunde variabeln endast ställas in manuellt, vanligtvis när du anger leveransinformation på en återförsäljarwebbplats. Förbättringar av Adobe Analytics gör att den här variabeln kan ställas in automatiskt med geolokaliseringsdata. Den här variabeln finns inte kvar efter den träff som har angetts.

>[!IMPORTANT]
>
>Kontrollera att inställningarna [!UICONTROL Zip Option] i rapportsviten är inställda på önskat värde. Du kan inte använda den här variabeln om [!UICONTROL geo zip] den alltid används. Mer information finns i [Allmänna kontoinställningar](/help/admin/admin/general-acct-settings-admin.md) i användarhandboken för Admin.

## Zip i Adobe Experience Platform Launch

Du kan ange Postnummer antingen när du konfigurerar Analytics-tillägget (globala variabler) eller enligt regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan [!UICONTROL Extension] på Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Zip] avsnittet.

Du kan ställa in postkoden på valfritt strängvärde, inklusive dataelement.

## s.zip i AppMeasurement and Launch custom code editor

Variabeln är en sträng som vanligtvis innehåller en ZIP-kod, men kan innehålla ett önskat värde som är upp till 50 byte långt. `s.zip`

```js
s.zip = "84043";
```
