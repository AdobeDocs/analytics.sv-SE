---
title: Fältbaserad stygn
description: Förstå förutsättningarna och begränsningarna med att sammanfoga data med fältbaserad sammanfogning.
translation-type: tm+mt
source-git-commit: 7b43c4ebbf9446507ab90a90e26c51635303dcc6
workflow-type: tm+mt
source-wordcount: '303'
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
* Även om props och eVars har regler för hur versaler och gemener hanteras för rapportering, innebär fältbaserad stygn inte att den propp eller eVar som används för stygn omvandlas på något sätt. Fältbaserad sammanfogning använder värdet i det angivna fältet så som det finns efter VISTA-regler och regler för efterbearbetning. Om ibland ordet &#39;Bob&#39; visas i utkastet/eVar och ibland ordet &#39;BOB&#39; visas, behandlas dessa som två separata personer.

## Nästa steg

När organisationen uppfyller alla krav och förstår begränsningarna kan du börja [konfigurera enhetsövergripande analyser](setup.md).
