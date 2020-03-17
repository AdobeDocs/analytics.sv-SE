---
description: (Valfritt) Innan du importerar klassificeringar till marknadsföringsrapporter kan du hämta en mall som hjälper dig att skapa en klassificeringsdatafil. I datafilen används de klassificeringar du vill använda som kolumnrubriker, och sedan ordnas rapportdatauppsättningen under rätt klassificeringsrubriker.
subtopic: Classifications
title: Klassificeringsmall
topic: Admin tools
uuid: 4edd411b-164c-4b4d-a872-b57a3163ca72
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Klassificeringsmall

(Valfritt) Innan du importerar klassificeringar till marknadsföringsrapporter kan du hämta en mall som hjälper dig att skapa en klassificeringsdatafil. I datafilen används de klassificeringar du vill använda som kolumnrubriker, och sedan ordnas rapportdatauppsättningen under rätt klassificeringsrubriker.

## Klassificeringsmall {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Valfritt) Innan du importerar klassificeringar till marknadsföringsrapporter kan du hämta en mall som hjälper dig att skapa en klassificeringsdatafil. I datafilen används de klassificeringar du vill använda som kolumnrubriker, och sedan ordnas rapportdatauppsättningen under rätt klassificeringsrubriker.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

| Element | Beskrivning |
|---|---|
| Välj Report Suite | Välj den rapportsvit som ska användas i mallen. Rapportsviten och datauppsättningen måste matcha. |
| Datauppsättning som ska klassificeras | Välj datatyp för datafilen. Menyn innehåller alla rapporter i rapportsviterna som är konfigurerade för klassificeringar. |
| Exportera numeriskt 2 | Du kan importera numeriska 2 klassificeringar till systemet via importeraren. Numeriska 2-klassificeringar är användbara för variabler som ändras över tid för olika artiklar, till exempel kostnads- och budgetvärden för [!UICONTROL Marketing Channel] rapporten. Mer information om hur du överför data med hjälp av numeriska 2-klassificeringar finns i [Numeriska 2-klassificeringar](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md) . |
| Kodning | Välj teckenkodning för datafilen. Standardkodningsformatet är UTF-8. |
| Hämta | Hämtar mallfilen. |

Mallen innehåller de för närvarande definierade klassificeringarna (kolumnrubriker) för en viss datauppsättning utan att inkludera de data som är kopplade till varje klassificering.

> [!NOTE] Mallmetoden begränsar nedladdningen av klassificeringsdata till en enda rapportserie.

Mer information om datafilens struktur finns i [Klassificeringsdatafiler](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).

## Hämta en mall för klassificeringsdata (valfritt) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

Mallen innehåller det filformat som du måste följa för klassificeringar.

> [!NOTE] Mallmetoden begränsar datainläsningen till en enda rapportserie.

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. På **[!UICONTROL Download Template]** fliken anger du [datamallens konfiguration](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md).
1. Klicka på **[!UICONTROL Download]**.
1. Spara mallfilen på ditt lokala system.

   Mallfilen är en tabbavgränsad datafil ( [!DNL .tab] filnamnstillägg) som stöds av de flesta kalkylbladsprogram.

