---
title: Hämta länk
description: Namnet på nedladdningslänken.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 0%

---


# Hämta länk

Dimensionen Download link visar namnen på de nedladdningslänkar som har implementerats på din webbplats. Den här dimensionen är värdefull när du vill veta mer om besökares beteende kring nedladdningslänkar, som:

* Bestäm vilka filer som laddas ned oftast från webbplatsen.
* Förstå om vissa filer laddas ned oftare under särskilda tidsperioder.
* Validera att besökarna hämtar olika filtyper om de erbjuds.

## Fyll den här dimensionen med data

Denna dimension samlar in data från [`pev2` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden för träffar som också har `pe` frågesträngen med värdet `lnk_d`. Om `pe` frågesträngen har ett annat värde i träffen samlar dimensionen inte in data.

Om du vill skicka data till den här dimensionen med AppMeasurement:

* Fyll variabeln med det önskade [`linkName`](/help/implement/vars/config-vars/linkname.md) värdet.
* Ställ in [`linkType`](/help/implement/vars/config-vars/linktype.md) variabeln på `"d"`.
* Skicka en [`tl()`](/help/implement/vars/functions/tl-method.md) bildförfrågan.

## Dimensionsvärden

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vilka dimensionsvärden som är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
