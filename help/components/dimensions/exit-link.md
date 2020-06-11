---
title: Avsluta länk
description: Namnet på länken för att avsluta.
translation-type: tm+mt
source-git-commit: c9e696201d0e9ec97dcdd6ff797ca72244dcf366
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---


# Avsluta länk

Dimensionen &#39;Avsluta länk&#39; visar namnen på de avslutningslänkar som implementerats på din webbplats. Den här dimensionen är värdefull när du vill förstå vilka länkar som är populärast och som pekar på domäner utanför din webbplats.

## Fyll den här dimensionen med data

Denna dimension samlar in data från [`pev2` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden för träffar som också har `pe` frågesträngen med värdet `lnk_e`. Om `pe` frågesträngen har ett annat värde i träffen samlar dimensionen inte in data.

Om du vill skicka data till den här dimensionen med AppMeasurement:

* Fyll variabeln med det önskade [`linkName`](/help/implement/vars/config-vars/linkname.md) värdet.
* Ställ in [`linkType`](/help/implement/vars/config-vars/linktype.md) variabeln på `"e"`.
* Skicka en [`tl()`](/help/implement/vars/functions/tl-method.md) bildförfrågan.

## Dimensionsvärden

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vilka dimensionsvärden som är. Adobe rekommenderar att du grupperar länkar i meningsfulla kategorier baserat på dina rapporteringsbehov.
