---
title: Egen länk
description: Namnet på den anpassade länken.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---

# Egen länk

Dimensionen Anpassad länk rapporterar namnen på anpassade länkar som implementerats på din webbplats. Den här dimensionen är värdefull när du vill förstå vilka typer av länkar besökarna klickar mest på.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från [`pev2` frågesträng](/help/implement/validate/query-parameters.md) i bildförfrågningar för träffar som också har `pe` frågesträng med värdet för `lnk_o`. Om `pe` frågesträngen har ett annat värde i träffen, den här dimensionen samlar inte in data.

Om du vill skicka data till den här dimensionen med AppMeasurement skickar du en [`tl()`](/help/implement/vars/functions/tl-method.md) bildbegäran med ett länktypargument av `"o"`. Fyll i länknamnsargumentet med det önskade värdet.

## Dimensioner

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
