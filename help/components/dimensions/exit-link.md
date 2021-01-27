---
title: Avsluta länk
description: Namnet på länken för att avsluta.
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---


# Avsluta länk

Dimensionen &#39;Avsluta länk&#39; visar namnen på de avslutningslänkar som implementerats på din webbplats. Den här dimensionen är värdefull när du vill förstå vilka länkar som är populärast och som pekar på domäner utanför din webbplats.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från [`pev2`-frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden för träffar som också har `pe`-frågesträngen med värdet `lnk_e`. Om frågesträngen `pe` har ett annat värde i träffen, samlar dimensionen inte in data.

Om du vill skicka data till den här dimensionen med AppMeasurement skickar du en [`tl()`](/help/implement/vars/functions/tl-method.md)-bildbegäran med ett länktypsargument på `"e"`. Fyll i länknamnsargumentet med det önskade värdet.

## Dimensioner

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
