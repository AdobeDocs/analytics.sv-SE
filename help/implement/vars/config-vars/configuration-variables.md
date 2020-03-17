---
title: Konfigurationsvariabler
description: Använd konfigurationsvariabler för att avgöra hur data samlas in.
translation-type: tm+mt
source-git-commit: e9a876a1f562333056387d63de46a9cfe3fb3939

---


# Översikt över konfigurationsvariabler

Konfigurationsvariabler styr hur data hämtas och bearbetas vid rapportering. De innehåller vanligtvis inte mått- eller måttvärden.

## Ställa in konfigurationsvariabler

I JavaScript-implementeringar med `AppMeasurement.js`ställs konfigurationsvariabler vanligtvis in överst i JS-filen.

I implementeringar som använder Adobe Experience Platform Launch hittas vanligtvis konfigurationsvariabler genom att Adobe Analytics-tillägget konfigureras:

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
2. Klicka på den egenskap som du vill redigera.
3. Klicka på [!UICONTROL Extensions] fliken och sedan på [!UICONTROL Configure] under Adobe Analytics.

> [!IMPORTANT] Kontrollera att alla konfigurationsvariabler är angivna innan du anropar en spårfunktion (`t()` eller `tl()`). Undvik att ange konfigurationsvariabler i `doPlugins()` funktionen.
