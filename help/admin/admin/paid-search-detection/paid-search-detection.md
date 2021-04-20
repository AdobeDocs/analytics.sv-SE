---
description: Betalsökningsidentifiering skiljer betald från naturlig sökning i rapporten Sökmotorer och Söknyckelord. Du kan ange sökmotorer där du använder betalda annonser och ange en teckensträng som finns i URL:en för ett besök från en betald annons.
title: Betalsökningsidentifiering
feature: Admin Tools
uuid: 41aadf17-7b8b-49ce-84ca-dc3293660205
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 1%

---

# Betalsökningsidentifiering

Betalsökningsidentifiering skiljer betald från naturlig sökning i rapporten Sökmotorer och Söknyckelord. Du kan ange sökmotorer där du använder betalda annonser och ange en teckensträng som finns i URL:en för ett besök från en betald annons.

## Betalsökningsidentifiering - beskrivningar {#section_0C2CFA0AF77B47098BE37CB024665D0D}

I följande tabell beskrivs de fält och alternativ som du använder för att [konfigurera identifiering av betald sökning](/help/admin/admin/paid-search-detection/t-paid-search-detection.md).

| Element | Beskrivning |
|--- |--- |
| Sökmotor | Välj en sökmotor i listrutan. Du anger motorn om du använder olika frågesträngsparametrar för olika sökmotorer. Vanligtvis är värdet Any tillräckligt. |
| Frågesträng | Anger en skiftlägeskänslig regeluppsättning som innehåller eller inte innehåller ett visst värde. Det här värdet ska vara frågesträngsparametern, utan&quot;?&quot;. <br>**Obs**: Betalsökningsidentifiering är skiftlägeskänsligt. En regel som anger PID som frågesträngsparameter visar till exempel inte pid i rapporter. Om din organisation använder blandade fall placerar du de exakta värdena som separata regler, så att alla önskade frågesträngsparametrar kan fångas upp.</br> |
