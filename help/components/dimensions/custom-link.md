---
title: Egen länk
description: Namnet på den anpassade länken.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---

# Egen länk

The Custom link [dimension](overview.md) rapporterar namnen på anpassade länkar som implementerats på din plats. Den här dimensionen är värdefull när du vill förstå vilka typer av länkar besökarna klickar mest på.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från [`pev2` frågesträng](/help/implement/validate/query-parameters.md) i bildförfrågningar för träffar som också har `pe` frågesträng med värdet för `lnk_o`. Om `pe` frågesträngen har ett annat värde i träffen, den här dimensionen samlar inte in data.

Om du vill skicka data till den här dimensionen med AppMeasurement skickar du en [`tl()`](/help/implement/vars/functions/tl-method.md) bildbegäran med ett länktypargument av `"o"`. Fyll i länknamnsargumentet med det önskade värdet.

## Dimensioner

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
