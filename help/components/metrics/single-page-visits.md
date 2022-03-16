---
title: Enkelsidiga besök (statistik)
description: Antalet gånger som sidobjektet inte ändrades vid ett besök.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 5%

---

# Besök enstaka sidor

*Den här hjälpsidan beskriver hur&quot;Enkelsidiga besök&quot; fungerar som ett mått. Se [Besök enstaka sidor](../dimensions/single-page-visits.md) för mer information.*

The [!UICONTROL Single page visits] mätvärdet visar antalet besök där [Sida](../dimensions/page.md) dimensionsobjektet innehöll endast ett unikt värde för hela besöket. Det här måttet är användbart när det gäller dimensioner där du vill se korta besök, men inte ha en så strikt regel som [[!UICONTROL Bounces]](bounces.md) gör det.

## Hur det här måttet beräknas

Det här måttet räknar antalet besök där [!UICONTROL Page] dimensionsobjektet innehöll endast ett unikt värde för hela besöket. Om en besökare läser in sidan igen eller utlöser ett länkspårningsanrop räknas det ändå som ett enda sidbesök. Så snart siddimensionen ändras till ett andra unikt värde räknas inte längre besöket som ett enda sidbesök.

Se [Enkel åtkomst](single-access.md) för en jämförelse mellan mätvärden.

## Antal upprepande instanser

Den här inställningen anger om upprepade förekomster räknas i rapporter. Mer information finns i [Antal upprepande instanser](/help/components/metrics/count-repeat-instances.md).