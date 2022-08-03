---
description: Gör att du enkelt kan visualisera jämförelsedata i Analysis Workspace, t.ex. skapa jämförelser till förra månaden, förra året och så vidare.
title: Visualisering av kombinationsdiagram
feature: Visualizations
role: User, Admin
source-git-commit: 04a314e93a77ecf5687e771e143bf68ba911b32b
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---


# Kombinationsdiagram

>[!NOTE]
>
>Den här funktionen finns för närvarande i [begränsad testning](/help/release-notes/releases.md).

The [!UICONTROL Combo chart] visualisering gör det enkelt att snabbt skapa en jämförelsevisualisering utan att först behöva skapa en tabell. Du kan enkelt visa trender i dina data i en kombination av rad och rad.

Använd ett kombinationsdiagram för att

* Jämför den här veckans order med order vid samma tidpunkt förra månaden (och förra året) - allt med bara några klick.

* Analysera och jämför snabbt olika mätvärden (som [!UICONTROL Unique Visitors] och [!UICONTROL Revenue]) mot varandra i samma diagram.

* Analysera ett mått mot en funktion (som [!UICONTROL Cumulative Average]) över en tidsperiod.

## Skapa ett kombinationsdiagram

1. Dra i listrutan Visualiseringar i den vänstra listen [!UICONTROL Combo chart] visualisering till en tom panel.

   ![](assets/combo-chart-build.png)

1. I listrutorna väljer du en dimension för X-axeln och ett mått för Y-axeln.

1. Välj typ av [!UICONTROL Line comparison] som du vill använda.

   | Jämförelsetyp | Definition |
   | --- | --- |
   | Tidsperiod | Den vanligaste typen av jämförelse - till exempel en jämförelse mellan den här tidsperioden och för 4 veckor sedan. Om du valde Tidsperiod väljer du en andra period som du vill jämföra med.<p>![](assets/combo-time-period.png) |
   | Ytterligare mått | Du kan till exempel jämföra [!UICONTROL Revenue] till ett annat mätvärde. |
   |  -funktion | Du kan presentera en funktion som [!UICONTROL Average] i jämförelsen. |

1. Klicka på **[!UICONTROL Build]**.

   Utdata ser ut ungefär så här:

   ![](assets/combo-output.png)





