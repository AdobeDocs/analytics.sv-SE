---
title: Skicka data till Adobe Analytics med JavaScript-biblioteket för Web SDK
description: Börja med en ren Web SDK-implementering för att skicka data till Adobe Analytics med hjälp av JavaScript-biblioteket.
hide: true
hidefromtoc: true
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# Skicka data till Adobe Analytics med JavaScript-biblioteket för Web SDK

Den här implementeringssökvägen innebär en ny Web SDK-installation med JavaScript-biblioteket för Web SDK. Andra implementeringsvägar beskrivs på separata sidor:

* [SDK-taggtillägg för webben](web-sdk-tag-extension.md): En ny installation av Web SDK med tillägget Web SDK. Liknar Web SDK JavaScript-biblioteket (den här sidan), förutom att du hanterar implementeringen med hjälp av taggar i Adobe Experience Platform Data Collection. Det kräver fältgruppen Adobe Analytics ExperienceEvent, som innehåller typiska analysvariabler som ska inkluderas i XDM-schemat.
* [Analystillägg till Web SDK-tillägg](analytics-extension-to-web-sdk.md): Ta ett smidigt och metodiskt tillvägagångssätt för att gå från taggtillägget Adobe Analytics till taggtillägget Web SDK. På så sätt slipper du använda XDM tills din organisation är redo att använda Adobe Experience Platform-tjänster, till exempel Customer Journey Analytics. Använd `data` i stället för `xdm` objekt som data ska skickas till Adobe.
* [AppMeasurement till Web SDK JavaScript-bibliotek](appmeasurement-to-web-sdk.md): Ett smidigt och metodiskt sätt att migrera till Web SDK, förutom att taggar inte används. I stället kan du ta bort Adobe Analytics datainsamlingsbibliotek manuellt (`AppMeasurement.js`) och ersätta det med JavaScript-biblioteket för Web SDK (`alloy.js`).

## Fördelar och nackdelar med implementeringsvägen

Att använda JavaScript-biblioteket Web SDK för att skicka data till Adobe Analytics har både fördelar och nackdelar. Väg noga in varje alternativ för att avgöra vilken metod som är bäst för er organisation.

| Fördelar | Nackdelar |
| --- | --- |
| <ul><li>**Direkt metod**: Den här implementeringsvägen är enklare än strategier som flyttar befintliga Adobe Analytics-implementeringar. Om du inte har någon Adobe Analytics-implementering att tänka på fyller du i de tillämpliga Web SDK XDM-fälten.</li><li>**Fördefinierat schema**: Om din organisation inte behöver ett eget schema kan du helt enkelt använda det schema som är avsett för Adobe Analytics. Det här konceptet gäller även när du går mot Customer Journey Analytics; konceptet med props och eVars gäller inte Customer Journey Analytics, men du kan fortsätta använda props och eVars som enkla anpassade dimensioner.</li></ul> | <ul><li>**Implementeringsändringar kräver åtgärd från utvecklaren**: Om du vill göra ändringar i Web SDK-implementeringen måste du samarbeta med ditt utvecklingsteam för att redigera koden på din webbplats. Metoden som använder [SDK-taggtillägg för webben](web-sdk-tag-extension.md) undviker denna nackdel.</li><li>**Låst till att använda ett specifikt schema**: När din organisation flyttar till Customer Journey Analytics måste du välja att fortsätta använda Adobe Analytics-schemat eller migrera till din egen organisations schema (som skulle vara en separat datauppsättning). Om din organisation vill undvika både Adobe Analytics-schemat och migrering till en separat datauppsättning när den flyttar till Customer Journey Analytics rekommenderar Adobe en av följande två metoder:</li><ul><li>Använd `data` objekt: `data` kan du skicka data till Adobe Analytics utan att följa ett XDM-schema. När din organisations schema har skapats kan du mappa dataStream-mappningen `data` till XDM. Båda [Analystillägg till Web SDK-tillägg](analytics-extension-to-web-sdk.md) och [AppMeasurement till Web SDK JavaScript-bibliotek](appmeasurement-to-web-sdk.md) använd denna `data` -objekt.</li><li>Hoppa över Adobe Analytics helt: Om du implementerar Web SDK kan du skicka dessa data till en datauppsättning i Adobe Experience Platform för användning i Customer Journey Analytics. Du kan använda vilket schema som helst. Adobe Analytics är inte involverat alls i det här arbetsflödet och därför krävs inte fältgruppen Adobe Analytics ExperienceEvent. Den här metoden medför minst teknisk skuld, men lämnar också Adobe Analytics helt utanför bilden.</li></ul></ul> |
