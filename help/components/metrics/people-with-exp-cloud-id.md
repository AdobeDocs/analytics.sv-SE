---
title: Personer med Experience Cloud ID
description: Antalet personer i Cross-Device Analytics som har ett Experience Cloud-ID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---

# Personer med Experience Cloud ID

&#39;Personer med Experience Cloud-ID&#39; är en [Enhetsövergripande analys](../cda/overview.md) mått som visar antalet [Folk](people.md) som identifieras av Adobe med [Experience Cloud ID-tjänst](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Hur det här måttet beräknas

Överväg varje [Folk](people.md) (identifierad eller oidentifierad) ökar mätvärdet om träffen innehåller `mid` frågesträng (baserad på [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie).

Du kan skapa det beräknade måttet `[People with ECID] ÷ [People]` om du vill få reda på hur många besökare på webbplatsen som använder ID-tjänsten.

Se motsvarande icke-CDA-mått [Besökare med Experience Cloud-ID](visitors-with-ecid.md) om du vill ha mer information om Experience Cloud ID och felsökning av konfigurationen.
