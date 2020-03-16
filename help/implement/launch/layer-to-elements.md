---
title: Mappa datalagerobjekt till dataelement
description: Konfigurera Launch för att läsa från datalagret.
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Mappa datalagerobjekt till dataelement

När organisationen har etablerat och implementerat ett datalager på webbplatsen kan du mappa datalagerobjekt till dataelement i Launch.

## Förutsättningar

[Skapa ett datalager](../prepare/data-layer.md): Kontrollera att det finns ett datalager på platsen. Även om du tekniskt kan mappa ett JavaScript-objekt eller skrapa CSS-element direkt från sidan, rekommenderar Adobe att detta görs som en sista utväg. Om webbplatslayouten ändras slutar de CSS-väljare som används i Launch att fungera, vilket orsakar dataförlust.

## Använd Adobe Experience Platform Launch för att skapa dataelement

[Dataelement](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) är komponenter i Launch som du kan använda i hela verktyget. Du kan tilldela variabelvärden i Adobe Analytics-tillägget med dataelement.

1. Gå till [Adobe Experience Platform Launch](https://launch.adobe.com) och logga in om du uppmanas till detta.
1. Klicka på önskad Launch-egenskap.
1. Klicka på [!UICONTROL Data Elements] fliken och sedan på [!UICONTROL Add Data Element].

   ![skapa dataelement](assets/createelement.png)

1. Ange ett namn för dataelementet. Det kan vara en enkel etikett som motsvarar en JavaScript-variabel i datalagret som du vill spåra.
1. Välj under [!UICONTROL Extension] listrutan [!UICONTROL Core].
1. Välj under [!UICONTROL Data Element Type] listrutan [!UICONTROL JavaScript Variable]. Ett textfält visas till höger där du kan ange JavaScript-variabeln som ska mappas till det här dataelementet.
1. Ange önskad JavaScript-variabel, vanligtvis i datalagret. Om t.ex. organisationens datalager är i linje med Adobes rekommenderade praxis kan ett värde vara `digitalData.page.pageInfo.pageName`. Du kan använda webbläsarens konsol för att validera JavaScript-variabelsyntax och -värden.
1. Klicka på [!UICONTROL Save].

## Nästa steg

[Mappa dataelement till analysvariabler](elements-to-variable.md): Tilldela dataelement till analysvariabler så att du kan använda dem som dimensioner i Analysis Workspace.
