---
title: Klassificeringsuppsättningshanteraren
description: Hantera klassificeringsuppsättningar i Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
source-git-commit: a1f199525c567bc9d7bb614ee03980f582cbbc7a
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Klassificeringsuppsättningshanteraren

Med Klassificeringsuppsättningshanteraren kan du skapa, redigera eller ta bort klassificeringsuppsättningar.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]**

Klassificeringsuppsättningar består av **Prenumerationer** (Rapporteringssviter som den här klassificeringsuppsättningen gäller för) och **Klassificeringsnamn** (De ytterligare dimensionerna som innehåller klassificeringsdata).

## Filterklassificeringsuppsättningar

Vänster sida av klassificeringsuppsättningshanteraren innehåller filterinställningar för att hitta önskad klassificeringsuppsättning. När du klickar på filterikonen växlas synligheten för filterinställningarna. Du kan filtrera klassificeringsuppsättningar efter **[!UICONTROL Tags]**, **[!UICONTROL Report suite]**, eller **[!UICONTROL Owner]**.

![Filter för klassificeringsuppsättning](../assets/classification-set-filters.png)

## Kolumner för klassificeringsuppsättningshanteraren

Följande kolumner är tillgängliga i Klassificeringsuppsättningshanteraren:

* **[!UICONTROL Classification Set]**: Klassificeringsuppsättningens namn. Klicka på ett namn på en klassificeringsuppsättning för att [redigera dess inställningar](settings.md).
* **[!UICONTROL Subscriptions]**: Antalet prenumerationer eller antalet rapportsviter som den här klassificeringsuppsättningen gäller för.
* **[!UICONTROL Owner]**: Ägaren till klassificeringsuppsättningen.
* **[!UICONTROL Classifications]**: Antalet klassificeringsdimensioner som klassificeringsuppsättningen innehåller.
* **[!UICONTROL Automated]**: Anger om klassificeringsuppsättningen är konfigurerad att hämta data automatiskt från en FTP-plats.
* **[!UICONTROL Last Modified]**: Det datum och den tidpunkt då klassificeringsuppsättningen senast ändrades.
* **[!UICONTROL FTP Host + Path]**: Om det är automatiserat hämtar FTP-platsen som Klassificeringsuppsättningen hämtar data från.

## Skapa eller redigera alternativ

Följande knappar är tillgängliga i Klassificeringsuppsättningshanteraren:

* **[!UICONTROL Add]**: [Skapa](create.md) en klassificeringsuppsättning.
* **[!UICONTROL Search by title]**: Sök efter klassificeringsuppsättningar efter namn.
* **[!UICONTROL Load more]**: Klassificeringsuppsättningshanteraren visar först upp till 1 000 klassificeringsuppsättningar. Klicka på den här knappen om du vill läsa in ytterligare 1 000 klassificeringsuppsättningar.
* **Visa/dölj kolumner**: Växla synlighet för alla kolumner förutom [!UICONTROL Classification Set].

Markera en eller flera klassificeringsuppsättningar genom att klicka i kryssrutan bredvid önskad klassificeringsuppsättning. Om du väljer en klassificeringsuppsättning visas följande alternativ:

* **[!UICONTROL Tag]**: Lägg till en eller flera taggar i de markerade klassificeringsuppsättningarna, som gör det enklare att hitta dem i framtiden genom att ordna eller gruppera klassificeringsuppsättningar.
* **[!UICONTROL Rename]**: Byt namn på den valda klassificeringsuppsättningen.
