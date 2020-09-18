---
title: Vanliga frågor om data warehouse
description: Frågor och svar om Data warehouse.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 6%

---


# Vanliga frågor om data warehouse

Frågor och svar om Data warehouse.

## När jag använder listrutan för granularitet när jag skapar en begäran, vilket format kan jag förvänta mig att datumen ska vara i?

När du använder granularitet i en Data warehouse-begäran läggs kolumnen Datum till i rapporten. Beroende på den valda granulariteten ändras datumformatet.

| Kornighet | Format | Exempel |
| --- | --- | --- |
| Varje timme | `mmmm d, yyyy` Timme `H` | 1 januari, 20XX, timme 0 |
| Dagligen | `mmmm d, yyyy` | 1 januari 20XX |
| Veckovis | Vecka `w, yyyy` | Vecka 1, 20XX |
| Månadsvis | `mmmm yyyy` | 20XX januari |
| Kvartalsvis | `q` Kvartal `yyyy` | 1:a kvartalet 20XX |
| Årlig | `yyyy` | 20XX |

## Hur fungerar segment som dimensioner i Data warehouse?

När du använder ett segment som en dimension i Data warehouse returneras en kolumn som innehåller `"0"` eller `"1"`:

* **`"0"`**: Dimensionsobjektet uppfyllde inte segmentets villkor.
* **`"1"`**: Dimensionsobjektet uppfyllde segmentets villkor.
