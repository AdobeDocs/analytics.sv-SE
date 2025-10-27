---
title: Inställningar för klassificeringsuppsättning
description: Lär dig hur du skapar eller redigerar en klassificeringsuppsättning.
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
feature: Classifications
source-git-commit: 2ced7cd61c4119347be2ef0fba9b8d60ee6c4df2
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 0%

---

# Inställningar för klassificeringsuppsättning

Du kan redigera de ursprungliga inställningarna för en klassificeringsuppsättning.

Så här redigerar du inställningarna för en klassificeringsuppsättning:


1. Välj **[!UICONTROL Components]** i Adobe Analytics övre menyrad och välj sedan **[!UICONTROL Classification sets]**.
1. I **[!UICONTROL Classification Sets]** väljer du fliken **[!UICONTROL Classification Sets]**.
1. I hanteraren för **[!UICONTROL Classifications Sets]** väljer du den klassificeringsgrupp som du vill redigera schemat för.
1. Välj fliken **[!UICONTROL Classification Set: _i dialogrutan_]** klassificeringsuppsättning **[!UICONTROL Settings]**.

1. I dialogrutan **[!UICONTROL Classification Set: _klassificeringsuppsättning_]**, där så är lämpligt:

   ![Klassificeringsuppsättningar - inställningar](assets/classification-sets-settings.png)

   1. Redigera **[!UICONTROL Name]**.
   1. Redigera en **[!UICONTROL Description (optional)]**.
   1. Redigera listan med e-postadresser (kommaavgränsare) i **[!UICONTROL Notify of issues]**. Dessa användare meddelas via e-post om eventuella problem.
   1. Lägg till en eller flera **[!UICONTROL Tags (optional)]** i klassificeringsuppsättningen. Välj en befintlig tagg i listrutan **[!UICONTROL Tags]** eller ange en ny tagg. Använd ![CrossSize100](/help/assets/icons/CrossSize100.svg) för att ta bort en tagg.
   1. Redigera **[!UICONTROL Subscriptions]**.
      * Du kan definiera flera **[!UICONTROL Report Suite]**- och **[!UICONTROL Dimension]**-kombinationer till en klassificeringsuppsättning.
      * Välj ![CrossSize400](/help/assets/icons/CrossSize400.svg) om du vill ta bort en kombination av **[!UICONTROL Report Suite]** och **[!UICONTROL Key Dimension]**.

      Mer information finns i [Skapa en klassificeringsuppsättning](create.md).

   1. Välj **[!UICONTROL Save]** om du vill spara inställningarna. Välj **[!UICONTROL Cancel]** om du vill avbryta.


<!--

Configure a classification set's settings.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Click the desired classification set name > **[!UICONTROL Settings]**

![classification set settings](../../assets/classification-set-settings.png)

The following fields are available in this tab:

* **[!UICONTROL Name]**: The classification set name.
* **[!UICONTROL Description]**: The description for the classification set.
* **[!UICONTROL Notify of issues]**: A comma-delimited list of email addresses that are notified of issues with this classification set.
* **[!UICONTROL Tags]**: Add one or more tags to the selected classification set. Tags allow you to organize or group classification sets so that it is easier to locate them in the future.
* **[!UICONTROL Type]**: The type of classification between [!UICONTROL Primary] and [!UICONTROL Lookup]. Primary classifications are typically used. You cannot alter a classification set's type after it is created.
* **[!UICONTROL Subscriptions]**: The report suite and dimension combinations that the classification set applies to.

-->