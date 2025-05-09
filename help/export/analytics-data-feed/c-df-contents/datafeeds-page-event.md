---
description: Uppslagstabell som avgör typen av träff baserat på sidhändelse.
keywords: page;event;page_event;post_page_event
title: Sökning efter sidhändelse
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Sökning efter sidhändelse

Uppslagstabell som avgör typen av träff baserat på värdet `page_event`. Som vi nämnt i [Datakolumnreferensen](datafeeds-reference.md) är kolumnerna `page_event` och `post_page_event` tinyint osignerade.

* Mer information om hur du implementerar sidvisningsanrop för AppMeasurement och Web SDK finns i [`t()`](/help/implement/vars/functions/t-method.md).
* Mer information om hur du implementerar länkspårningsanrop för AppMeasurement och Web SDK finns i [`tl()`](/help/implement/vars/functions/tl-method.md).
* Se [Implementera Adobe Analytics med Adobe Experience Platform Edge Network](/help/implement/aep-edge/overview.md) för att förstå hur Adobe Analytics översätter XDM-nyttolaster till sidhändelsetyper.

| `page_event` värde | `post_page_event` värde | Beskrivning |
| --- | --- | --- |
| `0` | `0` | Alla standardanrop för sidvisning. Det är standardvärdet för de flesta träffar. |
| `10` | `100` | Anpassade länkar. Ange länktyp till `o` (AppMeasurement) eller `xdm.web.webInteraction.type` till `other` (Web SDK eller Mobile SDK). |
| `11` | `101` | Hämta länkar. Ange länktyp till `d` (AppMeasurement) eller `xdm.web.webInteraction.type` till `download` (Web SDK eller Mobile SDK). |
| `12` | `102` | Avsluta länkar. Ange länktyp till `e` (AppMeasurement) eller `xdm.web.webInteraction.type` till `exit` (Web SDK eller Mobile SDK). |
| `31` | `76` | Mediestart |
| `32` | `77` | Medieuppdateringar (utan annan variabelbearbetning) |
| `33` | `78` | Medieuppdateringar (med annan variabelbearbetning) |
| `40` | `80` | Undersökning |
| `50` | `50` | Start av direktuppspelande media |
| `51` | `51` | Stänga direktuppspelande media |
| `52` | `52` | Direktuppspelning av mediaskärmning |
| `53` | `53` | Direktuppspelande media hålls levande |
| `54` | `54` | Streaming media och start |
| `55` | `55` | Direktuppspelande media och stängning |
| `56` | `56` | Direktuppspelning av media och snabbspolning |
| `60` | `60` | Primetime-mediestart |
| `61` | `61` | Stäng primär media |
| `62` | `62` | Rensa media i Primetime |
| `63` | `63` | Primetimes media håller sig levande |
| `64` | `64` | Start av annonsering i Primetime-media |
| `65` | `65` | Primetime media - stäng |
| `66` | `66` | Rensning av annonser i Primetime |
| `70` | `70` | Inkluderar målaktivitetsdata |
