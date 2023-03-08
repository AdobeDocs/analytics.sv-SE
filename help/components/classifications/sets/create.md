---
title: Skapa en klassificeringsuppsättning
description: Tillgängliga fält och beskrivningar när du skapar en klassificeringsuppsättning.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# Skapa en klassificeringsuppsättning

Du kan använda klassificeringsuppsättningshanteraren för att skapa en klassificeringsuppsättning.

>[!NOTE]
>
>Den här funktionen är tillgänglig för alla kunder som har sina rapportsviter migrerade till den nya klassifikationsarkitekturen. Kontakta Adobe kundtjänst eller din kontoansvarige om du vill ha mer information.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

När du skapar en klassificeringsuppsättning är följande fält tillgängliga.

* **[!UICONTROL Name]**: Ett textfält som används för att identifiera klassificeringsuppsättningen. Det går inte att redigera det här fältet när det skapas, men du kan byta namn senare.
* **[!UICONTROL Column Name]**: Namnet på den klassificeringsdimension som du vill skapa. Det här fältet är dimensionsnamnet som används i Analysis Workspace och kolumnnamnet när klassificeringsdata exporteras.
* **[!UICONTROL Type]**: Alternativknappar som anger klassificeringstypen. Primära klassificeringar används vanligen. Uppslagsklassificeringar representerar [Underklassificeringar](../c-sub-classifications.md).
* **[!UICONTROL Subscriptions]** Rapportsviten och dimensionen som den här klassificeringsuppsättningen gäller för. Stöd för flera rapportsviter planeras.

![Skapa en klassificeringsuppsättning](../assets/classification-set-create.png)

Om det finns en klassificeringsuppsättning för en viss Report Suite +-variabel läggs klassificeringen till i schemat i stället.
