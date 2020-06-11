---
title: Avslutar
description: En instans av det sista värdet i ett besök.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---


# Avslutar

*Den här hjälpsidan beskriver hur avslutar fungerar som ett mått. Mer information om hur avslutar fungerar som en dimension finns i[Avsluta dimensioner](../dimensions/exit-dimensions.md).*

Måttet &#39;Exits&#39; visar hur många gånger ett givet dimensionsvärde hämtas som det sista värdet vid ett besök. Detta mått är användbart när du vill veta mer om det sista besökarna ser innan de lämnar din webbplats. Att se de sista värdena i en dimension kan hjälpa er att förstå och optimera upplevelsen som besökaren får innan de går.

## Hur det här måttet beräknas

När ett [besök](visits.md) är klart ska du registrera det senaste dimensionsvärdet som en avslutning. Det finns bara en avslutning per dimension och besök. Det är inte nödvändigtvis den sista träffen av besöket om dimensionen ställdes in i tidigare träffar. Det är ett besöksbaserat mätresultat. det gäller retroaktivt alla träffar på besöket.

>[!TIP] Om du visar det här måttet mot en dimension som inte alltid är inställd vid varje besök, kan du dölja dimensionsvärdet Ospecificerat i Analysis Workspace. Klicka på filterikonen och avmarkera sedan [!UICONTROL Include unspecified (None)].
