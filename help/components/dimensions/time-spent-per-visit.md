---
title: Tid per besök (dimensioner)
description: Den totala tiden för besöket.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Tid per besök

*Den här hjälpsidan beskriver hur&quot;Tid per besök&quot; fungerar som respektive [mått](overview.md). Mer information finns i [Tid per besök](../metrics/time-spent-per-visit.md).*

Dimensionerna &#39;Tid per besök&#39; visar hur mycket tid en besökare tillbringat på hela besöket. Följande steg används för att mäta beräkningen:

1. Titta på tidsstämpeln för besökets första träff.
2. Jämför träffen med tidsstämpeln för besökets senaste träff.
3. Den tid som förflutit mellan dessa två träffar bidrar till den tid som tillbringas.

Dessa dimensioner är värdefulla när ni vill förstå hur länge besökarna interagerar med er webbplats i allmänhet.

>[!TIP]
>
>Tidsåtgången kräver minst två träffar vid ett besök för att mäta tiden. Besök som består av en enda träff visas inte i den här dimensionen.

Denna dimension är besöksbaserad, vilket innebär att värdet gäller för alla träffar inom besöket och inte ändras. Jämför den här dimensionen med [Den tid som har ägnats åt sidan &#x200B;](time-spent-on-page.md), som är en träffbaserad dimension.

Den här dimensionen är relaterad till [Genomsnittlig tid på webbplatsen &#x200B;](../metrics/average-time-on-site.md) och [Tid per besök](../metrics/time-spent-per-visit.md).

## Fyll den här dimensionen med data

De här dimensionerna fungerar som de ska för alla implementeringar. Om en rapportsvit innehåller data fungerar de här dimensionerna.

## Dimensioner

Det finns flera dimensioner av den tid som tillbringas per besök:

* **Tid per besök - bucketed**: Den tid som har använts är bucketad. Dimensionens objekt varierar från `"Less than 1 minute"` till `"More than 15 hours"`. Besök varar vanligtvis inte längre än 12 timmar, men besöken kan överstiga 12 timmar om tidsstämplade träffar eller datakällor används.
* **Tid per besök - granulat**: Varje antal sekunder är ett unikt dimensionsobjekt. Den här dimensionen är inte tillgänglig i Data Warehouse.

Mer allmän information om hur lång tid du tillbringar finns i [Tidsåtgång - översikt](../metrics/time-spent.md).
