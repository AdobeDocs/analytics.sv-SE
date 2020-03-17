---
title: Vanliga frågor om identifiering av besökare på olika enheter
description: Vanliga frågor och svar om identifiering av besökare på olika enheter
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Vanliga frågor om identifiering av besökare på olika enheter

Vanliga frågor och svar om identifiering av besökare på olika enheter.

**Vad är skillnaden mellan identifiering av besökare på olika enheter och analys på olika enheter?**

Identifiering av besökare på olika enheter använder variabeln för att knyta samman enheter, med flera stora begränsningar. `visitorID` En av de största begränsningarna med den här identifieringsmetoden är att oautentiserade träffar isoleras om inte enheten redan har identifierats. Dessa oautentiserade träffar kan öka antalet besökare.

Enhetsövergripande analys är Adobes senaste metod för identifiering av besökare på olika enheter. Det använder Experience Cloud ID-tjänsten och enhetsgrafen för att retroaktivt sammanfoga besök från olika enheter. CDA kräver att funktionen används för `setCustomerIDs` att avgöra vilka enheter som används av samma besökare.

**Hur hanterar identifieringen av besökare på olika enheter segment?**

Identifiering av besökare på olika enheter hanterar segment på liknande sätt som andra funktioner. Den tittar på varje enskild träff för att se om den matchar segmentvillkoren, och inkluderar dessa träffar i dina data om de matchar. Segment som använder besöks- och besöksbaserade behållare tittar fortfarande på besökar-ID:t. Se till att implementeringen använder variabeln där det är möjligt för att konsekvent identifiera unika besökare för segmentering. `visitorID`
