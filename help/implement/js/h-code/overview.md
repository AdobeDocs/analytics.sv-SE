---
title: H Code JavaScript implementation overview
description: Lär dig arbetsflödet för att implementera H-kod på din webbplats.
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# H Code JavaScript implementation overview

>[!IMPORTANT]
>
>Den här versionen av datainsamling stöds inte längre. Uppgradera till [taggar i Adobe Experience Platform](../../launch/overview.md) eller [AppMeasurement for JavaScript](../overview.md).

Du måste ha tillgång till värdservrarna för att kunna implementera en sida med kod för att samla in data. Följande steg visar dig vägen genom en grundläggande H-kodimplementering i Analytics.

>[!NOTE]
>
>Du måste ha en befintlig kopia av `s_code.js` för att kunna följa dessa instruktioner. Adobe erbjuder inte längre något alternativ för att hämta H-kod i Code Manager.

1. **Uppdatera grundläggande JS-filvariabler**: Redigera  `s_code.js` filen och kontrollera att följande variabler är uppdaterade:
   * `s_account` innehåller det rapportsvit-ID som du vill skicka data till. Se
   * `s.trackingServer` innehåller de platscookies som lagras. Se [trackingServer](../../vars/config-vars/trackingserver.md).
1. **Lägg  `s_code.js` filen på din plats**: Den här filen finns vanligtvis tillsammans med andra skript på webbservern.
1. **Referens  `s_code.js` på alla sidor**: Se till att alla enskilda sidor anropar JavaScript-huvudfilen och gör det i HTML- `<body>` taggen (inte  `<head>` taggen).

   >[!TIP]
   >
   >H-koden kräver att skriptet `s_code.js` anropas i taggen `<body>`. Detta skiljer sig från andra implementeringsmetoder, varav de flesta kräver skriptreferenser i taggen `<head>`.
1. **Definiera sidspecifika variabler på varje sida**: Varje sida ska ha individuella variabler definierade, till exempel sidnamn eller eVars. Enskilda variabler definieras vanligtvis med en infogad `<script>`-tagg på varje sida.
1. **Använd felsökaren för att verifiera datainsamling**: Hämta och installera  [Experience Cloud-](../../validate/debugger.md) felsökaren för att se till att data skickas till Adobe och att sidvariabler definieras korrekt.

## Cachelagring

JavaScript-filen cachelagras i besökarens webbläsare efter att den först lästs in och hämtas vanligtvis inte mer än en gång per session. Filen hämtas inte till varje sida, även om den används av alla sidor på webbplatsen. På de flesta webbplatser använder användarna i genomsnitt mer än ett fåtal sidvisningar per session, så om JavaScript överförs flera gånger till den här filen kan det leda till mindre totala nedladdade data.

## H-kodkomprimering

Om du är orolig för nedladdningsstorleken för `s_code.js`-filen rekommenderar Adobe att du komprimerar `s_code.js`-filen med GZIP. GZIP stöds av alla större webbläsare och ger bättre prestanda än JavaScript-komprimering. Se [Apache Module mod_deflate](https://httpd.apache.org/docs/current/mod/mod_deflate.html) i dokumentationen för Apache.
