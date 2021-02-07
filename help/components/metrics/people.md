---
title: Personer
description: Antalet unika individer, vanligtvis med flera enheter.
translation-type: tm+mt
source-git-commit: 2a32ac1aafbbdfa4d0161666061fc9084af13fae
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 6%

---


# Personer

Det finns två versioner av personmåttet.

För medlemmar i [Device Co-op](https://docs.adobe.com/content/help/sv-SE/device-co-op/using/data/people.html) som inte använder [Cross-Device Analytics](../cda/overview.md) är personmåttet ett statistiskt härlett antal personer som finns representerade i rapporten. Det är antalet besökar-ID:n som identifieras av Device Co-op plus antalet enheter som inte identifieras av Co-op.

I en [enhetsanalys](../cda/overview.md) virtuell rapportsvit är personmåttet ett direkt antal unika individer i stället för en statistisk härledning. Definitionen av en person i CDA baseras antingen på Device Co-op, Private Graph eller fältbaserad sammanfogning, beroende på hur CDA är konfigurerat för basrapportsviten. Personer är summan av personer som har identifierats i rapporten plus antalet enheter som inte har identifierats som tillhörande en person.
