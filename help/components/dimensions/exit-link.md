---
title: Avsluta länk
description: Namnet på länken för att avsluta.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Avsluta länk

Avsluta länk [dimension](overview.md) rapporterar namnen på de avslutningslänkar som implementerats på din plats. Den här dimensionen är värdefull när du vill förstå vilka länkar som är populärast och som pekar på domäner utanför din webbplats.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från [`pev2`-frågesträngen &#x200B;](/help/implement/validate/query-parameters.md) i bildbegäranden för träffar som också har frågesträngen `pe` med värdet `lnk_e`. Om frågesträngen `pe` har ett annat värde i träffen samlar dimensionen inte in data. Den maximala längden för den här dimensionen är 100 byte.

Om du vill skicka data till den här dimensionen med AppMeasurement skickar du en [`tl()`](/help/implement/vars/functions/tl-method.md)-bildbegäran med ett länktypsargument på `"e"`. Fyll i länknamnsargumentet med det önskade värdet.

## Dimension-objekt

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
