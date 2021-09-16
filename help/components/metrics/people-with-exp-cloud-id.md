---
title: Personer med Experience Cloud ID
description: Antalet personer i Cross-Device Analytics som har ett Experience Cloud-ID.
source-git-commit: eaf0c3b751a5fbdc70ad6bef501dbf9e8400339c
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---

# Personer med Experience Cloud ID

&#39;Personer med Experience Cloud-ID&#39; är en [enhetsanalys](../cda/overview.md)-mätning som visar antalet [personer](people.md) som identifieras av Adobe med [Experience Cloud ID-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Hur det här måttet beräknas

Med tanke på var och en av [People](people.md) (identifierad eller oidentifierad) ökar detta mätvärde om träffen innehåller frågesträngen `mid` (baserad på cookien [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)).

Du kan skapa det beräknade måttet `[People with ECID] ÷ [People]` för att få antalet besökare på din webbplats med ID-tjänsten.

Se motsvarande icke-CDA-mått [Besökare med Experience Cloud ID](visitors-with-ecid.md) för mer information om Experience Cloud ID:ts betydelse och felsökning av installationen.
