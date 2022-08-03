---
description: Gör att du enkelt kan visualisera jämförelsedata i Analysis Workspace, t.ex. skapa jämförelser till förra månaden, förra året och så vidare.
title: Visualisering av kombinationsdiagram
feature: Visualizations
role: User, Admin
source-git-commit: e2cd08ae4109e037f8b54edf21239fa6fa659896
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 1%

---


# Kombinationsdiagram

>[!NOTE]
>
>Den här funktionen finns för närvarande i [begränsad testning](/help/release-notes/releases.md).

The [!UICONTROL Combo chart] visualisering gör det enkelt att snabbt skapa en jämförelsevisualisering utan att först behöva skapa en tabell. Du kan enkelt visa trender i dina data i en kombination av rad och rad.

Använd en [!UICONTROL Combo chart] till

* Jämför den här veckans order med order vid samma tidpunkt förra månaden (och förra året) - allt med bara några klick.

* Analysera och jämför snabbt olika mätvärden (som [!UICONTROL Unique Visitors] och [!UICONTROL Revenue]) mot varandra i samma diagram.

* Analysera ett mått mot en funktion (som [!UICONTROL Cumulative Average]) över en tidsperiod.

Kom ihåg att du kan

* Lägg till flera jämförelser i en enda [!UICONTROL Combo chart].
* Om du lägger till en eller flera jämförelser måste de vara av samma typ, till exempel en tidsperiod.
* Du kan lägga till upp till fem jämförelser.
* Du kan använda ett filter på ett mätresultat.

## Skapa ett kombinationsdiagram

1. Dra i listrutan Visualiseringar i den vänstra listen [!UICONTROL Combo chart] visualisering till en tom panel.

   ![](assets/combo-chart-build.png)

1. I listrutorna väljer du en dimension för X-axeln och ett mått för Y-axeln.

1. Välj typ av [!UICONTROL Line comparison] som du vill använda.

   | Jämförelsetyp | Definition |
   | --- | --- |
   | Tidsperiod | Den vanligaste typen av jämförelse - till exempel en jämförelse mellan den här tidsperioden och för 4 veckor sedan. Om du valde Tidsperiod väljer du en andra period som du vill jämföra med.<p>![](assets/combo-time-period.png) |
   | Ytterligare mått | Du kan till exempel jämföra [!UICONTROL Revenue] till ett annat mätvärde.<p>![](assets/combo-2metrics.png) |
   |  -funktion | Du kan presentera en funktion som [!UICONTROL Average] i jämförelsen. Se en lista över funktioner som stöds nedan.<p>![](assets/combo-functions.png) |

   {style=&quot;table-layout:auto&quot;}

1. Klicka på **[!UICONTROL Build]**.

   Utdata ser ut ungefär så här:

   ![](assets/combo-output.png)

   Den aktuella perioden visas i stapeldiagrammet och jämförelseperioden representeras av linjediagrammet. Punkter i linjediagrammet kallas för&quot;streck&quot;.

## Funktioner som stöds

Om du väljer **[!UICONTROL Function]** som [!UICONTROL Line comparison type], returneras en funktion för det mätvärde du har valt.

|  -funktion | Definition |
| --- | --- |
| **[!UICONTROL Cumulative average]** | Returnerar medelvärdet för de sista N raderna. |
| **[!UICONTROL Sum]** | Lägger till alla numeriska värden för ett mått i en kolumn (över elementen i en dimension) |
| **[!UICONTROL Exponent]** | Returnerar *e* upphöjt till ett visst tal. |
| **[!UICONTROL Mean]** | Returnerar det aritmetiska medelvärdet, eller medelvärdet, för ett mått. |
| **[!UICONTROL Quartile]** | Returnerar kvartilen med värden för ett mått. Du kan till exempel använda kvartilarna för att hitta de 25 % av de bästa produkterna som genererar störst intäkter. |

{style=&quot;table-layout:auto&quot;}

Här är ett exempel på det ackumulerade genomsnittet för intäktsmåttet:

![](assets/combo-cumul-avg.png)

Här följer ett exempel på ett kombinationsdiagram med funktioner för både Cumulativt medelvärde och Medel:

![](assets/combo-two-functions.png)

## Inställningar för kombinationsdiagram

Klicka på kugghjulsikonen längst upp till höger i ett kombinationsdiagram om du vill ändra dess inställningar.

![](assets/combo-settings.png)

| Inställning | Definition |
| --- | --- |
| **[!UICONTROL General]** |  |
| **[!UICONTROL Percentages]** | Visar värden i procent. |
| **[!UICONTROL Legend visible]** | Gör att du kan dölja den detaljerade förklaringstexten för visualiseringen av kombinationsdiagram. |
| **[!UICONTROL Granularity]** | För trendvisualiseringar kan du ändra tidshalten (dag, vecka, månad osv.) från den här listrutan. |
| **[!UICONTROL Overlays]** | Visa eller dölj strecken på linjer. |
| **[!UICONTROL Axis]** |  |
| **[!UICONTROL Display dual axis]** | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för det andra måttet). Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
| **[!UICONTROL Normalization]** | Tvingar måtten att ha samma proportioner. Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
| **[!UICONTROL Show x-axis]** | Visa x-axeln eller dölj den. |
| **[!UICONTROL Show y-axis]** | Visa y-axeln eller dölj den. |
| **[!UICONTROL Anchor y-axis at zero]** | Om alla värden som är ritade i diagrammet ligger betydligt över noll, kommer diagrammets standardvärde att göra den nedre delen av y-axeln ICKE-ZERO. Om du markerar den här rutan kommer y-axeln att tvingas till noll (och diagrammet ritas om). |

{style=&quot;table-layout:auto&quot;}


