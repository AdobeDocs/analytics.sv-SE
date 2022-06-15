---
title: Skapa en klassificeringsuppsättning
description: Tillgängliga fält och beskrivningar när du skapar en klassificeringsuppsättning.
source-git-commit: 7347fe573aaab86bdef51a9d74cbef0e091739d4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# Skapa en klassificeringsuppsättning

Du kan använda klassificeringsuppsättningshanteraren för att skapa en klassificeringsuppsättning.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

När du skapar en klassificeringsuppsättning är följande fält tillgängliga.

* **[!UICONTROL Name]**: Ett textfält som används för att identifiera klassificeringsuppsättningen. Det går inte att redigera det här fältet när det skapas, men du kan byta namn senare.
* **[!UICONTROL Column Name]**: Namnet på den klassificeringsdimension som du vill skapa. Det här fältet är dimensionsnamnet som används i Analysis Workspace och kolumnnamnet när klassificeringsdata exporteras.
* **[!UICONTROL Type]**: Alternativknappar som anger klassificeringstypen. Primära klassificeringar används vanligen. Uppslagsklassificeringar representerar [Underklassificeringar](../c-sub-classifications.md).
* **[!UICONTROL Subscriptions]** Rapportsviten och dimensionen som den här klassificeringsuppsättningen gäller för. Stöd för flera rapportsviter planeras.

Om det finns en klassificeringsuppsättning för en viss Report Suite +-variabel läggs klassificeringen till i schemat i stället.
