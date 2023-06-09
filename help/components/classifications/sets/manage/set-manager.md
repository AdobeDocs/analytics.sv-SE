---
title: Klassificeringsuppsättningshanterare
description: Hantera klassificeringsuppsättningar i Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
source-git-commit: 496b4891d447ed9dd091a6498a792146a2d5aceb
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Klassificeringsuppsättningshanterare

Med Klassificeringsuppsättningshanteraren kan du skapa, redigera eller ta bort klassificeringsuppsättningar.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]**

Klassificeringsuppsättningar består av **Prenumerationer** (rapportpaket och dimensionskombinationer) och **Klassificeringsnamn** (dimensioner som innehåller klassificeringsdata). Prenumerationer konfigureras under [Inställningar](settings.md), medan klassificeringsnamn konfigureras under [Schema](schema.md).

## Filterklassificeringsuppsättningar

Den vänstra sidan av klassificeringsuppsättningshanteraren innehåller filterinställningar för att hitta önskad klassificeringsuppsättning. När du klickar på filterikonen växlas synligheten för filterinställningarna. Du kan filtrera klassificeringsuppsättningar efter **[!UICONTROL Tags]**, **[!UICONTROL Report suite]**, eller **[!UICONTROL Owner]**.

![Filter för klassificeringsuppsättning](../../assets/classification-set-filters.png)

## Hanteringskolumner för klassificeringsuppsättning

Följande kolumner är tillgängliga i Klassificeringsuppsättningshanteraren:

* **[!UICONTROL Classification set]**: Klassificeringsuppsättningens namn. Klicka på ett namn på en klassificeringsuppsättning [redigeringsinställningar](settings.md).
* **[!UICONTROL Subscriptions]**: Antalet prenumerationer som den här klassificeringsuppsättningen gäller för.
* **[!UICONTROL Owner]**: Klassificeringsuppsättningens ägare.
* **[!UICONTROL Classifications]**: Antalet klassificeringsdimensioner som klassificeringsuppsättningen innehåller.
* **[!UICONTROL Automated]**: Avgör om klassificeringsuppsättningen är konfigurerad att automatiskt importera data från en molnplats. Automatisering kan konfigureras i klassificeringsuppsättningens [schema](schema.md).
* **[!UICONTROL Last Modified]**: Det datum och den tidpunkt då klassificeringsuppsättningen senast ändrades.

## Skapa eller redigera alternativ

Följande knappar är tillgängliga i Klassificeringsuppsättningshanteraren:

* **[!UICONTROL Add]**: [Skapa](create.md) en klassificeringsuppsättning.
* **[!UICONTROL Search by title]**: Sök efter klassificeringsuppsättningar efter namn.
* **[!UICONTROL Load more]**: Klassificeringsuppsättningshanteraren visar först upp till 1 000 klassificeringsuppsättningar. Den här knappen läser in ytterligare 1 000 klassificeringsuppsättningar.
* **Visa/dölj kolumner**: Växla synlighet för alla kolumner förutom [!UICONTROL Classification set].

Välj en eller flera klassificeringsuppsättningar genom att klicka i kryssrutan bredvid önskad klassificeringsuppsättning. Om du väljer en klassificeringsuppsättning visas följande alternativ:

* **[!UICONTROL Tag]**: Lägg till en eller flera taggar i de markerade klassificeringsuppsättningarna, så att du kan ordna eller gruppera klassificeringsuppsättningar så att de blir lättare att hitta i framtiden.
* **[!UICONTROL Delete]**: Tar bort klassificeringsuppsättningen. Klassificeringsdimensioner baserade på den här klassificeringsuppsättningen är inte längre tillgängliga. Schemalagda projekt med den borttagna klassificeringsuppsättningen fortsätter att använda beroende dimensioner tills du sparar om det schemalagda projektet.
* **[!UICONTROL Consolidate]**: Starta en ny [konsolidering](../consolidations/process.md).
* **[!UICONTROL Rename]**: Byt namn på den valda klassificeringsuppsättningen.
