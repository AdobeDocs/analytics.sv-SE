---
title: Hash-kollisioner
description: Beskriver vad en hash-kollision är och hur den kan visa sig.
feature: Validation
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: 06f61fa7b39faacea89149650e378c8b8863ac4f
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# Hash-kollisioner

Dimensioner i Adobe Analytics samlar in strängvärden. Ibland är de här strängarna hundratals tecken långa, medan andra gånger de är korta. För att förbättra prestandan används dessa strängvärden inte direkt i bearbetningen. I stället beräknas en hash för varje värde så att alla värden får en enhetlig storlek. Alla rapporter körs på dessa hash-kodade värden, vilket drastiskt ökar deras prestanda.

För de flesta fält konverteras strängen först till gemener. Vid konvertering med gemener minskas antalet unika värden. Värden hashas månadsvis - för ett givet värde används det första värdet som visas varje månad. Från månad till månad finns det en liten möjlighet att två unika variabelvärden hash-kodas till samma värde. Detta koncept kallas *hash-kollision*.

Hash-kollisioner kan visas i rapporter på följande sätt:

* Om du visar en rapport över tiden och ser en oväntad topp, är det möjligt att flera unika värden för den variabeln använder samma hash.
* Om du använder ett segment och ser ett oväntat värde är det möjligt att det oväntade dimensionsobjektet använder samma hash som en annan dimensionsobjekt som matchade ditt segment.

## Oddsen för en hash-kollision

Adobe Analytics använder 32-bitars hash för de flesta dimensioner, vilket betyder att det finns 2<sup>32</sup> möjliga hash-kombinationer (cirka 4,3 miljarder). En ny hash-tabell för varje dimension skapas varje månad. De ungefärliga oddsen för en hash-kollision baserad på antalet unika värden är följande. Oddsen baseras på en enda dimension för en månad.

| Unika värden | Oddning |
| --- | --- |
| 1 000 | 0,01 % |
| 10 000 | 1 % |
| 50 000 | 26 % |
| 100 000 | 71 % |

{style="table-layout:auto"}

Liknar [födelsedagsparadox](https://en.wikipedia.org/wiki/Birthday_problem)Sannolikheten för hash-kollisioner ökar drastiskt när antalet unika värden ökar. Vid 1 miljon unika värden är det troligt att det förekommer minst 100 hash-kollisioner för den dimensionen.

## Minska hashkollisioner

De flesta hash-kollisioner inträffar med två mindre vanliga värden, som inte har någon meningsfull inverkan på rapporter. Även om en hash kolliderar med ett vanligt och ovanligt värde är resultatet försumbart. I sällsynta fall där två populära värden upplever en hash-kollision är det dock möjligt att se effekten tydligt. Adobe rekommenderar följande för att minska effekten i rapporter:

* **Ändra datumintervall**: Hash-tabeller ändras varje månad. Om du ändrar datumintervallet så att det sträcker sig över en annan månad kan du ge varje värde olika hash-värden som inte kolliderar.
* **Minska antalet unika värden**: Du kan justera implementeringen eller användningen [Bearbetar regler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) för att minska antalet unika värden som en dimension samlar in. Om dimensionen till exempel samlar in en URL-adress kan du ta bort frågesträngar eller protokoll.

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
