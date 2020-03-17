---
title: H Code JavaScript implementation overview
description: Lär dig arbetsflödet för att implementera H-kod på din webbplats.
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# H Code JavaScript implementation overview

> [!IMPORTANT] Den här versionen av datainsamling stöds inte längre. Uppgradera till [Adobe Experience Platform Launch](../../launch/overview.md) eller [AppMeasurement for JavaScript](../overview.md).

Du måste ha tillgång till värdservrarna för att kunna implementera en sida med kod för att samla in data. Följande steg visar dig vägen genom en grundläggande H-kodimplementering i Analytics.

> [!NOTE] Du måste ha en befintlig kopia av `s_code.js` för att kunna följa dessa instruktioner. Adobe erbjuder inte längre något alternativ för att hämta H-kod i Code Manager.

1. **Uppdatera grundläggande JS-filvariabler**: Redigera `s_code.js` filen och kontrollera att följande variabler är uppdaterade:
   * `s_account` innehåller det rapportsvit-ID som du vill skicka data till. Se
   * `s.trackingServer` innehåller de platscookies som lagras. Se [trackingServer](../../vars/config-vars/trackingserver.md).
2. **Lägg`s_code.js`filen på din plats** som värd: Den här filen finns vanligtvis tillsammans med andra skript på webbservern.
3. **Referens`s_code.js`på alla sidor**: Se till att alla enskilda sidor anropar JavaScript-huvudfilen och gör det i HTML- `<body>` taggen (inte `<head>` -taggen).
   > [!TIP] H-koden kräver att `s_code.js` skriptet anropas inom `<body>` -taggen. Detta skiljer sig från andra implementeringsmetoder, varav de flesta kräver skriptreferenser i `<head>` -taggen.
4. **Definiera sidspecifika variabler på varje sida**: Varje sida ska ha individuella variabler definierade, till exempel sidnamn eller eVars. Enskilda variabler definieras vanligtvis med en intern `<script>` tagg på varje sida.
5. **Använd felsökaren för att verifiera datainsamling**: Hämta och installera [Experience Cloud-felsökaren](../../validate/debugger.md) för att se till att data skickas till Adobe och att sidvariabler definieras korrekt.

## Cachelagring

JavaScript-filen cachelagras i besökarens webbläsare efter att den först lästs in och hämtas vanligtvis inte mer än en gång per session. Filen hämtas inte till varje sida, även om den används av alla sidor på webbplatsen. På de flesta webbplatser använder användarna i genomsnitt mer än ett fåtal sidvisningar per session, så om JavaScript överförs flera gånger till den här filen kan det leda till mindre totala nedladdade data.

## H-kodkomprimering

Om du är orolig för nedladdningsstorleken på `s_code.js` filen rekommenderar Adobe att du komprimerar `s_code.js` filen med GZIP. GZIP stöds av alla större webbläsare och ger bättre prestanda än JavaScript-komprimering. Se [Apache Module mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) i dokumentationen för Apache.
