---
description: Beroende på dina behörigheter kan du dela segment med hela organisationen, grupper eller enskilda användare.
title: Dela segment
feature: Segmentation
exl-id: f51a0d1b-d293-4b41-b1dd-a79da841d94a
source-git-commit: 842f4226572ac38d01ddf16ad0b9991abbd3e906
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Dela segment

Beroende på dina behörigheter kan du dela segment med hela organisationen, grupper eller enskilda användare.

| Administratör | Kan dela segment med alla, med grupper och med användare. Grupper konfigureras som behörighetsgrupper i Admin Console. |
|---|---|
| Icke-administratör | Kan endast dela segment med enskilda användare. |

När ska ni dela segment med hela företaget jämfört med bara en grupp användare eller enskilda? Här är några tips du kan följa:

* Som administratör kan du dela ett segment med **[!UICONTROL All]** om det används av hela företaget och alla känner sig bekväma med att använda det. I det här fallet bör du även överväga att göra det till ett [godkänt](/help/components/segmentation/segmentation-workflow/seg-approve.md)-segment.

* Som administratör kan du dela ett segment med en specifik **[!UICONTROL Group]** om segmentet ger ett bra affärsvärde för det teamet. Godkänn inte den här typen av segment officiellt.
* Som administratör eller enskild användare kan du dela ett segment med andra personer för att granska och validera ett segment. Om det inte visar sig användbart kan det kasseras. Godkänn inte den här typen av segment officiellt.

1. Markera kryssrutan ![SelectBox](/help/assets/icons/SelectBox.svg) bredvid segmentet som du vill dela i segmenthanteraren.
1. Välj ![Dela](/help/assets/icons/Share.svg) Dela.
1. I dialogrutan **[!UICONTROL Share Segments]**:

   ![Dela segment](assets/share-segments-dialog.png)

   Om du är administratör kan du välja **[!UICONTROL All]** eller välja mellan **[!UICONTROL Groups]** och **[!UICONTROL Users]** i din organisation. Som icke-administratör kan du bara se enskilda användare. Använd fältet **[!UICONTROL Search]** för att söka efter grupper eller användare. 1.

   1. (valfritt) Använd ![Sök](/help/assets/icons/Search.svg) för att *söka efter enskilda personer eller grupper* och begränsa listan med grupper eller individer som du vill dela segmentet med.

   1. Välj **[!UICONTROL Save]** om du vill dela segmenten. Välj **[!UICONTROL Cancel]** om du vill avbryta.




   Ikonen Delad visas bredvid segmentet: ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)

1. Du kan filtrera segment som delas med dig genom att gå till **[!UICONTROL Filters]** > **[!UICONTROL Other Filters]** > **[!UICONTROL Shared with Me]**.

## God praxis

Nedan följer några tips om hur du bör dela segment och med vilka du bör dela segment.

* Som administratör kan du bara dela ett segment med Alla om du är övertygad om att någon i organisationen känner sig bekväm med att använda segmenten. Du kan också överväga att prioritera dessa segment. Mer information finns i [Markera ett segment som favorit](t-seg-favorite.md).

* Som administratör kan du dela ett segment med en viss grupp om det segmentet ger affärsvärdet för användarna som ingår i gruppen.

* Som administratör eller enskild användare kan du dela ett segment med en eller flera personer för att validera ett segment. Om segmenten inte visar sig vara användbara kan du ta bort segmentet.
