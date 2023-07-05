---
title: Konsolideringshanterare för klassificeringsuppsättning
description: Konsolidera en eller flera klassificeringsuppsättningar i en enda klassificeringsuppsättning.
exl-id: 032e93f6-9c11-4522-a02e-376eb4fd98bf
feature: Classifications
source-git-commit: c697530103ea7cd279cc3560c1daec796759e7a1
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# Konsolideringshanterare för klassificeringsuppsättning

Om du har flera klassificeringsuppsättningar som innehåller liknande data kan du konsolidera dem till en enda klassificeringsuppsättning. När du konsoliderar två eller flera klassificeringsuppsättningar genererar Adobe en ny klassificeringsuppsättning som innehåller alla klassificeringsdata från varje enskild klassificeringsuppsättning. Konsolideringar är användbara när du har överfört data till många rapportsviter eller dimensioner som innehåller samma klassificeringsdata och vill sammanfoga dem i ett enda arbetsflöde.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]**

När en konsolidering har utförts tas de ursprungliga klassificeringsuppsättningarna bort och den konsoliderade klassificeringen ersätter dem. Klicka **[!UICONTROL Add]** till [Skapa en konsolidering](process.md).

## Filterklassificeringsuppsättningar

Den vänstra sidan av konsolideringshanteraren för klassificeringsuppsättningar innehåller filterinställningar för att hitta önskad konsolidering. När du klickar på filterikonen växlas synligheten för filterinställningarna. Du kan filtrera konsolideringar efter **[!UICONTROL Status]**, **[!UICONTROL Completion time]**, eller **[!UICONTROL Creation time]**.

![Konsolideringsfilter för klassificeringsuppsättning](../../assets/classification-set-consolidation-filters.png)

Ytterligare filteralternativ är tillgängliga ovanför kolumnerna för konsolideringshanteraren för klassificeringsuppsättningar:

* **[!UICONTROL Search by title]**: Sök efter konsolideringar efter namn.
* **Visa/dölj kolumner**: Växla synlighet för alla kolumner förutom [!UICONTROL Name].

## Konsolideringshanterarkolumner för klassificeringsuppsättning

Följande kolumner är tillgängliga i konsolideringshanteraren för klassificeringsuppsättningar:

* **[!UICONTROL Name]**: Konsolideringens namn.
* **[!UICONTROL Current job]**: Det aktuella jobbet. <!-- todo: better description -->
* **[!UICONTROL Status]**: Konsolideringens status. <!-- todo: get list of possible statuses -->
* **[!UICONTROL Creation date]**: Datum och tid då konsolideringen skapades.
* **[!UICONTROL Completion date]**: Datum och tid då konsolideringen slutfördes (eller misslyckades).
