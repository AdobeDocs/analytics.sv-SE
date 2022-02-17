---
title: Konfigurationsvariabler
description: Använd konfigurationsvariabler för att avgöra hur data samlas in.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 4%

---

# Översikt över konfigurationsvariabler

Konfigurationsvariabler styr hur data hämtas och bearbetas vid rapportering. De innehåller vanligtvis inte mått- eller måttvärden.

## Ställa in konfigurationsvariabler

I JavaScript-implementeringar med `AppMeasurement.js`, ställs konfigurationsvariabler vanligtvis in överst i JS-filen.

I implementeringar som använder Adobe Experience Platform-taggar hittas vanligtvis konfigurationsvariabler genom att Adobe Analytics-tillägget konfigureras:

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den egenskap som du vill redigera.
1. Klicka på [!UICONTROL Extensions] -flik och sedan klicka [!UICONTROL Configure] under Adobe Analytics.

>[!IMPORTANT]
>
>Kontrollera att alla konfigurationsvariabler har angetts innan du anropar en spårningsmetod ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)). Undvik att ange konfigurationsvariabler i [`doPlugins()`](../functions/doplugins.md) funktion.
