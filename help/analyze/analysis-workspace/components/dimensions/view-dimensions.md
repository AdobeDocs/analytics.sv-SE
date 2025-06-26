---
description: Visa de översta värdena för en dimension innan du använder den i ett projekt.
title: Förhandsvisa dimensioner
feature: Dimensions
role: User, Admin
exl-id: 897edc76-6744-4d8c-ab0e-20672838f7b3
source-git-commit: a629b2be66d9458bf10872a95aaec739aed9d791
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 0%

---

# Förhandsgranska dimensioner i Analysis Workspace

Du kan använda [komponentinformationen](/help/analyze/analysis-workspace/components/use-components-in-workspace.md#component-info) för en komponent om du vill visa de översta objekten för en dimension.

![Komponentinformation](assets/component-info.png)

<!--
Now, by default, we show dynamic values instead of static ones, with the option to turn them into static values. Other things to note:

* As your data updates, the dynamic dimension columns will update to show the current 5/15 dimension items.
* A dynamic dimension column that is copied or moved will become static.
* When hovering a static dimension column you will see a lock icon, indicating that the dimension is static.

![Dimension column popup highlighting the lock icon.](assets/dimension_static.png)

-->


## Visa dimensionsobjekt

När du väljer ![SparrronRight](/help/assets/icons/ChevronRight.svg) för en dimension på komponentpanelen visas en lista med dimensionsobjekten. I listan över dimensionsobjekt visas vanligtvis de översta artiklarna de senaste 30 dagarna. När fler objekt är tillgängliga, utanför det valda datumintervallet för panelen, markerar du länken för att visa fler objekt. Exempel: **[!UICONTROL Show items from last month]**.

![Visa dimensionsobjekt](assets/dimension-items.png)


<!--
# Preview dimensions

Hover over the information (i) icon next to a dimension. This shows the top 5 values for non-time dimensions (and 15 for time dimensions). We used to keep those values static (i.e., the 5 values picked never changed).

![](assets/dimension-preview.png)

Now, by default, we show dynamic values instead of static ones, with the option to turn them into static values. Other things to note:

* As your data updates, the dynamic dimension columns will update to show the current 5/15 dimension items.
* A dynamic dimension column that is copied or moved will become static.
* When hovering a static dimension column you will see a lock icon, indicating that the dimension is static.

![](assets/dimension_static.png)

## Show dimension items

When you hover over a dimension and click the grey right-arrow next to it, a list of its dimension items appears. Any list of dimension items usually shows the top items for the last 30 days.

If you scroll down to the bottom of the list, you see **[!UICONTROL Show Top Items From Last 18 Months]**. Click this option to see top dimension items from the last 547 days.

-->
