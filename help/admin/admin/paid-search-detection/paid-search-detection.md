---
description: 'Betalsökningsidentifiering skiljer betald från naturlig sökning i rapporten Sökmotorer och Söknyckelord. '
title: Betalsökningsidentifiering
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: 2c0aef13bdb88b0a7aa9f100c72c21f66a14c8dd
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 1%

---

# Betalsökningsidentifiering

[!UICONTROL Paid Search Detection] skiljer betald från naturlig sökning i [!UICONTROL Search Engines] och [!UICONTROL Search Keywords] rapporter. Du kan ange sökmotorer där du använder betalda annonser och ange en teckensträng som finns i URL:en för ett besök från en betald annons.

## Konfigurationsalternativ {#section_0C2CFA0AF77B47098BE37CB024665D0D}

I följande tabell beskrivs fälten och alternativen som du använder för [konfigurera identifiering av betalsökningar](/help/admin/admin/paid-search-detection/t-paid-search-detection.md).

| Alternativ | Beskrivning |
| --- | --- |
| [!UICONTROL Search Engine] | Välj en sökmotor i listrutan. Du anger motorn om du använder olika frågesträngsparametrar för olika sökmotorer. Vanligtvis är värdet `Any` är tillräckligt. |
| [!UICONTROL Query string] | Anger en sträng för en skiftlägeskänslig matchning med någon del av frågesträngsparametern, som är den del av url som kommer efter &quot;?&quot;. <br>**Anteckning**: [!UICONTROL Paid Search Detection] är skiftlägeskänsligt. En regel som till exempel anger &quot;PID&quot; som frågesträngsparameter kommer inte att matcha &quot;pid&quot;. Om din organisation använder blandade fall placerar du de exakta värdena som separata regler, så att alla önskade frågesträngsparametrar kan fångas upp. |
