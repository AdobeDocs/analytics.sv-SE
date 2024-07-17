---
title: Skapa en klassificeringsuppsättning
description: Tillgängliga fält och beskrivningar när du skapar en klassificeringsuppsättning.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# Skapa en klassificeringsuppsättning

Du kan använda klassificeringsuppsättningshanteraren för att skapa en klassificeringsuppsättning.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

När du skapar en klassificeringsuppsättning är följande fält tillgängliga.

* **[!UICONTROL Name]**: Ett textfält som används för att identifiera klassificeringsuppsättningen. Det går inte att redigera det här fältet när det skapas, men du kan byta namn senare.
* **[!UICONTROL Column Name]**: Namnet på den första klassificeringsdimensionen som du vill skapa. Det här fältet är dimensionsnamnet som används i Analysis Workspace och kolumnnamnet när klassificeringsdata exporteras. Du kan lägga till fler kolumnnamn när klassificeringsuppsättningen har skapats.
* **[!UICONTROL Type]**: Alternativknappar som anger klassificeringstypen. Primära klassificeringar används vanligtvis. Uppslagsklassificeringar representerar [underklassificeringar](../../c-sub-classifications.md).
* **[!UICONTROL Subscriptions]** Rapportsviterna och dimensionerna som den här klassificeringsmängden gäller för. Du kan lägga till flera rapportsviter och dimensionskombinationer i en klassificeringsuppsättning.

![Skapa en klassificeringsuppsättning](../../assets/classification-set-create.png)

Om det finns en klassificeringsuppsättning för en viss rapportserie + variabel läggs klassificeringen till i schemat i stället. En given kombination av rapportserie och variabel kan inte tillhöra flera klassificeringsuppsättningar.
