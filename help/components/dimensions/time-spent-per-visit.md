---
title: Tid per besök (dimensioner)
description: Den totala tiden för besöket.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# Tid per besök

*Den här hjälpsidan beskriver hur&quot;Tid per besök&quot; fungerar som respektive mått. Se [Tid per besök](../metrics/time-spent-per-visit.md) för mer information.*

Dimensionerna &#39;Tid per besök&#39; visar hur mycket tid en besökare tillbringat på hela besöket. Följande steg används för att mäta beräkningen:

1. Titta på tidsstämpeln för besökets första träff.
2. Jämför träffen med tidsstämpeln för besökets senaste träff.
3. Den tid som förflutit mellan dessa två träffar bidrar till den tid som tillbringas.

Dessa dimensioner är värdefulla när ni vill förstå hur länge besökarna interagerar med er webbplats i allmänhet.

>[!TIP]
>
>Tidsåtgången kräver minst två träffar vid ett besök för att mäta tiden. Besök som består av en enda träff visas inte i den här dimensionen.

Denna dimension är besöksbaserad, vilket innebär att värdet gäller för alla träffar inom besöket och inte ändras. Jämför den här dimensionen med [Tid som använts på sidan](time-spent-on-page.md), vilket är en träffbaserad dimension.

Den här dimensionen är relaterad till [Genomsnittlig tid på webbplatsen](../metrics/average-time-on-site.md) och [Tid per besök](../metrics/time-spent-per-visit.md) mätvärden.

## Fyll den här dimensionen med data

De här dimensionerna passar alla implementeringar. Om en rapportsvit innehåller data fungerar de här dimensionerna.

## Dimensioner

Det finns flera dimensioner av den tid som tillbringas per besök:

* **Tid per besök - paketerad**: Tidsmängden är spärrad. Objekten i Dimensionen kan variera från `"Less than 1 minute"` till `"More than 15 hours"`. Besök varar vanligtvis inte längre än 12 timmar. besöken kan dock överskrida 12 timmar om tidsstämplade träffar eller datakällor används.
* **Tidsåtgång per besök - granulerad**: Varje antal sekunder är ett unikt dimensionsobjekt. Den här dimensionen är inte tillgänglig i Rapporter och analyser eller Data warehouse.

Se [Tidsåtgång - översikt](../metrics/time-spent.md) om du vill ha mer allmän information om hur länge du har tillbringat.
