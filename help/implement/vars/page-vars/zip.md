---
title: zip
description: Fyll i dimensionen 'Postnummer' manuellt om inställningarna för rapportsviten tillåter det.
feature: Variables
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# zip

The `zip` kan du fylla i postnummer manuellt om [!UICONTROL Zip Option] i rapportsvitens inställningar tillåter det. I tidigare versioner av Adobe Analytics kunde variabeln endast ställas in manuellt, vanligtvis när fraktinformation skrevs in på en detaljhandelsplats. Förbättringar av Adobe Analytics gör att den här variabeln kan ställas in automatiskt med geopositioneringsdata. Den här variabeln finns inte kvar efter den träff som har angetts.

>[!IMPORTANT]
>
>Se till att [!UICONTROL Zip Option] i rapportsvitens inställningar är inställda på önskat värde. Du kan inte använda variabeln om [!UICONTROL Geo zip] används alltid. Se [Allmänna kontoinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) i användarhandboken för Admin om du vill ha mer information.

## Postnummer med Web SDK

Postnumret mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.placeContext.geo.postalCode`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.zip`

## Postnummer med Adobe Analytics-tillägg

Du kan ange postnummer antingen när du konfigurerar Analytics-tillägget (globala variabler) eller enligt regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Zip] -avsnitt.

Du kan ställa in postkoden på valfritt strängvärde, inklusive dataelement.

## s.zip i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.zip` variabeln är en sträng som vanligtvis innehåller en ZIP-kod, men som kan innehålla önskat värde upp till 50 byte.

```js
s.zip = "84043";
```
