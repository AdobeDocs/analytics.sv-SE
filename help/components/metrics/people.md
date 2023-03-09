---
title: Personer
description: Antalet unika individer, vanligtvis med flera enheter.
feature: Metrics
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: db7d8b4e8426a97af4c7e566c41b115dbb5b6174
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 1%

---

# Personer

>[!IMPORTANT]
>
>Personmåttet som relaterar till Device Co-op kommer att bli inaktuellt den 8 mars 2023. Det CDA-relaterade personmåttet som beskrivs nedan påverkas inte av den här borttagningen.

Personmåttet är specifikt för [Enhetsövergripande analys](../cda/overview.md) virtuella rapportsviter. Det representerar summan av de personer som identifieras i rapporten plus antalet enheter som inte identifieras som tillhörande en person.

Om en besökare identifieras mitt på besöket kan besökaren räknas som 2 personer (1 oidentifierad person och 1 identifierad person). [Spela upp](/help/components/cda/replay.md) reducerar denna dubbelräkning beroende på rapporteringsfönstret, repriser och antalet lyckade försök. Se [Unika enheter](unique-devices.md) för mer information.
