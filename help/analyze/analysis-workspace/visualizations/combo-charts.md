---
description: Gör att du enkelt kan visualisera jämförelsedata i Analysis Workspace, t.ex. skapa jämförelser till förra månaden, förra året och så vidare.
title: Visualisering av kombinationsdiagram
feature: Visualizations
role: User, Admin
exl-id: 08e49857-aa58-4527-bdfd-b1663a75a02b
source-git-commit: c0855c6bed6a9762c0440e1a8e004ee11020808e
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# Kombinationsdiagram {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_combo_button"
>title="Kombination"
>abstract="Skapa snabbt en visualisering av kombinationsdiagram utan att först behöva skapa en frihandstabell."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*I den här artikeln beskrivs visualiseringen av kombinationen i **Adobe Analytics**.<br/>Se [Kombination](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/combo-charts) för **Customer Journey Analytics**-versionen av den här artikeln.*

>[!ENDSHADEBOX]

Visualiseringen av [!UICONTROL Combo chart] gör det enkelt att snabbt skapa en jämförelsevisualisering utan att först behöva skapa en tabell. Du kan enkelt visa trender i dina data i en kombination av rad och rad.

Använd en [!UICONTROL Combo chart] till

* Jämför veckans order med order vid samma tidpunkt förra månaden (och förra året) - allt med bara några klick.

* Analysera och jämför snabbt flera mätvärden (som [!UICONTROL Unique Visitors] och [!UICONTROL Revenue]) mot varandra i samma diagram.

* Analysera ett mätvärde mot en funktion (till exempel [!UICONTROL Cumulative Average]) över en tidshorisont.

Tänk på detta:

* Du kan lägga till flera jämförelser i en enda [!UICONTROL Combo chart].
* Om du lägger till en eller flera jämförelser måste de vara av samma typ, till exempel [!UICONTROL Time comparison].
* Du kan lägga till upp till fem jämförelser.
* Du kan använda upp till tre filter (segment) för ett mätresultat.
* Beräknade mått stöds inte i kombinationsdiagram.

## Skapa ett kombinationsdiagram

1. Dra [!UICONTROL Combo chart]-visualiseringen från listrutan Visualiseringar i den vänstra listen till en tom panel.

   ![](assets/combo-chart-build.png)

1. Välj en dimension för X-axeln och ett mått för Y-axeln i listrutan.

1. Välj den typ av [!UICONTROL Line comparison] som du vill använda.

   | Jämförelsetyp | Definition |
   | --- | --- |
   | **[!UICONTROL Time comparison]** | Den vanligaste typen av jämförelse - till exempel en jämförelse mellan den här tidsperioden och för 4 veckor sedan. Om du har valt [!UICONTROL Time comparison] kan du göra ett andra val för vilken tidsperiod du vill jämföra.<p>![](assets/combo-time-period.png) |
   | **[!UICONTROL Function]** | Du kan introducera en funktion som [!UICONTROL Average] i jämförelsen. Se en lista över funktioner som stöds nedan.<p>![](assets/combo-functions.png) |
   | **[!UICONTROL Secondary metric]** | Du kan till exempel jämföra [!UICONTROL Revenue] med ett annat mått.<p>![](assets/combo-2metrics.png) |

   {style="table-layout:auto"}

1. Klicka på **[!UICONTROL Build]**.

   Utdata ser ut ungefär så här:

   ![](assets/combo-output.png)

   Den aktuella perioden visas i stapeldiagrammet och jämförelseperioden representeras av linjediagrammet. Punkter i linjediagrammet kallas för&quot;streck&quot;.

## Funktioner som stöds

Om du väljer **[!UICONTROL Function]** som [!UICONTROL Line comparison type] returneras en funktion för måttet som du har valt.

| Funktion | Definition |
| --- | --- |
| **[!UICONTROL Column Sum]** | Lägger till alla numeriska värden för ett mått i en kolumn (över elementen i en dimension) |
| **[!UICONTROL Cumulative Average]** | Returnerar medelvärdet för de sista N raderna. |
| **[!UICONTROL Median]** | Returnerar medianvärdet för ett mått i en kolumn. Medianvärdet är talet i mitten av en uppsättning tal, det vill säga hälften av talen har värden som är större än eller lika med medianvärdet och hälften är mindre än eller lika med medianvärdet. |
| **[!UICONTROL Cumulative]** | Den kumulativa summan av N-rader. |
| **[!UICONTROL Column Maximum]** | Returnerar det största värdet i en uppsättning dimensionselement för en måttkolumn. |
| **[!UICONTROL Mean]** | Returnerar det aritmetiska medelvärdet, eller medelvärdet, för ett mått. |
| **[!UICONTROL Column Minimum]** | Returnerar det minsta värdet i en uppsättning dimensionselement för en måttkolumn. |

{style="table-layout:auto"}

Här är ett exempel på det ackumulerade genomsnittet för intäktsmåttet:

![](assets/combo-cumul-avg.png)

Här följer ett exempel på ett kombinationsdiagram med funktioner för både Cumulativt medelvärde och Medel:

![](assets/combo-two-functions.png)

## Inställningar för kombinationsdiagram

Klicka på kugghjulsikonen längst upp till höger i ett kombinationsdiagram om du vill ändra dess inställningar.

![](assets/combo-settings.png)

| Inställning | Definition |
| --- | --- |
| **[!UICONTROL Visualization type]** | Växla till en annan visualiseringstyp. |
| **[!UICONTROL Granularity]** | För trendvisualiseringar kan du ändra tidgranulariteten (dag, vecka, månad osv.) i den här listrutan. |
| **[!UICONTROL General]** |  |
| **[!UICONTROL Percentages]** | Visar värden i procent. |
| **[!UICONTROL Legend visible]** | Gör att du kan dölja den detaljerade förklaringstexten för visualiseringen av kombinationsdiagram. |
| **[!UICONTROL Limit max items]** | Minskar antalet objekt på X-axeln. Om du har en stor datauppsättning kan du bara visa de första 10 objekten (eller vilket värde du än väljer). |
| **[!UICONTROL Overlays]** | Visa eller dölj strecken på linjer. |
| **[!UICONTROL Axis]** | |
| **[!UICONTROL Display dual axis]** | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för det andra måttet). Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. Färgen på den dubbla axeln matchar färgen på tabellen, såvida det inte finns flera jämförelser. I så fall är färgen för alla jämförelser grå. |
| **[!UICONTROL Normalization]** | Tvingar måtten att ha samma proportioner. Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
| **[!UICONTROL Show x-axis]** | Visa x-axeln eller dölj den. |
| **[!UICONTROL Show y-axis]** | Visa y-axeln eller dölj den. |
| **[!UICONTROL Anchor y-axis at zero]** | Om alla värden som är ritade i diagrammet ligger betydligt över noll, kommer diagrammets standardvärde att göra den nedre delen av y-axeln ICKE-ZERO. Om du markerar den här rutan kommer y-axeln att tvingas till noll (och diagrammet ritas om). |

{style="table-layout:auto"}
