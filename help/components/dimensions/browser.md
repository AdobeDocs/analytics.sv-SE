---
title: Webbläsare
description: Namnet på och versionen av den webbläsare som används.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%

---


# Webbläsare

Dimensionen &quot;Webbläsare&quot; visar namnet och versionen på den webbläsare som skickade träffen. Den här dimensionen är användbar för att förstå vilka de vanligaste webbläsarna besökarna använder. När du testar nya versioner av din webbplats kan du köra testerna i de vanligaste webbläsarna i den här dimensionen för att maximera kvalitetskontrollen.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en söktabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet i bildbegäranden `User-Agent` . Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen direkt.

## Dimensionsobjekt

Dimensionsobjekten är webbläsarnamn och versioner som används. Olika versioner av samma webbläsare är separata dimensionsobjekt.

Vissa dimensionsobjekt innehåller `"(unknown version)"` i stället för versionsnumret. Dimensionsobjektet refererar till en ny webbläsarversion som Adobe inte har lagt till i sina sökregister. Eftersom webbläsare uppdateras ofta är `"(unknown version)"` för en viss webbläsare vanliga och tillfälliga. Adobe uppdaterar vanligtvis tabeller under månadsvisa underhållsreleaser.
