---
title: Mappa datalagerobjekt till dataelement
description: Konfigurera Launch för att läsa från datalagret.
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 6%

---

# Mappa datalagerobjekt till dataelement

När organisationen har etablerat och implementerat ett datalager på webbplatsen kan du mappa datalagerobjekt till dataelement i Launch.

## Förutsättningar

[Skapa ett datalager](../prepare/data-layer.md): Kontrollera att det finns ett datalager på platsen. Även om du tekniskt kan mappa ett JavaScript-objekt eller skrapa CSS-element direkt från sidan, rekommenderar Adobe att detta görs som en sista utväg. Om webbplatslayouten ändras slutar de CSS-väljare som används i Launch att fungera, vilket orsakar dataförlust.

## Använd Adobe Experience Platform Launch för att skapa dataelement

[Dataelement är ](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) komponenter i Launch som du kan använda i hela verktyget. Du kan tilldela variabelvärden i Adobe Analytics-tillägget med dataelement.

1. Gå till [Adobe Experience Platform Launch](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på önskad Launch-egenskap.
1. Klicka på fliken **[!UICONTROL Data Elements]** och sedan på **[!UICONTROL Add Data Element]**.

   ![skapa dataelement](assets/createelement.png)

1. Ange ett namn för dataelementet. Det kan vara en enkel etikett som motsvarar en JavaScript-variabel i datalagret som du vill spåra.
1. Välj **[!UICONTROL Core]** i listrutan **[!UICONTROL Extension]**.
1. Välj **[!UICONTROL JavaScript Variable]** i listrutan **[!UICONTROL Data Element Type]**. Ett textfält visas till höger där du kan ange JavaScript-variabeln som ska mappas till det här dataelementet.
1. Ange önskad JavaScript-variabel, vanligtvis i datalagret. Om organisationens datalager till exempel överensstämmer med den praxis som rekommenderas av Adobe kan värdet vara `digitalData.page.pageInfo.pageName`. Du kan använda webbläsarens konsol för att validera JavaScript-variabelsyntax och -värden.
1. Klicka på **[!UICONTROL Save]**.

## Nästa steg

[Mappa dataelement till analysvariabler](elements-to-variable.md): Tilldela dataelement till Analytics-variabler så att ni kan använda dem som dimensioner i Analysis Workspace.
