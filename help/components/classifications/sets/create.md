---
title: Skapa en klassificeringsuppsättning
description: Tillgängliga fält och beskrivningar när du skapar en klassificeringsuppsättning.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 0%

---

# Skapa en klassificeringsuppsättning

Du kan använda klassificeringsuppsättningshanteraren för att skapa en klassificeringsuppsättning.

>[!NOTE]
>
>Den här funktionen är för närvarande i begränsad version. Om du vill ha tillgång till den här funktionen kontaktar du kundtjänst på Adobe eller kontohanteraren som kan vidarebefordra din begäran till klassificeringsgruppen för etablering.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

När du skapar en klassificeringsuppsättning är följande fält tillgängliga.

* **[!UICONTROL Name]**: Ett textfält som används för att identifiera klassificeringsuppsättningen. Det går inte att redigera det här fältet när det skapas, men du kan byta namn senare.
* **[!UICONTROL Column Name]**: Namnet på den klassificeringsdimension som du vill skapa. Det här fältet är dimensionsnamnet som används i Analysis Workspace och kolumnnamnet när klassificeringsdata exporteras.
* **[!UICONTROL Type]**: Alternativknappar som anger klassificeringstypen. Primära klassificeringar används vanligen. Uppslagsklassificeringar representerar [Underklassificeringar](../c-sub-classifications.md).
* **[!UICONTROL Subscriptions]** Rapportsviten och dimensionen som den här klassificeringsuppsättningen gäller för. Stöd för flera rapportsviter planeras.

![Skapa en klassificeringsuppsättning](../assets/classification-set-create.png)

Om det finns en klassificeringsuppsättning för en viss Report Suite +-variabel läggs klassificeringen till i schemat i stället.
