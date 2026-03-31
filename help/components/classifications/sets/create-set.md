---
title: Skapa och redigera klassificeringsuppsättningar
description: Lär dig hur du skapar och redigerar klassificeringsuppsättningar i Adobe Analytics, inklusive primära klassificeringstyper och sökklassificeringstyper, prenumerationer och jobbmeddelanden.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 9feefd318d5239812f62afd727836e8aa203a4b2
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Skapa och redigera klassificeringsuppsättningar

Du [skapar](#create-a-classification-set) och [redigerar](#edit-a-classification-set) klassificeringsuppsättningar från hanteraren för klassificeringsuppsättningar.

## Skapa en klassificeringsuppsättning

Så här skapar du en klassificeringsuppsättning:

1. Välj **[!UICONTROL Components]** i Adobe Analytics övre menyrad och välj sedan **[!UICONTROL Classification sets]**.
1. I **[!UICONTROL Classification sets]** väljer du fliken **[!UICONTROL Classification sets]**.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]**.
1. I dialogrutan **[!UICONTROL Add New Classification Set]**:

   ![Klassificeringsuppsättningar - Lägg till ny klassificeringsuppsättning](assets/classifications-sets-new.png)

   1. Ange **[!UICONTROL Name]**. Till exempel: `Classification Set Example`.
   1. Ange **[!UICONTROL Description (optional)]**. Exempel: `Example classification set`.
   1. Välj **[!UICONTROL Type]** för klassificeringsuppsättningen. Möjliga typer är:
      * **[!UICONTROL Primary]**. En primär klassificeringsuppsättning gäller för dimensioner som samlats in i Adobe Analytics. Primära klassificeringar är ett sätt att gruppera (klassificera) granulära dimensionsvärden till mer meningsfulla datanivåer. Du kanske vill gruppera interna söknyckelord i interna sökkategorier för att förstå teman i dina sökdata. Eller klassificera produktens SKU:er efter färg eller kategori.
      * **[!UICONTROL Lookup]**. En uppslagstabell kallas vanligen för underklassificeringar eller underklassificeringar och är en klassificering av en primär klassificering. En sökning är metadata om ett klassificeringsvärde i stället för den ursprungliga dimensionen. En *Produkt*-dimension kan till exempel ha en primär klassificering av *Färgkod*. En uppslagstabell med *färgnamn* kan sedan bifogas till *färgkoden* för att förklara varje färgkod.
1. I avsnittet **[!UICONTROL Job notifications]** väljer du vem du vill meddela om klassificeringsuppsättningsjobben misslyckas eller lyckas.
   * Så här meddelar du användare om ett fel inträffar:
      1. Aktivera **[!UICONTROL Notify on failure]**.
      1. Ange en eller flera kommaseparerade e-postadresser i **[!UICONTROL Failure email recipients]**.
   * Så här meddelar du användare om det lyckas:
      1. Aktivera **[!UICONTROL Notify on success]**.
      1. Ange en eller flera kommaseparerade e-postadresser i **[!UICONTROL Success email recipients]**.
1. I avsnittet **[!UICONTROL Subscriptions]** anger du en eller flera **[!UICONTROL Primary]** om du har valt **[!UICONTROL Subscriptions]**.  Du kan definiera flera **[!UICONTROL Report Suite]**- och **[!UICONTROL Dimension]**-kombinationer till en klassificeringsuppsättning.

   * Välj ![CrossSize400](/help/assets/icons/CrossSize400.svg) om du vill ta bort en kombination av **[!UICONTROL Report Suite]** och **[!UICONTROL Key Dimension]**.

   Om du lägger till en **[!UICONTROL Report Suite]**- och **[!UICONTROL Key Dimension]**-kombination som redan finns i en annan klassificeringsuppsättning visas ett rött färgat meddelande.
Ni kan:
   * Välj **[!UICONTROL Add to existing]** om du vill öppna den andra klassificeringsuppsättningen och [lägga till klassificeringar i schemat ](manage/schema.md) för den andra klassificeringsuppsättningen.
   * Ändra **[!UICONTROL Report Suite]** och **[!UICONTROL Key Dimension]** till en kombination som inte redan prenumererar på en annan klassificeringsuppsättning.
1. Välj **[!UICONTROL Save]** om du vill spara klassificeringsuppsättningen. Välj **[!UICONTROL Cancel]** om du vill avbryta definitionen.

Om du vill definiera schemat för klassificeringsuppsättningen väljer du den nya klassificeringsuppsättningen i hanteraren **[!UICONTROL Classification Sets]** och [redigerar klassificeringsuppsättningen](#edit-a-classification-set).


## Redigera en klassificeringsuppsättning

Så här redigerar du en klassificeringsuppsättning:

1. Välj **[!UICONTROL Components]** i Adobe Analytics övre menyrad och välj sedan **[!UICONTROL Classification sets]**.
1. I **[!UICONTROL Classification Sets]** väljer du fliken **[!UICONTROL Classification Sets]**.
1. Välj namnet på din klassificeringsgrupp.
1. I dialogrutan **[!UICONTROL Classification Set: _klassificeringsuppsättningsnamn_]** kan du definiera [inställningarna](manage/settings.md) och [schemat](manage/schema.md) för klassificeringsuppsättningen.
1. När du är klar väljer du **[!UICONTROL Save]** för att spara ändringarna. Välj **[!UICONTROL Cancel]** om du vill avbryta.
