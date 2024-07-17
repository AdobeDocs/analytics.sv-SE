---
title: H Code JavaScript - implementeringsöversikt
description: Lär dig arbetsflödet för att implementera H-kod på din webbplats.
feature: Implementation Basics
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 0%

---

# H Code JavaScript - implementeringsöversikt

>[!IMPORTANT]
>
>Den här versionen av datainsamling stöds inte längre. Uppgradera till [taggar i Adobe Experience Platform](../../launch/overview.md) eller [AppMeasurement för JavaScript](../overview.md).

Du måste ha tillgång till värdservrarna för att kunna implementera en sida med kod för att samla in data. Följande steg visar dig vägen genom en grundläggande H-kodimplementering i Analytics.

>[!NOTE]
>
>Du måste redan ha en befintlig kopia av `s_code.js` för att kunna följa dessa instruktioner. Adobe erbjuder inte längre något alternativ för att hämta H-kod i Code Manager.

1. **Uppdatera grundläggande JS-filvariabler**: Redigera `s_code.js`-filen och se till att följande variabler uppdateras:
   * `s_account` innehåller det rapportsviter-ID som du vill skicka data till. Se
   * `s.trackingServer` innehåller de platscookies som lagras. Se [trackingServer](../../vars/config-vars/trackingserver.md).
1. **Använd `s_code.js` som värd för filen på din plats**: Den här filen finns vanligtvis tillsammans med andra skript på webbservern.
1. **Referens `s_code.js` på alla sidor**: Se till att alla enskilda sidor anropar JavaScript-huvudfilen och gör det i HTML-taggen `<body>` (inte `<head>` -taggen).

   >[!TIP]
   >
   >H-koden kräver att skriptet `s_code.js` anropas i taggen `<body>`. Detta skiljer sig från andra implementeringsmetoder, varav de flesta kräver skriptreferenser i taggen `<head>`.
1. **Definiera sidspecifika variabler på varje sida**: Varje sida ska ha individuella variabler definierade, till exempel sidnamn eller eVars. Enskilda variabler definieras vanligtvis med en intern `<script>`-tagg på varje sida.
1. **Använd felsökaren för att verifiera datainsamling**: Hämta och installera [Experience Cloud-felsökaren](../../validate/debugger.md) för att se till att data skickas till Adobe och att sidvariabler är korrekt definierade.

## Cachning

JavaScript-filen cachelagras i besökarens webbläsare när den först lästs in och hämtas vanligtvis inte mer än en gång per session. Filen hämtas inte till varje sida, även om den används av alla sidor på webbplatsen. På de flesta webbplatser använder man i genomsnitt mer än ett fåtal sidvisningar per session, så om man överför JavaScript som används flera gånger till den här filen kan det leda till mindre totala nedladdade data.

## H-kodkomprimering

Om du är orolig för hämtningsstorleken för filen `s_code.js` rekommenderar Adobe att du komprimerar filen `s_code.js` med GZIP. GZIP stöds av alla större webbläsare och ger bättre prestanda än JavaScript-komprimering. Se [Apache Module mod_deflate](https://httpd.apache.org/docs/current/mod/mod_deflate.html) i dokumentationen för Apache.
