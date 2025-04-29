---
title: Egen länk
description: Namnet på den anpassade länken.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# Egen länk

Den anpassade länken [dimension](overview.md) rapporterar namnen på anpassade länkar som implementerats på din plats. Den här dimensionen är värdefull när du vill förstå vilka typer av länkar besökarna klickar mest på.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från [`pev2`-frågesträngen ](/help/implement/validate/query-parameters.md) i bildbegäranden för träffar som också har frågesträngen `pe` med värdet `lnk_o`. Om frågesträngen `pe` har ett annat värde i träffen samlar dimensionen inte in data. Den maximala längden för den här dimensionen är 100 byte.

Om du vill skicka data till den här dimensionen med AppMeasurement skickar du en [`tl()`](/help/implement/vars/functions/tl-method.md)-bildbegäran med ett länktypsargument på `"o"`. Fyll i länknamnsargumentet med det önskade värdet.

## Dimension-objekt

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
