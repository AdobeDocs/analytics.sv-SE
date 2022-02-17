---
title: Hämta länk
description: Namnet på nedladdningslänken.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
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

Den här dimensionen samlar in data från [`pev2` frågesträng](/help/implement/validate/query-parameters.md) i bildförfrågningar för träffar som också har `pe` frågesträng med värdet för `lnk_d`. Om `pe` frågesträngen har ett annat värde i träffen, den här dimensionen samlar inte in data.

Om du vill skicka data till den här dimensionen med AppMeasurement skickar du en [`tl()`](/help/implement/vars/functions/tl-method.md) bildbegäran med ett länktypargument av `"d"`. Fyll i länknamnsargumentet med det önskade värdet.

## Dimensioner

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
