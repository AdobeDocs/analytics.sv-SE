---
title: Besök enstaka sidor
description: Antalet gånger som sidobjektet inte ändrades vid ett besök.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Besök enstaka sidor

*Den här hjälpsidan beskriver hur&quot;Enkelsidiga besök&quot; fungerar som ett mått. Mer information finns i dimensionen[Enkelsidiga besök](../dimensions/single-page-visits.md).*

Mätvärdet för besök på en sida visar antalet besök där [sidobjektet](../dimensions/page.md) endast innehöll ett unikt värde för hela besöket. Det här måttet är användbart i samband med dimensioner där du vill se korta besök, men inte ha lika strikta regler som [studsar](bounces.md).

## Hur det här måttet beräknas

Det här måttet räknar antalet besök där dimensionsobjektet &quot;Sida&quot; endast innehöll ett unikt värde för hela besöket. Om en besökare läser in sidan igen eller utlöser ett länkspårningsanrop räknas det ändå som ett enda sidbesök. Så snart siddimensionen ändras till ett andra unikt värde räknas inte längre besöket som ett enda sidbesök.

Se [Enkel åtkomst](single-access.md) för en jämförelse mellan mätvärden.
