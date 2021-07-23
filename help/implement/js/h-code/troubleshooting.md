---
title: Felsöka implementeringar av H-kod
description: Lär dig några vanliga problem med äldre JavaScript-implementeringar.
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Felsöka implementeringar av H-kod

Följande är felsökningssteg som är specifika för H-kodimplementeringar.

## Placera analyskoden i head-taggen

>[!NOTE]
>
>Det krävs referenser till kod för H-kodimplementeringar i taggen `<body>`, men andra implementeringar (som att använda taggar i Adobe Experience Platform) kräver att du refererar till kod i taggen `<head>`.

Analyskoden skapar en osynlig 1x1-pixelbild. Tidigare var en vanlig implementeringspraxis att placera referensen `s_code.js` i taggen `<head>`. Om du placerar koden här förhindrar du att bilden påverkar sidlayouten på något sätt. Den körs också tidigare, vilket gör att du kan räkna sidvisningar för partiell sidinläsning mer effektivt.

Vissa element i koden kräver att `<body>`-objektet finns. Om JavaScript-koden för Analytics finns i `<head>`-taggen körs den innan `<body>`-objektet finns. Därför samlar implementeringen inte in [!UICONTROL ClickMap]-data, automatisk spårning av filhämtningar eller avslutslänkar eller anslutningstypdata. Det går att placera skriptreferensen på `s_code.js` i taggen `<head>`, men resultatet är en mycket begränsad version av Analytics.

Analyskoden kan placeras var som helst inuti taggen `<body>` för en välformaterad HTML-sida. Adobe rekommenderar att Analytics-koden placeras så nära överkanten av `<body>`-taggen som möjligt. Kontrollera att alla sidvariabler har angetts efter att `s_code.js`-filen har lästs in.

>[!TIP]
>
>Om du vill integrera Adobe Analytics med Adobe Target måste JavaScript-inkluderingsfilen placeras längst ned på sidan.
