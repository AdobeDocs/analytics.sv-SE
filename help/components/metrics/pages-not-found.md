---
title: Det gick inte att hitta sidor (mått)
description: Antalet träffar som innehåller ett fel.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Sidorna hittades inte

*Den här hjälpsidan beskriver hur&quot;Sidor som inte hittas&quot; fungerar som ett mått. Se [Sidorna hittades inte](../dimensions/pages-not-found.md) för mer information.*

Mätvärdet &quot;Sidor som inte hittas&quot; visar antalet träffar där sidan innehöll ett fel. Det här måttet är värdefullt när du vill se vilka sidor eller URL-adresser som innehåller felmeddelanden (till exempel 404), så att du kan fastställa orsaken till felet och åtgärda det.

## Hur det här måttet beräknas

Det här måttet räknar alla träffar där [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabeln är lika med värdet för `"errorPage"`. Det är måttmotsvarigheten till [Sidorna hittades inte](../dimensions/pages-not-found.md) dimension.
