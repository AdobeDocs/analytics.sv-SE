---
title: Personer
description: Antalet unika individer, vanligtvis med flera enheter.
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%

---

# Personer

Det finns två versioner av personmåttet.

För medlemmar i [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html) som inte använder [Cross-Device Analytics](../cda/overview.md) är personmåttet ett statistiskt härlett antal personer som finns representerade i rapporten. Det är antalet besökar-ID:n som identifieras av Device Co-op plus antalet enheter som inte identifieras av Co-op.

I en [enhetsanalys](../cda/overview.md) virtuell rapportsvit är personmåttet ett direkt antal unika individer i stället för en statistisk härledning. Definitionen av en person i CDA baseras antingen på Device Co-op, Private Graph eller fältbaserad sammanfogning, beroende på hur CDA är konfigurerat för basrapportsviten. Personer är summan av personer som har identifierats i rapporten plus antalet enheter som inte har identifierats som tillhörande en person.
