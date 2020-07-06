---
title: Felsöka implementeringar av H-kod
description: Lär dig några vanliga problem med äldre JavaScript-implementeringar.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---


# Felsöka implementeringar av H-kod

Följande är felsökningssteg som är specifika för H-kodimplementeringar.

## Placera Analytics-kod i head-taggen

>[!NOTE]
>
>Det krävs referenser till kod för H-kodimplementeringar i `<body>` -taggen, men andra implementeringar (som att använda Adobe Experience Platform Launch) kräver att det finns en referens till kod i `<head>` -taggen.

Analytics-kod skapar en osynlig 1x1-pixelbild. Tidigare var en vanlig implementeringspraxis att placera `s_code.js` referensen i `<head>` -taggen. Om du placerar koden här förhindrar du att bilden påverkar sidlayouten på något sätt. Den körs också tidigare, vilket gör att du kan räkna sidvisningar för partiell sidinläsning mer effektivt.

Vissa element i koden kräver dock att `<body>` objektet finns. Om Analytics JavaScript-koden finns i `<head>` -taggen körs den innan `<body>` objektet finns. Detta innebär att implementeringen inte samlar in [!UICONTROL ClickMap] data, automatisk spårning av filhämtningar eller avslutslänkar eller data för anslutningstyp. Det går att placera skriptreferensen `s_code.js` i `<head>` -taggen, men resultatet är en mycket begränsad version av Analytics.

Analytics-koden kan placeras var som helst inuti taggen för en välformaterad HTML-sida. `<body>` Adobe rekommenderar att du placerar Analytics-koden så nära taggens överkant som möjligt. `<body>` Kontrollera att sidvariablerna har angetts när `s_code.js` filen har lästs in.

>[!TIP]
>
>Om du vill integrera Adobe Analytics med Adobe Target måste JavaScript-inkluderingsfilen placeras längst ned på sidan.
