---
title: Dagar före första köpet
description: Antalet dagar mellan besökarens första besök och deras första inköp.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# Dagar före första köpet

Dagar före första köp [dimension](overview.md) rapporterar antalet dagar som går mellan den första gången en besökare kommer till er webbplats och när de gör ett köp. Om en besökare till exempel gör ett köp en dag efter första besök, tillhör alla efterföljande besök eller evenemang dimensionsposten&quot;1 dag&quot;.

När en besökare gör sitt första köp tillhör de samma dimensionsobjekt under resten av besökarens cookie-livstid.

## Fyll den här dimensionen med data

Adobe fyller automatiskt i dimensionen baserat på [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) i implementeringen. Om du implementerar `purchase` den här dimensionen fungerar alltid på din webbplats.

## Dimensioner

Dimensionen omfattar antalet dagar mellan besökarens första besök på webbplatsen och deras första inköp. Varje antal dagar är en separat dimensionspost, där&quot;samma dag&quot; inträffar där en besökares första besök och deras första inköp sker samma dag.
