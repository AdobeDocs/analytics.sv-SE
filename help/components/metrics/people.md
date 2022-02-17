---
title: Personer
description: Antalet unika individer, vanligtvis med flera enheter.
feature: Metrics
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 1%

---

# Personer

Det finns två versioner av personmåttet.

För medlemmar i [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html) som inte används [Enhetsövergripande analys](../cda/overview.md), är personmåttet ett statistiskt härlett antal personer som finns representerade i rapporten. Det är antalet besökar-ID:n som identifieras av Device Co-op plus antalet enheter som inte identifieras av Co-op.

Inom en [Enhetsövergripande analys](../cda/overview.md) den virtuella rapportsviten, personmåttet är inte en statistisk härledning. I stället är det summan av individer som identifieras i rapporten plus antalet enheter som inte identifieras som tillhörande en person.

Om en besökare identifieras mitt på besöket kan besökaren räknas som 2 personer (1 oidentifierad person och 1 identifierad person). [Spela upp](/help/components/cda/replay.md) reducerar denna dubbelräkning beroende på rapporteringsfönstret, repriser och antalet lyckade försök. Se [Unika enheter](unique-devices.md) för mer information.
