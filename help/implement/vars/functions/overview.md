---
title: Funktioner och metoder
description: Lär dig hur du kan använda de funktioner och metoder som Adobe erbjuder i implementeringen.
feature: Variables
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Funktioner och metoder

Adobe har flera funktioner och metoder som du kan använda i implementeringen. När du refererar till dessa funktioner eller metoder utför de vanliga uppgifter med en enda kodrad.

Vissa av dessa kodrader tillhör följande kategorier:

* **Spåra samtal**: De vanligaste metoderna och de viktigaste i många implementeringar. De innehåller [`t()`](t-method.md) och [`tl()`](tl-method.md) metoder.
* **AppMeasurement utilities**: I tidigare versioner av AppMeasurementet var implementeringarna tvungna att skriva sin egen kod för att utföra dessa åtgärder. Adobe tillhandahåller dessa verktygsmetoder för att effektivisera dessa vanliga uppgifter. AppMeasurementen innehåller [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md)och [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registerfunktioner**: Du kan skriva egna funktioner och låta AppMeasurementet köra dem automatiskt före eller efter att du har skickat ett spårningsanrop till Adobe. Variabler som tillhör den här kategorin är [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md)och [`registerPostTrackCallback()`](registerposttrackcallback.md).
