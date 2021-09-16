---
title: Personer
description: Antalet unika individer, vanligtvis med flera enheter.
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 7f9442d6be7930b9e040539dc683c62953aba342
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 1%

---

# Personer

Det finns två versioner av personmåttet.

För medlemmar i [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html) som inte använder [Cross-Device Analytics](../cda/overview.md) är personmåttet ett statistiskt härlett antal personer som finns representerade i rapporten. Det är antalet besökar-ID:n som identifieras av Device Co-op plus antalet enheter som inte identifieras av Co-op.

I en [enhetsanalys](../cda/overview.md) virtuell rapportsvit är personmåttet inte en statistisk härledning. I stället är det summan av individer som identifieras i rapporten plus antalet enheter som inte identifieras som tillhörande en person.

Om en besökare identifieras mitt på besöket kan besökaren räknas som 2 personer tills [Replay](/help/components/cda/replay.md) körs (1 oidentifierad person och 1 identifierad person). Mer information finns i [Unika enheter](unique-devices.md).
