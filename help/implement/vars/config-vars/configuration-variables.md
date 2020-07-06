---
title: Konfigurationsvariabler
description: Använd konfigurationsvariabler för att avgöra hur data samlas in.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 5%

---


# Översikt över konfigurationsvariabler

Konfigurationsvariabler styr hur data hämtas och bearbetas vid rapportering. De innehåller vanligtvis inte mått- eller måttvärden.

## Ställa in konfigurationsvariabler

I JavaScript-implementeringar med `AppMeasurement.js`ställs konfigurationsvariabler vanligtvis in överst i JS-filen.

I implementeringar som använder Adobe Experience Platform Launch hittas vanligtvis konfigurationsvariabler genom att Adobe Analytics-tillägget konfigureras:

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. Klicka på den egenskap som du vill redigera.
3. Klicka på [!UICONTROL Extensions] fliken och sedan på [!UICONTROL Configure] under Adobe Analytics.

>[!IMPORTANT]
>
>Kontrollera att alla konfigurationsvariabler är angivna innan du anropar en spårningsmetod ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)). Undvik att ange konfigurationsvariabler i [`doPlugins()`](../functions/doplugins.md) funktionen.
