---
title: Felsöka implementeringar av H-kod
description: Lär dig några vanliga problem med äldre JavaScript-implementeringar.
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Felsöka implementeringar av H-kod

Följande är felsökningssteg som är specifika för H-kodimplementeringar.

## Placera analyskoden i head-taggen

>[!NOTE]
>
>Medan H-kodimplementeringar kräver att kod refereras i `<body>` -taggen, andra implementeringar (till exempel att använda -taggar i Adobe Experience Platform) kräver att du refererar till kod i `<head>` -tagg.

Analyskoden skapar en osynlig 1x1-pixelbild. Tidigare var en vanlig implementeringspraxis att placera `s_code.js` i `<head>` -tagg. Om du placerar koden här förhindrar du att bilden påverkar sidlayouten på något sätt. Den körs också tidigare, vilket gör att du kan räkna sidvisningar för partiell sidinläsning mer effektivt.

Vissa element i koden kräver dock att det finns `<body>` -objekt. Om JavaScript-koden för Analytics finns i `<head>` -taggen körs den före `<body>` finns. Därför samlar implementeringen inte in [!UICONTROL ClickMap] data, automatisk spårning av filhämtningar eller avslutslänkar, eller anslutningstypdata. Skriptreferensen placeras på `s_code.js` i `<head>` -taggen fungerar, men resultatet är en mycket begränsad version av Analytics.

Analyskoden kan placeras var som helst inuti `<body>` -taggen för en välformaterad HTML-sida. Adobe rekommenderar att Analytics-koden placeras så nära överkanten av `<body>` tagga så mycket som möjligt. Se till att alla sidvariabler anges efter `s_code.js` filen läses in.

>[!TIP]
>
>Om du vill integrera Adobe Analytics med Adobe Target måste JavaScript-inkluderingsfilen placeras längst ned på sidan.
