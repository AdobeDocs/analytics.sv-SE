---
title: Sista besökssida
description: En instans av det sista värdet i ett besök.
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---

# Sista besökssida

*Den här hjälpsidan beskriver hur avslutar fungerar som ett mått. Mer information om hur slutar fungera som en dimension finns i [Avsluta dimensioner](../dimensions/exit-dimensions.md).*

Måttet &#39;Exits&#39; visar hur många gånger en given dimensionspost hämtas som det sista värdet vid ett besök. Detta mått är användbart när du vill veta mer om det sista besökarna ser innan de lämnar din webbplats. Att se de sista värdena i en dimension kan hjälpa er att förstå och optimera upplevelsen som besökaren får innan de går.

## Hur det här måttet beräknas

Efter [besök](visits.md) slutför, registrera den senaste dimensionsartikeln som en avslutning. Det finns bara en avslutning per dimension och besök. Det är inte nödvändigtvis den sista träffen av besöket om dimensionen ställdes in i tidigare träffar. Det är ett besöksbaserat mätresultat. det gäller retroaktivt alla träffar på besöket.

>[!TIP]
>
>Om du visar det här måttet mot en dimension som inte alltid är inställd vid varje besök kan du dölja dimensionsobjektet &#39;Ospecificerad&#39; i Analysis Workspace. Klicka på filterikonen och avmarkera [!UICONTROL Include unspecified (None)].
