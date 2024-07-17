---
title: Felsöka implementeringar av H-kod
description: Lär dig några vanliga problem med tidigare JavaScript-implementeringar.
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Felsöka implementeringar av H-kod

Följande är felsökningssteg som är specifika för H-kodimplementeringar.

## Placera analyskoden i head-taggen

>[!NOTE]
>
>H-kodimplementeringar kräver att kod refereras i taggen `<body>`, men andra implementeringar (till exempel att använda taggar i Adobe Experience Platform) kräver att kod refereras i taggen `<head>`.

Analyskoden skapar en osynlig 1x1-pixelbild. Tidigare var en vanlig implementeringspraxis att placera referensen `s_code.js` i taggen `<head>`. Om du placerar koden här förhindrar du att bilden påverkar sidlayouten på något sätt. Den körs också tidigare, vilket gör att du kan räkna sidvisningar för partiell sidinläsning mer effektivt.

Vissa element i koden kräver dock att objektet `<body>` finns. Om Analytics JavaScript-koden finns i `<head>`-taggen körs den innan `<body>`-objektet finns. Därför samlar din implementering inte in [!UICONTROL ClickMap]-data, automatisk spårning av filhämtningar eller avslutslänkar eller anslutningstypdata. Det går att placera skriptreferensen på `s_code.js` i taggen `<head>`, men resultatet är en mycket begränsad version av Analytics.

Analyskoden kan placeras var som helst inuti taggen `<body>` på en välformaterad HTML-sida. Adobe rekommenderar att Analytics-koden placeras så nära överkanten av `<body>`-taggen som möjligt. Kontrollera att alla sidvariabler har angetts efter att filen `s_code.js` har lästs in.

>[!TIP]
>
>Om du vill integrera Adobe Analytics med Adobe Target måste JavaScript inkluderingsfil placeras längst ned på sidan.
