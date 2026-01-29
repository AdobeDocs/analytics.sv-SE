---
title: Skapa klassificeringsuppsättningar
description: Lär dig hur du skapar en klassificeringsuppsättning i Tillgängliga fält och beskrivningar.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 993bef6137bbcda98cb6f09f9e8644db44e7d8cb
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 0%

---

# Skapa och redigera klassificeringsuppsättningar

Du [skapar](#create-a-classification-set) och [redigerar](#edit-a-classification-set) klassificeringsuppsättningar från hanteraren för klassificeringsuppsättningar.

## Skapa en klassificeringsuppsättning

Så här skapar du en klassificeringsuppsättning:

1. Välj **[!UICONTROL Components]** i Adobe Analytics övre menyrad och välj sedan **[!UICONTROL Classification sets]**.
1. I **[!UICONTROL Classification Sets]** väljer du fliken **[!UICONTROL Classification Sets]**.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]**.
1. I dialogrutan **[!UICONTROL Add New Classification Set]**:

   ![Klassificeringsuppsättningar - Lägg till ny klassificeringsuppsättning](assets/classifications-sets-new.png)

   1. Ange **[!UICONTROL Name]**. Till exempel: `Classification Set Example`.
   1. Ange **[!UICONTROL Description (optional)]**. Exempel: `Example classification set`.
   1. Ange en eller flera e-postadresser (kommaavgränsade) i **[!UICONTROL Notify of issues]**. E-postmeddelanden skickas till de här användarna om problem uppstår.
   1. Välj **[!UICONTROL Type]** för klassificeringsuppsättningen. Möjliga typer är:
      * **[!UICONTROL Primary]**. En primär klassificeringsuppsättning gäller för dimensioner som samlats in i Adobe Analytics. Primära klassificeringar är ett sätt att gruppera (klassificera) granulära dimensionsvärden till mer meningsfulla datanivåer. Du kanske vill gruppera interna söknyckelord i interna sökkategorier för att förstå teman i dina sökdata. Eller klassificera produktens SKU:er efter färg eller kategori.
         * Ange en eller flera **[!UICONTROL Subscriptions]**.  Du kan definiera flera **[!UICONTROL Report Suite]**- och **[!UICONTROL Dimension]**-kombinationer till en klassificeringsuppsättning.

         * Välj ![CrossSize400](/help/assets/icons/CrossSize400.svg) om du vill ta bort en kombination av **[!UICONTROL Report Suite]** och **[!UICONTROL Key Dimension]**.

        Om du lägger till en **[!UICONTROL Report Suite]**- och **[!UICONTROL Key Dimension]**-kombination som redan finns i en annan klassificeringsuppsättning visas ett rött färgat meddelande.
Ni kan:
         * Välj **[!UICONTROL Add to existing]** om du vill öppna den andra klassificeringsuppsättningen och [lägga till klassificeringar i schemat ](manage/schema.md) för den andra klassificeringsuppsättningen.
         * Ändra **[!UICONTROL Report Suite]** och **[!UICONTROL Key Dimension]** till en kombination som inte redan prenumererar på en annan klassificeringsuppsättning.
      * **[!UICONTROL Lookup]**. En uppslagstabell kallas vanligen för underklassificeringar eller underklassificeringar och är en klassificering av en primär klassificering. En sökning är metadata om ett klassificeringsvärde i stället för den ursprungliga dimensionen. En *Produkt*-dimension kan till exempel ha en primär klassificering av *Färgkod*. En uppslagstabell med *färgnamn* kan sedan bifogas till *färgkoden* för att förklara varje färgkod.
1. Välj **[!UICONTROL Save]** om du vill spara klassificeringsuppsättningen. Välj **[!UICONTROL Cancel]** om du vill avbryta definitionen.
1. Om du vill definiera schemat för klassificeringsuppsättningen väljer du den nya klassificeringsuppsättningen i hanteraren **[!UICONTROL Classification Sets]** och [redigerar klassificeringsuppsättningen](#edit-a-classification-set).


## Redigera en klassificeringsuppsättning

Så här redigerar du en klassificeringsuppsättning:

1. Välj **[!UICONTROL Components]** i Adobe Analytics övre menyrad och välj sedan **[!UICONTROL Classification sets]**.
1. I **[!UICONTROL Classification Sets]** väljer du fliken **[!UICONTROL Classification Sets]**.
1. Välj namnet på din klassificeringsgrupp.
1. I dialogrutan **[!UICONTROL Classification Set: _klassificeringsuppsättningsnamn_]** kan du definiera [inställningarna](manage/settings.md) och [schemat](manage/schema.md) för klassificeringsuppsättningen.
1. När du är klar väljer du **[!UICONTROL Save]** för att spara ändringarna. Välj **[!UICONTROL Cancel]** om du vill avbryta.
