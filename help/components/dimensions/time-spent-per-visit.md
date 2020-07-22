---
title: Tid per besök
description: Den totala tiden för besöket.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---


# Tid per besök

*Den här hjälpsidan beskriver hur&quot;Tid per besök&quot; fungerar som respektive mått. Mer information finns i mätvärdena för[Tid per besök](../metrics/time-spent-per-visit.md).*

Dimensionerna &#39;Tid per besök&#39; visar hur mycket tid en besökare tillbringat på hela besöket. Följande steg används för att mäta beräkningen:

1. Titta på tidsstämpeln för besökets första träff.
2. Jämför träffen med tidsstämpeln för besökets senaste träff.
3. Den tid som förflutit mellan dessa två träffar bidrar till den tid som tillbringas.

Dessa dimensioner är värdefulla när ni vill förstå hur länge besökarna interagerar med er webbplats i allmänhet.

>[!TIP]
>
>Tidsåtgången kräver minst två träffar vid ett besök för att mäta tiden. Besök som består av en enda träff visas inte i den här dimensionen.

Denna dimension är besöksbaserad, vilket innebär att värdet gäller för alla träffar inom besöket och inte ändras. Jämför den här dimensionen med den [tid som spenderas på sidan](time-spent-on-page.md), som är en träffbaserad dimension.

Den här dimensionen är relaterad till [genomsnittlig tid på webbplatsen](../metrics/average-time-on-site.md) och [tid per besök](../metrics/time-spent-per-visit.md) .

## Fyll den här dimensionen med data

De här dimensionerna passar alla implementeringar. Om en rapportsvit innehåller data fungerar de här dimensionerna.

## Dimensionsobjekt

Det finns flera dimensioner av den tid som tillbringas per besök:

* **Tid per besök - inbuktad**: Tidsmängden är spärrad. Dimensionsobjekten varierar från `"Less than 1 minute"` till `"More than 15 hours"`. Besök varar vanligtvis inte längre än 12 timmar. besöken kan dock överskrida 12 timmar om tidsstämplade träffar eller datakällor används.
* **Tidsåtgång per besök - i korthet**: Varje antal sekunder är ett unikt dimensionsobjekt. Den här dimensionen är inte tillgänglig i Rapporter &amp; Analytics eller Data warehouse.

Mer allmän information om hur lång tid du tillbringar finns i [Tidsåtgång - översikt](../metrics/time-spent.md) .
