---
description: (Valfritt) Innan du importerar klassificeringar till marknadsföringsrapporter kan du hämta en mall som hjälper dig att skapa en klassificeringsdatafil. I datafilen används de klassificeringar du vill använda som kolumnrubriker, och sedan ordnas rapportdatauppsättningen under rätt klassificeringsrubriker.
subtopic: Classifications
title: Klassificeringsmall
feature: Administratörsverktyg
uuid: 4edd411b-164c-4b4d-a872-b57a3163ca72
source-git-commit: eb256b6d8308792747710284d2bfbaa4b5044b2a
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 3%

---


# Klassificeringsmall

(Valfritt) Innan du importerar klassificeringar till rapporter och projekt kan du hämta en mall som hjälper dig att skapa en klassificeringsdatafil. I datafilen används de klassificeringar du vill använda som kolumnrubriker, och sedan ordnas rapportdatauppsättningen under rätt klassificeringsrubriker.

## Klassificeringsmall {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Valfritt) Innan du importerar klassificeringar till marknadsföringsrapporter kan du hämta en mall som hjälper dig att skapa en klassificeringsdatafil. I datafilen används de klassificeringar du vill använda som kolumnrubriker, och sedan ordnas rapportdatauppsättningen under rätt klassificeringsrubriker.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

| Element | Beskrivning |
| --- | ---|
| Välj Report Suite | Välj den rapportsvit som ska användas i mallen. Rapportsviten och datauppsättningen måste matcha. |
| Datauppsättning som ska klassificeras | Välj datatyp för datafilen. Menyn innehåller alla rapporter i rapportsviterna som är konfigurerade för klassificeringar. |
| Exportera numeriskt 2 | **Viktigt**: Det här alternativet är inte tillgängligt för rapportsviter som har aktiverats för den nya klassificeringsarkitekturen. |
| Kodning | Välj teckenkodning för datafilen. Standardkodningsformatet är UTF-8.<br>**Viktigt**: Det här alternativet är inte tillgängligt för rapportsviter som har aktiverats för den nya klassificeringsarkitekturen. |
| Hämta | Hämtar mallfilen. |

Mallen innehåller de för närvarande definierade klassificeringarna (kolumnrubriker) för en viss datauppsättning utan att inkludera de data som är kopplade till varje klassificering.

>[!NOTE]
>
>Mallmetoden begränsar nedladdningen av klassificeringsdata till en enda rapportserie.

Mer information om datafilens struktur finns i [Om klassificeringsdatafiler](/help/components/classifications/importer/c-saint-data-files.md).

## Hämta en mall för klassificeringsdata (valfritt) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

Mallen innehåller det filformat som du måste följa för klassificeringar.

>[!NOTE]
>
>Mallmetoden begränsar datainläsningen till en enda rapportserie.

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. På fliken **[!UICONTROL Download Template]** anger du [datamallskonfigurationen](/help/components/classifications/importer/c-download-saint-data.md).
1. Klicka på **[!UICONTROL Download]**.
1. Spara mallfilen på ditt lokala system.

   Mallfilen är en tabbavgränsad datafil ( [!DNL .tab] filnamnstillägg) som stöds i de flesta kalkylbladsprogram.

