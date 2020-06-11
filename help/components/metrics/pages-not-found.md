---
title: Sidorna hittades inte
description: Antalet träffar som innehåller ett fel.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%

---


# Sidorna hittades inte

*Den här hjälpsidan beskriver hur&quot;Sidor som inte hittas&quot; fungerar som ett mått. Mer information finns i dimensionen[Sidor som inte hittas](../dimensions/pages-not-found.md).*

Mätvärdet &quot;Sidor som inte hittas&quot; visar antalet träffar där sidan innehöll ett fel. Det här måttet är värdefullt när du vill se vilka sidor eller URL-adresser som innehåller felmeddelanden (till exempel 404), så att du kan fastställa orsaken till felet och åtgärda det.

## Hur det här måttet beräknas

Det här måttet räknar alla träffar där [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabeln är lika med värdet för `"errorPage"`. Det är måttmotsvarigheten för de [sidor som inte hittas](../dimensions/pages-not-found.md) .