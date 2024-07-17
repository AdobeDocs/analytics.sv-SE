---
title: Avslutar
description: En instans av det sista värdet i ett besök.
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---

# Avslutar

*Den här hjälpsidan beskriver hur avslutar fungerar som ett mått. Mer information om hur avslutar fungerar som en dimension finns i [Avsluta dimensioner](../dimensions/exit-dimensions.md).*

Måttet [Exits](overview.md) visar hur många gånger ett angivet dimensionsobjekt hämtas som det sista värdet vid ett besök. Detta mått är användbart när du vill veta mer om det sista besökarna ser innan de lämnar din webbplats. Att se de sista värdena i en dimension kan hjälpa er att förstå och optimera upplevelsen som besökaren får innan de går.

## Hur det här måttet beräknas

När ett [besök](visits.md) är avslutat registrerar du det senaste dimensionsobjektet som en avslutning. Det finns bara en avslutning per dimension och besök. Det är inte nödvändigtvis den sista träffen av besöket om dimensionen ställdes in i tidigare träffar. Det är en besöksbaserad mätmetod som gäller retroaktivt för alla träffar i besöket.

>[!TIP]
>
>Om du visar det här måttet mot en dimension som inte alltid är inställd vid varje besök kan du dölja dimensionsobjektet &#39;Ospecificerad&#39; i Analysis Workspace. Klicka på filterikonen och avmarkera sedan [!UICONTROL Include unspecified (None)].
