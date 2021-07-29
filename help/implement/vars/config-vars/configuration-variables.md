---
title: Konfigurationsvariabler
description: Använd konfigurationsvariabler för att avgöra hur data samlas in.
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 4%

---

# Översikt över konfigurationsvariabler

Konfigurationsvariabler styr hur data hämtas och bearbetas vid rapportering. De innehåller vanligtvis inte mått- eller måttvärden.

## Ställa in konfigurationsvariabler

I JavaScript-implementeringar som använder `AppMeasurement.js` ställs konfigurationsvariabler vanligtvis in överst i JS-filen.

I implementeringar som använder Adobe Experience Platform-taggar hittas vanligtvis konfigurationsvariabler genom att Adobe Analytics-tillägget konfigureras:

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på den egenskap som du vill redigera.
1. Klicka på fliken [!UICONTROL Extensions] och sedan på [!UICONTROL Configure] under Adobe Analytics.

>[!IMPORTANT]
>
>Kontrollera att alla konfigurationsvariabler är angivna innan du anropar en spårningsmetod ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)). Undvik att ange konfigurationsvariabler i funktionen [`doPlugins()`](../functions/doplugins.md).
