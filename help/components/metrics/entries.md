---
title: Poster
description: En instans av det första värdet i ett besök.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---


# Poster

*Den här hjälpsidan beskriver hur poster fungerar som mått. Mer information om hur poster fungerar som en dimension finns i[Postdimensioner](../dimensions/entry-dimensions.md).*

Måttet Inmatningar visar hur många gånger ett givet dimensionsvärde hämtas som det första värdet vid ett besök. Detta mått är användbart när du vill veta mer om de första visningar besökarna har på din webbplats. Att se de första värdena i en dimension kan hjälpa er att förstå och optimera upplevelsen som en ny besökare får.

## Hur det här måttet beräknas

För en given dimension ska du registrera det första dimensionsvärdet som ses vid ett besök som ett tävlingsbidrag. Det finns bara ett inlägg per dimension och besök. Det är inte nödvändigtvis första besöket om dimensionen inte är inställd från början. Det är ett besöksbaserat mätresultat. när det är kopplat till ett dimensionsvärde kvarstår det under resten av besöket.

>[!TIP] Om du visar det här måttet mot en dimension som inte alltid är inställd vid varje besök, kan du dölja dimensionsvärdet Ospecificerat i Analysis Workspace. Klicka på filterikonen och avmarkera sedan [!UICONTROL Include unspecified (None)].
