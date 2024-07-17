---
title: Mappa datalagerobjekt till dataelement
description: Konfigurera taggar som ska läsas från datalagret.
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 1%

---

# Mappa datalagerobjekt till dataelement

När organisationen har etablerat och implementerat ett datalager på webbplatsen kan du mappa datalagerobjekt till dataelement inom taggar.

## Förutsättningar

[Skapa ett datalager](../prepare/data-layer.md): Kontrollera att det finns ett datalager på platsen. Även om du tekniskt kan mappa ett JavaScript-objekt eller skrapa CSS-element direkt från sidan rekommenderar Adobe denna metod som en sista utväg. Om platslayouten ändras slutar de CSS-väljare som används i -taggar att fungera, vilket orsakar dataförlust.

## Använd taggar för att skapa dataelement

[Dataelement](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html) är komponenter i Adobe Experience Platform Data Collection som du kan använda i hela verktyget. Du kan tilldela variabelvärden i Adobe Analytics-tillägget med dataelement.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Klicka på fliken **[!UICONTROL Data Elements]** och sedan på **[!UICONTROL Add Data Element]**.

   ![skapa dataelement](assets/createelement.png)

1. Ange ett namn för dataelementet. Det kan vara en enkel etikett som motsvarar en JavaScript-variabel i datalagret som du vill spåra.
1. Välj **[!UICONTROL Core]** i listrutan **[!UICONTROL Extension]**.
1. Välj **[!UICONTROL JavaScript Variable]** i listrutan **[!UICONTROL Data Element Type]**. Ett textfält visas till höger där du kan ange JavaScript-variabeln för att mappa till det här dataelementet.
1. Ange önskad JavaScript-variabel, vanligtvis i datalagret. Om din organisations datalager till exempel överensstämmer med den praxis som rekommenderas av Adobe, kan värdet vara `digitalData.page.pageInfo.pageName`. Du kan använda webbläsarens konsol för att validera JavaScript variabelsyntax och -värden.
1. Klicka på **[!UICONTROL Save]**.

## Nästa steg

[Mappa dataelement till analysvariabler](elements-to-variable.md): Tilldela dataelement till analysvariabler så att du kan använda dem som mått i Analysis Workspace.
