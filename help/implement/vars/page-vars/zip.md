---
title: zip
description: Fyll i dimensionen 'Postnummer' manuellt om inställningarna för rapportsviten tillåter det.
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# zip

Med variabeln `zip` kan du manuellt fylla i dimensionen &#39;Postnummer&#39; om det är tillåtet med [!UICONTROL Zip Option] i inställningarna för rapportsviten. I tidigare versioner av Adobe Analytics kunde variabeln endast ställas in manuellt, vanligtvis när fraktinformation skrevs in på en detaljhandelsplats. Förbättringar av Adobe Analytics gör att den här variabeln kan ställas in automatiskt med geopositioneringsdata. Den här variabeln finns inte kvar efter den träff som har angetts.

>[!IMPORTANT]
>
>Kontrollera att [!UICONTROL Zip Option] i inställningarna för rapportsviten är inställda på önskat värde. Du kan inte använda den här variabeln om [!UICONTROL geo zip] alltid används. Mer information finns i [Allmänna kontoinställningar](/help/admin/admin/general-acct-settings-admin.md) i användarhandboken för Admin.

## Zippa med taggar i Adobe Experience Platform

Du kan ange Postnummer antingen när du konfigurerar Analytics-tillägget (globala variabler) eller enligt regler.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Gå till avsnittet [!UICONTROL Zip].

Du kan ställa in postkoden på valfritt strängvärde, inklusive dataelement.

## s.zip i AppMeasurement och anpassad kodredigerare

Variabeln `s.zip` är en sträng som vanligtvis innehåller en ZIP-kod, men som kan innehålla önskat värde upp till 50 byte.

```js
s.zip = "84043";
```
