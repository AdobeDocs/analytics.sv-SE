---
title: Första besökssida
description: En instans av det första värdet i ett besök.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 1%

---


# Första besökssida

*Den här hjälpsidan beskriver hur poster fungerar som mått. Mer information om hur poster fungerar som en dimension finns i[Postdimensioner](../dimensions/entry-dimensions.md).*

Måttet Inmatningar visar hur många gånger en given dimensionspost hämtas som första värde vid ett besök. Detta mått är användbart när du vill veta mer om de första visningar besökarna har på din webbplats. Att se de första värdena i en dimension kan hjälpa er att förstå och optimera upplevelsen som en ny besökare får.

## Hur det här måttet beräknas

För en given dimension registrerar du den första dimensionsposten som visas som en post vid ett besök. Det finns bara ett inlägg per dimension och besök. Det är inte nödvändigtvis första besöket om dimensionen inte är inställd från början. Det är ett besöksbaserat mätresultat. när den är kopplad till en dimensionsuppgift kvarstår den för resten av besöket.

>[!TIP]
>
>Om du visar det här måttet mot en dimension som inte alltid är inställd vid varje besök kan du dölja dimensionsobjektet &#39;Ospecificerad&#39; i Analysis Workspace. Klicka på filterikonen och avmarkera sedan [!UICONTROL Include unspecified (None)].
