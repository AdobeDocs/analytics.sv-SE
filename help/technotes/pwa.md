---
title: PWA for Analytics
description: Progressiva webbprogram för Adobe Analytics
role: User, Admin
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
source-git-commit: a9d892ab8caaeb797fbbd9b5aa136c5dab76f8bd
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---

# PWA för Adobe Analytics

På den här sidan beskrivs hur du använder Adobe Analytics med progressiva webbappar (PWA).

## Introduktion

PWA kan tillhandahålla både en inbyggd appupplevelse och offlinefunktioner för en webbplats. Vanligtvis innehåller PWA en servicearbetare, cachelagring och en manifestfil som kan hjälpa till med snabbare inläsningstider, enklare navigering och responsiva beteenden.

Adobe Analytics fungerar lika smidigt med PWA som med traditionella webbplatser. Även om PWA har några fler krav på att agera progressivt i och för sig själva skapar de inga hinder eller begränsningar för hur Analytics samlar in eller rapporterar data från dem på något annat sätt än traditionella webbplatser. Eftersom Analytics redan har funktioner för offlinespårning kan PWA hjälpa er att utnyttja den här inbyggda funktionen enklare än med traditionella webbplatser.

## Hämta data från PWA Analytics

Om du vill samla in och analysera dina PWA-data med [!UICONTROL Analytics] behöver du inte göra några konfigurationsändringar. [!UICONTROL Analytics] har automatiskt samma funktioner och funktioner som en traditionell webbplats.

## Lägg till offline-spårning för att öka effektiviteten i PWA

Du kan öka effektiviteten för PWA genom att använda Adobe Analytics [offlinespårningsfunktioner](/help/implement/vars/config-vars/trackoffline.md). Som standard är den här funktionen inaktiverad, men du kan lägga till följande egenskap i filen AppMeasurement.js för att aktivera den: `s.trackOffline=true;`.

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

Mer information om hur du konfigurerar filen AppMeasurement.js finns i [Översikt över konfigurationsvariabler](/help/implement/vars/config-vars/configuration-variables.md) och de enskilda variabelspecifika sidorna i samma underkapitel.

Mer information om egenskaperna för filen AppMeasurement.js finns i [Översikt över JavaScript-implementering](/help/implement/js/overview.md).
