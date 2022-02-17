---
title: Avsluta länk
description: Namnet på länken för att avsluta.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---

# Avsluta länk

Dimensionen &#39;Avsluta länk&#39; visar namnen på de avslutningslänkar som implementerats på din webbplats. Den här dimensionen är värdefull när du vill förstå vilka länkar som är populärast och som pekar på domäner utanför din webbplats.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från [`pev2` frågesträng](/help/implement/validate/query-parameters.md) i bildförfrågningar för träffar som också har `pe` frågesträng med värdet för `lnk_e`. Om `pe` frågesträngen har ett annat värde i träffen, den här dimensionen samlar inte in data.

Om du vill skicka data till den här dimensionen med AppMeasurement skickar du en [`tl()`](/help/implement/vars/functions/tl-method.md) bildbegäran med ett länktypargument av `"e"`. Fyll i länknamnsargumentet med det önskade värdet.

## Dimensioner

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
