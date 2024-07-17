---
title: Enkelsidiga besök (mätvärden)
description: Antalet gånger som sidobjektet inte ändrades vid ett besök.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 5%

---

# Besök enstaka sidor

*Den här hjälpsidan beskriver hur enkelsidiga besök fungerar som ett mått. Mer information finns i dimensionen [Enkelsidiga besök](../dimensions/single-page-visits.md).*

[!UICONTROL Single page visits] [Mått](overview.md) visar antalet besök där dimensionsobjektet [Sida](../dimensions/page.md) endast innehöll ett unikt värde för hela besöket. Det här måttet är användbart när det gäller dimensioner där du vill se korta besök, men som inte har en lika strikt regel som [[!UICONTROL Bounces]](bounces.md).

## Hur det här måttet beräknas

Det här måttet räknar antalet besök där dimensionsobjektet [!UICONTROL Page] endast innehöll ett unikt värde för hela besöket. Om en besökare läser in sidan igen eller utlöser ett länkspårningsanrop räknas det ändå som ett enda sidbesök. Så snart siddimensionen ändras till ett andra unikt värde räknas inte längre besöket som ett enda sidbesök.

Se [Enkel åtkomst](single-access.md) för en jämförelse mellan mätvärden.

## Antal upprepande instanser

Den här inställningen anger om upprepade förekomster räknas i rapporter. Mer information finns i [Antal upprepade instanser](/help/components/metrics/count-repeat-instances.md).
