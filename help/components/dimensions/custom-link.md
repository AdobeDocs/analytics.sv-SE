---
title: Egen länk
description: Namnet på den anpassade länken.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Egen länk

Dimensionen Anpassad länk rapporterar namnen på anpassade länkar som implementerats på din webbplats. Den här dimensionen är värdefull när du vill förstå vilka typer av länkar besökarna klickar mest på.

## Fyll den här dimensionen med data

Denna dimension samlar in data från [`pev2` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden för träffar som också har `pe` frågesträngen med värdet `lnk_o`. Om `pe` frågesträngen har ett annat värde i träffen samlar dimensionen inte in data.

Om du vill skicka data till den här dimensionen med AppMeasurement:

* Fyll variabeln med det önskade [`linkName`](/help/implement/vars/config-vars/linkname.md) värdet.
* Ställ in [`linkType`](/help/implement/vars/config-vars/linktype.md) variabeln på `"o"`.
* Skicka en [`tl()`](/help/implement/vars/functions/tl-method.md) bildförfrågan.

## Dimensionsobjekt

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
