---
title: Fältbaserad stygn
description: Förstå förutsättningarna och begränsningarna med att sammanfoga data med fältbaserad sammanfogning.
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---


# Fältbaserad stygn

Enhetsövergripande analys erbjuder två olika metoder för att sammanfoga data. Den här metoden är beroende av en Analytics-variabel, till exempel en [prop](/help/implement/vars/page-vars/prop.md) eller [eVar](/help/implement/vars/page-vars/evar.md), som innehåller en personidentifierare. Den använder den variabeln som bas för att länka samman enheter.

## Förutsättningar som är specifika för fältbaserad sammanfogning

Om du tänker implementera enhetsövergripande analys med fältbaserad sammanfogning krävs följande. Samarbeta med team inom organisationen och kontohanteraren för Adobe för att säkerställa att ni uppfyller alla följande:

>[!IMPORTANT]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att aktivera enhetsövergripande analys eller dåliga resultat när data sammanfogas.

* Alla krav som anges på översiktssidan [](overview.md).
* Implementeringen måste ange ett utkast eller en eVar som unikt identifierar en individ när det är möjligt, till exempel när en användare loggar in eller öppnar ett e-postmeddelande. Detta krav gäller alla plattformar, inklusive mobilappar om de används. Informera kontohanteraren om den önskade identifieringsvariabeln när den tillhandahålls för fältbaserad sammanfogning.

## Begränsningar som är specifika för fältbaserad sammanfogning

* Fältbaserad sammanfogning fungerar bäst på rapportsviter med hög användaridentifieringsfrekvens. Om rapportsviten har låg identifierings- eller inloggningsfrekvens bör du använda [Co-op-diagrammet](device-graph.md).

## Nästa steg

När din organisation uppfyller alla krav och förstår begränsningarna kan du börja med [Konfigurera Cross-Device Analytics](setup.md).