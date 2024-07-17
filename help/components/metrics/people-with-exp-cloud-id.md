---
title: Personer med Experience Cloud ID
description: Antalet personer i Cross-Device Analytics som har ett Experience Cloud-ID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 0%

---

# Personer med Experience Cloud ID

Människor med Experience Cloud-ID är ett [helhetsvärde för analys](../cda/overview.md) som visar antalet [Personer](people.md) som identifieras av Adobe med hjälp av [Experience Cloud ID-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Hur det här måttet beräknas

Med tanke på varje [person](people.md) (identifierad eller oidentifierad) ökar detta [mått](overview.md) om träffen innehåller frågesträngen `mid` (baserad på cookien [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)).

Du kan skapa det beräknade måttet `[People with ECID] ÷ [People]` om du vill få antalet besökare på din webbplats med ID-tjänsten.

Se motsvarande icke-CDA-mått [Besökare med Experience Cloud ID](visitors-with-ecid.md) för mer information om Experience Cloud ID:ts betydelse och felsökning av konfigurationen.
