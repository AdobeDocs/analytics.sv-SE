---
title: Det gick inte att hitta sidor (mått)
description: Antalet träffar som innehåller ett fel.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: ed4538efa9a28d40ab18fecd3bd87545808d9ac5
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---

# Sidorna hittades inte

*Den här hjälpsidan beskriver hur&quot;Sidor som inte hittas&quot; fungerar som ett mått. Se [Sidorna hittades inte](../dimensions/pages-not-found.md) för mer information.*

Måttet &quot;Sidor som inte hittas&quot; visar antalet träffar där en dimension angavs eller kvarstod när en besökare påträffade ett fel. Det här måttet är värdefullt när du vill se vilka sidor eller URL-adresser som innehåller felmeddelanden (till exempel en 404-adress). Du kan sedan skicka informationen vidare till webbutvecklingsteamet, som kan fastställa orsaken till felet och åtgärda det.

## Hur det här måttet beräknas

Det här måttet räknar alla träffar där [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabeln är lika med värdet för `"errorPage"`. Det är måttmotsvarigheten till [Sidorna hittades inte](../dimensions/pages-not-found.md) dimension.
