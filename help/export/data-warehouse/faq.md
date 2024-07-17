---
title: Vanliga frågor om Data Warehouse
description: Frågor och svar om Data Warehouse.
feature: Data Warehouse
exl-id: 51c3ba17-a8b2-4030-9521-355ebbbfcd0d
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%

---

# Vanliga frågor om Data Warehouse

Frågor och svar om Data Warehouse.

## När jag använder listrutan för granularitet när jag skapar en begäran, vilket format kan jag förvänta mig att datumen ska vara i?

När du använder granularitet i en Data Warehouse-förfrågan läggs kolumnen Datum till i rapporten. Beroende på den valda granulariteten ändras datumformatet.

| Kornighet | Format | Exempel |
| --- | --- | --- |
| Varje timme | `mmmm d, yyyy` timme `H` | 1 januari, 20XX, timme 0 |
| Dagligen | `mmmm d, yyyy` | 1 januari 20XX |
| Veckovis | Vecka `w, yyyy` | Vecka 1, 20XX |
| Månadsvis | `mmmm yyyy` | 20XX januari |
| Kvartalsvis | `q` kvartal `yyyy` | 1:a kvartalet 20XX |
| Årlig | `yyyy` | 20XX |

## Hur fungerar segment som dimensioner i Data Warehouse?

När du använder ett segment som en dimension i Datan Warehouse returnerar rapporten en kolumn som innehåller `"0"` eller `"1"`:

* **`"0"`**: Dimensionsobjektet uppfyllde inte segmentets villkor.
* **`"1"`**: Dimensionsobjektet uppfyller segmentets villkor.
