---
title: Läs in igen
description: Antalet gånger som sidan lästes in på nytt.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
source-git-commit: c9b7c32adfb44a04ab792d12ca049106b3009710
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 0%

---

# Läs in igen

[Måttet ](overview.md) för att läsa in igen visar hur många gånger ett dimensionsobjekt fanns under en omläsning. En besökare som uppdaterar sin webbläsare är det vanligaste sättet att utlösa en omladdning.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar där dimensionen [Sida](../dimensions/page.md) innehåller samma värde som föregående träff.

Begreppet omladdning gäller för siddimensionen oavsett vilken dimension du använder vid rapportering. Om du till exempel använder [eVar1](../dimensions/evar.md) som mått och läser in igen, visas antalet gånger som varje eVar-värde fanns under en omladdning (två på varandra följande sidvärden). Det visar inte hur många gånger det finns två på varandra följande eVar1-värden.
