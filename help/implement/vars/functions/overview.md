---
title: Funktioner och metoder
description: Lär dig hur du kan använda de funktioner och metoder som Adobe erbjuder i implementeringen.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Funktioner och metoder

Adobe erbjuder flera funktioner och metoder som du kan använda i implementeringen. När du refererar till dessa funktioner eller metoder utför de vanliga uppgifter med en enda kodrad.

Vissa av dessa kodrader tillhör följande kategorier:

* **Spåra samtal**: De vanligaste metoderna och de viktigaste i många implementeringar. De innehåller metoderna [`t()`](t-method.md) och [`tl()`](tl-method.md) .
* **AppMeasurement-verktyg**: I tidigare versioner av AppMeasurement var implementeringarna tvungna att skriva sin egen kod för att kunna utföra dessa åtgärder. Adobe tillhandahåller dessa verktygsmetoder för att effektivisera dessa vanliga uppgifter. AppMeasurement-verktygen inkluderar [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md)och [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registreringsfunktioner**: Du kan skriva egna funktioner och låta AppMeasurement köra dem automatiskt före eller efter att du har skickat ett spårningsanrop till Adobe. Variabler som tillhör den här kategorin är [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md)och [`registerPostTrackCallback()`](registerposttrackcallback.md).
