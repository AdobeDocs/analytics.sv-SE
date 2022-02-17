---
title: Sidorna hittades inte
description: Antalet träffar som innehåller ett fel.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%

---

# Sidorna hittades inte

*Den här hjälpsidan beskriver hur&quot;Sidor som inte hittas&quot; fungerar som ett mått. Se [Sidorna hittades inte](../dimensions/pages-not-found.md) för mer information.*

Mätvärdet &quot;Sidor som inte hittas&quot; visar antalet träffar där sidan innehöll ett fel. Det här måttet är värdefullt när du vill se vilka sidor eller URL-adresser som innehåller felmeddelanden (till exempel 404), så att du kan fastställa orsaken till felet och åtgärda det.

## Hur det här måttet beräknas

Det här måttet räknar alla träffar där [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabeln är lika med värdet för `"errorPage"`. Det är måttmotsvarigheten till [Sidorna hittades inte](../dimensions/pages-not-found.md) dimension.
