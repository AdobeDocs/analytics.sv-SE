---
description: 'Betalsökningsidentifiering skiljer betald från naturlig sökning i rapporten Sökmotorer och Söknyckelord. '
title: Betalsökningsidentifiering
feature: Administratörsverktyg
uuid: 41aadf17-7b8b-49ce-84ca-dc3293660205
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: b88f9d373d715b295dc4982a6ee05bd982f5bae7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---

# Betalsökningsidentifiering

[!UICONTROL Paid Search Detection] skiljer betald från naturlig sökning i  [!UICONTROL Search Engines] och  [!UICONTROL Search Keywords] rapporter. Du kan ange sökmotorer där du använder betalda annonser och ange en teckensträng som finns i URL:en för ett besök från en betald annons.

## Konfigurationsalternativ {#section_0C2CFA0AF77B47098BE37CB024665D0D}

I följande tabell beskrivs de fält och alternativ som du använder för att [konfigurera identifiering av betald sökning](/help/admin/admin/paid-search-detection/t-paid-search-detection.md).

| Alternativ | Beskrivning |
| --- | --- |
| [!UICONTROL Search Engine] | Välj en sökmotor i listrutan. Du anger motorn om du använder olika frågesträngsparametrar för olika sökmotorer. Vanligtvis är värdet `Any` tillräckligt. |
| [!UICONTROL Query string] | Anger en sträng för en skiftlägeskänslig matchning med en del av frågesträngsparametern, som är en del av url:en efter &quot;?&quot;. <br>**Obs**:  [!UICONTROL Paid Search Detection] är skiftlägeskänsligt. En regel som till exempel anger &quot;PID&quot; som frågesträngsparameter kommer inte att matcha &quot;pid&quot;. Om din organisation använder blandade fall placerar du de exakta värdena som separata regler, så att alla önskade frågesträngsparametrar kan fångas upp. |
