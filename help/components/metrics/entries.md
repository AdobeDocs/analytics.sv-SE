---
title: Första besökssida
description: En instans av det första värdet i ett besök.
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 1%

---

# Första besökssida

*Den här hjälpsidan beskriver hur poster fungerar som mått. Mer information om hur poster fungerar som en dimension finns i [Postdimensioner](../dimensions/entry-dimensions.md).*

Transaktioner [mått](overview.md) visar hur många gånger en viss dimensionspost hämtas som första värde vid ett besök. Den här mätningen är användbar när du vill veta mer om de första visningar besökarna har på din webbplats. Att se de första värdena i en dimension kan hjälpa er att förstå och optimera upplevelsen som en ny besökare får.

## Hur det här måttet beräknas

För en given dimension registrerar du den första dimensionsposten som visas som en post vid ett besök. Det finns bara ett inlägg per dimension och besök. Det är inte nödvändigtvis första besöket om dimensionen inte är inställd från början. Det är ett besöksbaserat mätresultat. När det väl är kopplat till en dimensionspost kvarstår det för resten av besöket.

>[!TIP]
>
>Om du visar det här måttet mot en dimension som inte alltid är inställd vid varje besök kan du dölja dimensionsobjektet &#39;Ospecificerad&#39; i Analysis Workspace. Klicka på filterikonen och avmarkera [!UICONTROL Include unspecified (None)].
