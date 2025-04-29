---
title: Det gick inte att hitta sidor (mått)
description: Antalet träffar som innehåller ett fel.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 0%

---

# Sidorna hittades inte

*Den här hjälpsidan beskriver hur &quot;Sidor som inte hittas&quot; fungerar som ett mått. Mer information om hur det fungerar som en dimension finns på sidan [Sidor som inte hittas](../dimensions/pages-not-found.md).*

Sidorna hittades inte [metrisk](overview.md) visar antalet träffar där en dimension angavs eller bestals när en besökare påträffade ett fel. Det här måttet är värdefullt när du vill se vilka sidor eller URL-adresser som innehåller felmeddelanden (till exempel en 404-adress). Du kan sedan skicka informationen vidare till webbutvecklingsteamet, som kan fastställa orsaken till felet och åtgärda det.

## Hur det här måttet beräknas

Det här måttet räknar alla träffar där variabeln [`pageType`](/help/implement/vars/page-vars/pagetype.md) är lika med värdet `"errorPage"`. Det är måttmotsvarigheten för dimensionen [Sidor som inte hittas](../dimensions/pages-not-found.md).
