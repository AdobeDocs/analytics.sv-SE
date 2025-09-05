---
title: zip
description: Fyll i dimensionen 'Postnummer' manuellt om inställningarna för rapportsviten tillåter det.
feature: Appmeasurement Implementation
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# zip

Variabeln `zip` gör att du manuellt kan fylla i dimensionen &#39;Postnummer&#39; om inställningarna för rapportsviten tillåter det. [!UICONTROL Zip Option] I tidigare versioner av Adobe Analytics kunde variabeln endast ställas in manuellt, vanligtvis när fraktinformation skrevs in på en detaljhandelsplats. Förbättringar av Adobe Analytics gör att den här variabeln kan ställas in automatiskt med geopositioneringsdata. Den här variabeln finns inte kvar efter den träff som har angetts.

>[!IMPORTANT]
>
>Kontrollera att inställningarna för [!UICONTROL Zip Option] i rapportsviten är inställda på önskat värde. Du kan inte använda den här variabeln om [!UICONTROL Geo zip] alltid används. Mer information finns i [Allmänna kontoinställningar](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) i användarhandboken för Admin.

## Postnummer med Web SDK

Postnumret mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.placeContext.geo.postalCode`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.zip`

## Postnummer med Adobe Analytics-tillägg

Du kan ange postnummer antingen när du konfigurerar Analytics-tillägget (globala variabler) eller enligt regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Actions]-åtgärd under [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Zip].

Du kan ställa in postkoden på valfritt strängvärde, inklusive dataelement.

## s.zip i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.zip` är en sträng som vanligtvis innehåller en ZIP-kod, men kan innehålla ett önskat värde som är upp till 50 byte långt.

```js
s.zip = "84043";
```
