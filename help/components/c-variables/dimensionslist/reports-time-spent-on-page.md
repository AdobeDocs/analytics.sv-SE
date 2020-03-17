---
description: Visar hur många besökare som tillbringar på sidan
title: Tid som använts på sidan
topic: Reports
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tid som använts på sidan

Adobe Analytics erbjuder flera sätt att avgöra hur lång tid som spenderas i Analytics-rapporter. I de flesta fall beräknas tidsåtgången med följande steg:

1. Titta på tidsstämpeln och dimensionsvärdet för en viss träff.
2. Jämför träffen med tidsstämpeln för nästa träff i besöket.
3. Den tid som förflutit mellan dessa två träffar bidrar till den tid som har ägnats åt sidan.

Tänk på följande när du visar tidsåtgången för dimensionsdata:

* Tidsåtgången tar hänsyn till allokering och förfallodatum.
* Både sidvyer och träfftyper för länkspårning beaktas vid beräkning av tidsåtgången för data.
* Tid som använts mäts inte under besökets senaste träff, eftersom det inte finns någon efterföljande bildbegäran för att mäta förfluten tid.
* Satsningar kan inte mäta hur lång tid som tillbringats eftersom besöket består av en enda träff.

Den tid som går åt till sidan mäter hur lång tid det tar mellan träffarna vid ett besök. Det finns olika dimensioner mellan **granulat** och **bucketat**.

* **Detaljerad:** Varje dimensionsvärde är ett annat antal sekunder mellan två träffar.
* **Bucketed:** Varje dimensionsvärde är en fördefinierad bucket:
   * Mindre än 15 sekunder
   * 15 till 29 sekunder
   * 1 till 3 minuter
   * 3 till 5 minuter
   * 5 till 10 minuter
   * 10 till 15 minuter
   * 15 till 20 minuter
   * 20 till 30 minuter
   * Mer än 30 minuter

Denna dimension är träffbaserad, som kan ge mer meningsfulla data om den används som en nedbrytning. Jämför den här dimensionen med [tidsåtgången per besök](reports-time-spent-per-visit.md), vilket är en besöksbaserad dimension.

![Tid](/help/components/c-variables/c-metrics/assets/time-spent1.png)
