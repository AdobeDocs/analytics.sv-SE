---
title: Funktioner och metoder
description: Lär dig hur du kan använda de funktioner och metoder som Adobe erbjuder i implementeringen.
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Funktioner och metoder

Adobe har flera funktioner och metoder som du kan använda i implementeringen. När du refererar till dessa funktioner eller metoder utför de vanliga uppgifter med en enda kodrad.

Vissa av dessa kodrader tillhör följande kategorier:

* **Spåra anrop**: De vanligaste metoderna och de viktigaste i många implementeringar. De innehåller metoderna [`t()`](t-method.md) och [`tl()`](tl-method.md).
* **AppMeasurement-verktyg**: I tidigare versioner av AppMeasurement var implementeringarna tvungna att skriva sin egen kod för att kunna utföra dessa åtgärder. Adobe har dessa verktygsmetoder för att effektivisera dessa vanliga uppgifter. AppMeasurement innehåller [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md) och [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registrera funktioner**: Du kan skriva egna funktioner och låta AppMeasurement köra dem automatiskt före eller efter ett spårningsanrop till Adobe. Variabler som tillhör den här kategorin är [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md) och [`registerPostTrackCallback()`](registerposttrackcallback.md).
