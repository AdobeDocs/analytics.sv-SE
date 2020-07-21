---
title: Fältbaserad stygn
description: Förstå förutsättningarna och begränsningarna med att sammanfoga data med fältbaserad sammanfogning.
translation-type: tm+mt
source-git-commit: 2e7ec3b2e4401b02005b3099dae2bb34c64a6846
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---


# Fältbaserad stygn

Analytics erbjuder två olika sätt att knyta ihop data. Den här metoden är beroende av en Analytics-variabel, till exempel en [prop](/help/implement/vars/page-vars/prop.md) eller [eVar](/help/implement/vars/page-vars/evar.md), som innehåller en personidentifierare. Den använder den variabeln som bas för att länka samman enheter.

## Förutsättningar som är specifika för fältbaserad sammanfogning

Om du tänker implementera Analytics för olika enheter med fältbaserad sammanfogning krävs följande. Samarbeta med team inom organisationen och er kontoansvarige på Adobe för att säkerställa att ni uppfyller alla följande krav.

>[!IMPORTANT] Om du inte uppfyller alla krav kan det leda till att det inte går att aktivera Analytics för olika enheter eller till dåliga resultat när du sammanfogar data.

* Alla krav som anges på [översiktssidan](overview.md).
* Implementeringen måste ange en prop eller eVar som unikt identifierar en individ när det är möjligt, till exempel när en användare loggar in eller öppnar ett e-postmeddelande. Detta krav gäller alla plattformar, inklusive mobilappar om de används. Informera kontohanteraren om den önskade identifieringsvariabeln när den tillhandahålls för fältbaserad sammanfogning.

## Begränsningar som är specifika för fältbaserad sammanfogning

* Fältbaserad sammanfogning fungerar bäst på rapportsviter med hög användaridentifieringsfrekvens. Om rapportsviten har låg identifierings- eller inloggningsfrekvens kan du använda [Co-op-diagrammet](device-graph.md).

## Nästa steg

När organisationen uppfyller alla krav och förstår begränsningarna kan du börja [konfigurera Analytics](setup.md)för olika enheter.