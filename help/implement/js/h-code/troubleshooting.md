---
title: Felsöka implementeringar av H-kod
description: Lär dig några vanliga problem med äldre JavaScript-implementeringar.
translation-type: tm+mt
source-git-commit: 69138bdedb42b66449426fee39822520ee4b1198

---


# Felsöka implementeringar av H-kod

Följande är felsökningssteg som är specifika för H-kodimplementeringar.

## Placera analyskoden i head-taggen

> [!NOTE] Det krävs referenser till kod för H-kodimplementeringar i taggen, men andra implementeringar (som att använda Adobe Experience Platform Launch) kräver att du refererar till kod i `<body>` `<head>` -taggen.

Analyskoden skapar en osynlig 1x1-pixelbild. Tidigare var en vanlig implementeringspraxis att placera `s_code.js` referensen i `<head>` -taggen. Om du placerar koden här förhindrar du att bilden påverkar sidlayouten på något sätt. Den körs också tidigare, vilket gör att du kan räkna sidvisningar för partiell sidinläsning mer effektivt.

Vissa element i koden kräver dock att `<body>` objektet finns. Om JavaScript-koden för Analytics finns i `<head>` -taggen körs den innan `<body>` objektet finns. Detta innebär att implementeringen inte samlar in [!UICONTROL ClickMap] data, automatisk spårning av filhämtningar eller avslutslänkar eller data för anslutningstyp. Det går att placera skriptreferensen `s_code.js` i `<head>` -taggen, men resultatet är en mycket begränsad version av Analytics.

Analyskoden kan placeras var som helst inuti taggen `<body>` för en välformaterad HTML-sida. Adobe rekommenderar att Analytics-koden placeras så nära taggens överkant som möjligt `<body>` . Kontrollera att sidvariablerna har angetts när `s_code.js` filen har lästs in.

> [!TIP] Om du vill integrera Adobe Analytics med Adobe Target måste JavaScript-inkluderingsfilen placeras längst ned på sidan.
