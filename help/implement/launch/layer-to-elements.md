---
title: Mappa datalagerobjekt till dataelement
description: Konfigurera taggar som ska läsas från datalagret.
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 5%

---

# Mappa datalagerobjekt till dataelement

När organisationen har etablerat och implementerat ett datalager på webbplatsen kan du mappa datalagerobjekt till dataelement inom taggar.

>[!NOTE]
>Adobe Experience Platform Launch har omklassificerats som en serie datainsamlingstekniker i Experience Platform. Som ett resultat av detta har flera terminologiska förändringar införts i produktdokumentationen. Se följande [dokument](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) för en konsoliderad referens till terminologiska ändringar.

## Förutsättningar

[Skapa ett datalager](../prepare/data-layer.md): Kontrollera att det finns ett datalager på platsen. Även om du tekniskt kan mappa ett JavaScript-objekt eller skrapa CSS-element direkt från sidan, rekommenderar Adobe att detta görs som en sista utväg. Om platslayouten ändras slutar de CSS-väljare som används i -taggar att fungera, vilket orsakar dataförlust.

## Använd taggar för att skapa dataelement

[Dataelement är ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=en) komponenter i användargränssnittet för datainsamling som du kan använda i hela verktyget. Du kan tilldela variabelvärden i Adobe Analytics-tillägget med dataelement.

1. Gå till [experience.adobe.com](https://experience.adobe.com) och logga in när du uppmanas till det.
1. Välj **[!UICONTROL Launch / Data Collection]**.
1. Klicka på **[!UICONTROL Go to Launch / Data Collection]** och välj sedan **[!UICONTROL Tags]**.
1. Klicka på den önskade taggegenskapen.
1. Klicka på fliken **[!UICONTROL Data Elements]** och sedan på **[!UICONTROL Add Data Element]**.

   ![skapa dataelement](assets/createelement.png)

1. Ange ett namn för dataelementet. Det kan vara en enkel etikett som motsvarar en JavaScript-variabel i datalagret som du vill spåra.
1. Välj **[!UICONTROL Core]** i listrutan **[!UICONTROL Extension]**.
1. Välj **[!UICONTROL JavaScript Variable]** i listrutan **[!UICONTROL Data Element Type]**. Ett textfält visas till höger där du kan ange JavaScript-variabeln som ska mappas till det här dataelementet.
1. Ange önskad JavaScript-variabel, vanligtvis i datalagret. Om organisationens datalager till exempel överensstämmer med den praxis som rekommenderas av Adobe kan värdet vara `digitalData.page.pageInfo.pageName`. Du kan använda webbläsarens konsol för att validera JavaScript-variabelsyntax och -värden.
1. Klicka på **[!UICONTROL Save]**.

## Nästa steg

[Mappa dataelement till analysvariabler](elements-to-variable.md): Tilldela dataelement till Analytics-variabler så att ni kan använda dem som dimensioner i Analysis Workspace.
