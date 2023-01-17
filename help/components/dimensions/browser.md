---
title: Webbläsare
description: Namnet på och versionen av den webbläsare som används.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 39f1ac66fb6374c62f790f9a38a52fba3bf9bda1
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Webbläsare

The[!UICONTROL Browser]&#39; anger namnet och versionen på den webbläsare som skickade träffen. Den här dimensionen är användbar för att förstå de vanligaste webbläsarna besökarna använder. När du testar nya versioner av din webbplats kan du köra testerna i de vanligaste webbläsarna i den här dimensionen för att maximera kvalitetskontrollen.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på `User-Agent` HTTP-huvud i bildbegäranden. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt.

## Dimensioner

Bland Dimensionerna finns webbläsarnamnen och versionerna. Olika versioner av samma webbläsare är separata dimensionsobjekt.

Vissa dimensionsobjekt innehåller `"(unknown version)"` i stället för versionsnumret. Dimensionsobjektet refererar till en ny webbläsarversion som Adobe inte har lagt till i sina sökregister. Eftersom webbläsarna uppdateras ofta visas `"(unknown version)"` för en viss webbläsare är vanlig och tillfällig. Adobe uppdaterar vanligtvis tabeller under månadsvisa underhållsutgåvor.

## Förändringar i märkning och definition

Nedan visas en lista över ändringar av hur webbläsare visas i rapporter. Dessa ändringar kan påverka din rapportering eller någon logik, t.ex. segment, som är beroende av dessa värden.

### Tar bort företag från webbläsaren

Från och med version 100 för webbläsarna Chrome, Edge och Firefox visas inte längre företagsnamnet före webbläsaren. Detta kan påverka användare om de har segmentdefinitioner som baseras på webbläsarens namn. Ett segment som innehåller en definition som&quot;webbläsaren innehåller&quot;Google&quot; kommer till exempel inte längre att identifiera Chrome-webbläsare som börjar med version 110.

Exempel:

Version 109 av Chrome visas som&quot;Google Chrome 109&quot;.
Version 110 av Chrome visas som&quot;Chrome 109&quot;.

### Ta bort skillnaden mellan mobil och icke-mobil för Chrome

Från och med Chrome 110 kommer både mobilversioner och icke-mobilversioner av Chrome att märkas på samma sätt. För närvarande är mobilversioner och andra versioner separat märkta. Viktigt är att detta ändrar innebörden av namnet utan&quot;mobil&quot;. &quot;Chrome 109&quot; är inte mobilt (dvs. stationär dator) &quot;Chrome 110&quot; är mobilt och inte mobilt. Om du har segmentdefinitioner som refererar till&quot;mobile&quot; i webbläsarnamnet kanske dessa inte längre fungerar som förväntat. Du kan använda mobilsegmentering och uppdelningar för att jämföra mobiltrafik med icke-mobiltrafik.

Exempel:

Mobile Chrome 109 visas som Chrome Mobile 109.
Krom 109 som inte är mobil visas som Chrome 109.

Mobile Chrome 110 visas som Chrome 110.
Krom 110 som inte är mobil visas som Chrome 110.
