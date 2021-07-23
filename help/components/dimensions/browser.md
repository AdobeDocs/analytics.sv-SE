---
title: Webbläsare
description: Namnet på och versionen av den webbläsare som används.
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# Webbläsare

Dimensionen &quot;Webbläsare&quot; visar namnet och versionen på den webbläsare som skickade träffen. Den här dimensionen är användbar för att förstå vilka de vanligaste webbläsarna besökarna använder. När du testar nya versioner av din webbplats kan du köra testerna i de vanligaste webbläsarna i den här dimensionen för att maximera kvalitetskontrollen.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet `User-Agent` i bildbegäranden. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt.

## Dimensioner

Bland Dimensionerna finns webbläsarnamnen och versionerna. Olika versioner av samma webbläsare är separata dimensionsobjekt.

Vissa dimensionsobjekt innehåller `"(unknown version)"` i stället för versionsnumret. Dimensionsobjektet refererar till en ny webbläsarversion som Adobe inte har lagt till i sina sökregister. Eftersom webbläsare uppdateras ofta är `"(unknown version)"` för en viss webbläsare vanlig och tillfällig. Adobe uppdaterar vanligtvis tabeller under månadsvisa underhållsutgåvor.
