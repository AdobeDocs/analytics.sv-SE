---
title: PWA för analys
description: Progressiva webbappar för Adobe Analytics
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# PWA för analys

I den här guiden beskrivs hur du använder Adobe Analytics med progressiva webbappar (PWA).

## Introduktion

PWA-program kan tillhandahålla både en inbyggd appupplevelse och offlinefunktioner för en webbplats. Vanligtvis innehåller PWA en servicearbetare, cachelagring och en manifestfil, som alla kan hjälpa till med snabbare inläsningstider, enklare navigering och responsivt beteende.

Adobe Analytics fungerar lika smidigt med PWA som med traditionella webbplatser. Även om PWA-program har några fler krav på att fungera progressivt i sig själva skapar de inga hinder eller begränsningar för hur Analytics samlar in eller rapporterar data från dem på något annat sätt än traditionella webbplatser. Eftersom Analytics redan har funktioner för offlinespårning kan PWA-program hjälpa er att utnyttja den inbyggda funktionen enklare än med traditionella webbplatser.

## Hämta PWA Analytics-data

Om du vill samla in och analysera dina PWA-data med Analytics behöver du inte göra några konfigurationsändringar. Analytics ger automatiskt samma funktionalitet och funktioner som en traditionell webbplats.

## Lägg in spårning offline för att öka effektiviteten i PWA

Ni kan öka effektiviteten i era PWA-avtal genom att använda Analytics [offline-spårningsfunktioner](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) tillsammans med dem. Som standard är den här funktionen inaktiverad, men du kan lägga till följande egenskap i filen AppMeasurement.js för att aktivera den: `s.trackOffline=true;`.

I följande AppMeasurement.js-fil läggs egenskapen till i slutet av `CONFIG SECTION`:

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.trackOffline=true
***
    
```


Mer information om hur du redigerar filen AppMeasurement.js finns i [Infoga kod i filen](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)AppMeasurement.js.

Exempel på konfigurationer i filen AppMeasurement.js finns i [Konfigurera filen](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)AppMeasurement.js.

Mer information om egenskaperna för filen AppMeasurement.js finns i [JavaScript-implementeringsöversikten](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).
