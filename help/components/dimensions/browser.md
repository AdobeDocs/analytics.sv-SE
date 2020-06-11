---
title: Webbläsare
description: Namnet på och versionen av den webbläsare som används.
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 0%

---


# Webbläsare

Dimensionen &quot;Webbläsare&quot; visar namnet och versionen på den webbläsare som skickade träffen. Den här dimensionen är användbar för att förstå vilka de vanligaste webbläsarna besökarna använder. När du testar nya versioner av din webbplats kan du köra testerna i de vanligaste webbläsarna i den här dimensionen för att maximera kvalitetskontrollen.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en söktabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet i bildbegäranden `User-Agent` . Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska.

## Dimensionsvärden

Dimensionsvärdena innehåller webbläsarnamn och versioner som används. Olika versioner av samma webbläsare är olika dimensionsvärden.

Vissa dimensionsvärden innehåller `"(unknown version)"` i stället för versionsnumret. Dimensionsvärdet refererar till en ny webbläsarversion som Adobe inte har lagt till i sina sökregister. Eftersom webbläsare uppdateras ofta är `"(unknown version)"` för en viss webbläsare vanliga och tillfälliga. Adobe uppdaterar vanligtvis tabeller under månadsvisa underhållsreleaser.
