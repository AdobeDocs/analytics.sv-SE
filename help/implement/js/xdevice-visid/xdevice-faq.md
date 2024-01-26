---
title: Vanliga frågor om identifiering av besökare på olika enheter
description: Vanliga frågor och svar om identifiering av besökare på olika enheter
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Vanliga frågor om identifiering av besökare på olika enheter

Vanliga frågor och svar om identifiering av besökare på olika enheter.

+++Vad är skillnaden mellan identifiering av besökare på olika enheter och analys på olika enheter?
Identifiering av besökare på olika enheter använder `visitorID` variabel för att knyta ihop enheter, med flera stora begränsningar. En av de största begränsningarna med den här identifieringsmetoden är att oautentiserade träffar isoleras om inte enheten redan har identifierats. Dessa oautentiserade träffar kan öka antalet besökare.

Cross-Device Analytics är den senaste metoden för identifiering av besökare mellan olika enheter i Adobe. Experience Cloud ID-tjänsten och enhetsdiagrammet används för att retroaktivt sammanfoga besök från olika enheter. CDA kräver att `setCustomerIDs` funktion för att avgöra vilka enheter som används av samma besökare.
+++

+++Hur hanterar identifiering av besökare på olika enheter segment?
Identifiering av besökare på olika enheter hanterar segment på liknande sätt som andra funktioner. Den tittar på varje enskild träff för att se om den matchar segmentvillkoren, och inkluderar dessa träffar i dina data om de matchar. Segment som använder besöks- och besöksbaserade behållare tittar fortfarande på besökar-ID:t. Se till att implementeringen använder `visitorID` variabel där det är möjligt för att konsekvent identifiera unika besökare för segmentering.
+++
