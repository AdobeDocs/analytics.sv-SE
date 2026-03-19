---
title: Enkelsidiga besök (mätvärden)
description: Antalet gånger som sidobjektet inte ändrades vid ett besök.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Besök enstaka sidor

*Den här hjälpsidan beskriver hur enkelsidiga besök fungerar som ett mått. Mer information finns i dimensionen [Enkelsidiga besök](../dimensions/single-page-visits.md).*

**[!UICONTROL Single page visits]** [Mått](overview.md) visar antalet besök där dimensionsobjektet [Sida](../dimensions/page.md) bara innehöll ett enda värde för hela besöket. Det här måttet är användbart när det gäller dimensioner där du vill se korta besök, men som inte har en lika strikt regel som [[!UICONTROL Bounces]](bounces.md).

## Hur det här måttet beräknas

Definitionen av det här måttet beror på projektinställningen för [[!UICONTROL Count repeat instances]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings):

* **[!UICONTROL Count repeat instances]enabled**: Räknar antalet besök där dimensionen [!UICONTROL Page] innehöll ett enda värde för besöket. Om en besökare läser in sidan igen kan den inte tolkas som ett enda sidbesök.
* **[!UICONTROL Count repeat instances]disabled**: Räknar antalet besök där dimensionen [!UICONTROL Page] innehöll ett unikt värde för hela besöket.

Oavsett projektinställningen [!UICONTROL Count repeat instances] följer det här måttet följande regler:

* Ett besök kvalificerar sig fortfarande som ett enda sidbesök om en besökare utlöser anrop för länkspårning (dimensionen [!UICONTROL Page] tas bort från alla anrop för länkspårning).
* Så snart dimensionen [!UICONTROL Page] ändras till ett andra unikt värde räknas inte längre besöket som ett enda sidbesök.

Se [Enkel åtkomst](single-access.md) för en jämförelse mellan mätvärden.
