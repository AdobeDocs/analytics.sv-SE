---
title: Hämta länk
description: Namnet på nedladdningslänken.
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 0%

---


# Hämta länk

Dimensionen Download link visar namnen på de nedladdningslänkar som har implementerats på din webbplats. Den här dimensionen är värdefull när du vill veta mer om besökares beteende kring nedladdningslänkar, som:

* Bestäm vilka filer som laddas ned oftast från webbplatsen.
* Förstå om vissa filer laddas ned oftare under särskilda tidsperioder.
* Validera att besökarna hämtar olika filtyper om de erbjuds.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från [`pev2`-frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden för träffar som också har `pe`-frågesträngen med värdet `lnk_d`. Om frågesträngen `pe` har ett annat värde i träffen, samlar dimensionen inte in data.

Om du vill skicka data till den här dimensionen med AppMeasurement skickar du en [`tl()`](/help/implement/vars/functions/tl-method.md)-bildbegäran med ett länktypsargument på `"d"`. Fyll i länknamnsargumentet med det önskade värdet.

## Dimensioner

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
