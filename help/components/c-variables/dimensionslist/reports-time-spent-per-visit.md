---
description: 'null'
title: Tid per besök
topic: Reports
uuid: 76441e36-b7fe-4cf3-8d72-c51d558afa13
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tid per besök

Adobe Analytics erbjuder flera sätt att avgöra hur lång tid som spenderas i Analytics-rapporter. I de flesta fall beräknas tidsåtgången med följande steg:

1. Titta på tidsstämpeln för den första träffen för ett visst besök.
2. Jämför träffen med tidsstämpeln för besökets senaste träff.
3. Den tid som förflyter mellan dessa två träffar avgör hur lång tid som tillbringas för besöket.

Tänk på följande när du visar tidsåtgången för dimensionsdata:

* Både sidvyer och träfftyper för länkspårning beaktas vid beräkning av tidsåtgången för data.
* Tid som använts mäts inte under besökets senaste träff, eftersom det inte finns någon efterföljande bildbegäran för att mäta förfluten tid.
* Satsningar kan inte mäta hur lång tid som tillbringats eftersom besöket består av en enda träff.

Den tid som tillbringas per besök mäter den sammanlagda tiden för ett besök. Det finns olika dimensioner mellan **granulat** och **bucketat**.

* **Detaljerad:** Varje dimensionsvärde består av olika antal sekunder som ett besök består av.
* **Bucketed:** Varje dimensionsvärde är en fördefinierad bucket:
   * Mindre än 1 minut
   * 1-5 minuter
   * 5-10 minuter
   * 30-60 minuter
   * 1-2 timmar
   * 2-5 timmar
   * 5-10 timmar
   * 10-15 timmar
   * 15+ timmar

> [!NOTE] [Besök](../c-metrics/metrics-visit.md) avslutas vanligtvis efter 12 timmars aktivitet. Besöken kan dock överskrida 12 timmar om tidsstämplade träffar eller datakällor används.

Denna dimension är besöksbaserad. Jämför den här dimensionen med den [tid som spenderas på sidan](reports-time-spent-on-page.md), som är en träffbaserad dimension.
