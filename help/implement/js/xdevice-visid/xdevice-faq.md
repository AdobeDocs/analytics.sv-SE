---
title: Vanliga frågor om identifiering av besökare på olika enheter
description: Vanliga frågor och svar om identifiering av besökare på olika enheter
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---


# Vanliga frågor om identifiering av besökare på olika enheter

Vanliga frågor och svar om identifiering av besökare på olika enheter.

**Vad är skillnaden mellan identifiering av besökare på olika enheter och analys på olika enheter?**

Identifiering av besökare på olika enheter använder variabeln `visitorID` för att knyta samman enheter, med flera stora begränsningar. En av de största begränsningarna med den här identifieringsmetoden är att oautentiserade träffar isoleras om inte enheten redan har identifierats. Dessa oautentiserade träffar kan öka antalet besökare.

Cross-Device Analytics är den senaste metoden för identifiering av besökare mellan olika enheter i Adobe. Experience Cloud ID-tjänsten och enhetsdiagrammet används för att retroaktivt sammanfoga besök från olika enheter. CDA kräver att funktionen `setCustomerIDs` används för att avgöra vilka enheter som används av samma besökare.

**Hur hanterar identifieringen av besökare på olika enheter segment?**

Identifiering av besökare på olika enheter hanterar segment på liknande sätt som andra funktioner. Den tittar på varje enskild träff för att se om den matchar segmentvillkoren, och inkluderar dessa träffar i dina data om de matchar. Segment som använder besöks- och besöksbaserade behållare tittar fortfarande på besökar-ID:t. Se till att implementeringen använder variabeln `visitorID` där det är möjligt för att konsekvent identifiera unika besökare för segmentering.
