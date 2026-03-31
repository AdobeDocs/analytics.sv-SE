---
title: Inställningar för klassificeringsuppsättning
description: Lär dig hur du redigerar namn, beskrivning, taggar, jobbmeddelanden och prenumerationer för en befintlig klassificeringsgrupp i Adobe Analytics.
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
feature: Classifications
source-git-commit: 47a88c1bf56acfc26794e5b9d5d6af41b697eed9
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# Inställningar för klassificeringsuppsättning

Du kan redigera inställningarna för en klassificeringsuppsättning, inklusive namn, beskrivning, vem som ska meddelas och prenumerationerna.

Så här redigerar du inställningarna för en klassificeringsuppsättning:

1. Välj **[!UICONTROL Components]** i Adobe Analytics övre menyrad och välj sedan **[!UICONTROL Classification sets]**.
1. I **[!UICONTROL Classification Sets]** väljer du fliken **[!UICONTROL Classification sets]**.
1. I hanteraren för **[!UICONTROL Classification sets]** väljer du den klassificeringsgrupp som du vill redigera schemat för.
1. I dialogrutan **[!UICONTROL Classification Set: _klassificeringsuppsättning_]** väljer du fliken **[!UICONTROL Settings]** för att redigera inställningar:

   ![Klassificeringsuppsättningar - inställningar](assets/classification-sets-settings.png)

   1. Redigera **[!UICONTROL Name]**.
   1. Redigera en **[!UICONTROL Description (optional)]**.
   1. Lägg till en eller flera **[!UICONTROL Tags (optional)]** i klassificeringsuppsättningen. Välj en befintlig tagg i listrutan **[!UICONTROL Tags]** eller ange en ny tagg. Använd ![CrossSize100](/help/assets/icons/CrossSize100.svg) för att ta bort en tagg.
   1. I avsnittet **[!UICONTROL Job notifications]** väljer du vem du vill meddela om klassificeringsuppsättningsjobben misslyckas eller lyckas.
      * Så här meddelar du användare om ett fel inträffar:
         1. aktivera **[!UICONTROL Notify on failure]**.
         1. Ange en eller flera kommaseparerade e-postadresser i **[!UICONTROL Failure email recipients]**.
      * Så här meddelar du användare om det lyckas:
         1. Aktivera **[!UICONTROL Notify on success]**.
         1. Ange en eller flera kommaseparerade e-postadresser i **[!UICONTROL Success email recipients]**.
   1. Redigera **[!UICONTROL Subscriptions]**.
      * Du kan definiera flera **[!UICONTROL Report Suite]**- och **[!UICONTROL Dimension]**-kombinationer till en klassificeringsuppsättning.
      * Välj ![CrossSize400](/help/assets/icons/CrossSize400.svg) om du vill ta bort en kombination av **[!UICONTROL Report Suite]** och **[!UICONTROL Key Dimension]**.

      Mer information finns i [Skapa en klassificeringsuppsättning](/help/components/classifications/sets/manage-sets.md).
   1. Välj **[!UICONTROL Save]** om du vill spara inställningarna. Välj **[!UICONTROL Cancel]** om du vill avbryta.
