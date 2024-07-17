---
title: Hämta länk
description: Namnet på nedladdningslänken.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: 33d837cfa7909bd93d5a4f675aa0d8894a403266
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 0%

---

# Hämta länk

Hämtningslänken [dimension](overview.md) rapporterar namnen på hämtningslänkar som har implementerats på din webbplats. Den här dimensionen är värdefull när du vill veta mer om besökares beteende kring nedladdningslänkar, som:

* Bestäm vilka filer som laddas ned oftast från webbplatsen.
* Förstå om vissa filer laddas ned oftare under särskilda tidsperioder.
* Validera att besökarna hämtar olika filtyper om de erbjuds.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från [`pev2`-frågesträngen ](/help/implement/validate/query-parameters.md) i bildbegäranden för träffar som också har frågesträngen `pe` med värdet `lnk_d`. Om frågesträngen `pe` har ett annat värde i träffen samlar dimensionen inte in data.

Om du vill skicka data till den här dimensionen med AppMeasurement skickar du en [`tl()`](/help/implement/vars/functions/tl-method.md)-bildbegäran med länktypsargumentet `"d"`. Fyll i länknamnsargumentet med det önskade värdet:

```js
s.tl(true,"d","Example download link");
```

## Dimensioner

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
