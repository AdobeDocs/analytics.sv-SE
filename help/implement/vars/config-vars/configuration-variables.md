---
title: Konfigurationsvariabler
description: Använd konfigurationsvariabler för att avgöra hur data samlas in.
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 4%

---

# Översikt över konfigurationsvariabler

Konfigurationsvariabler styr hur data hämtas och bearbetas vid rapportering. De innehåller vanligtvis inte mått- eller måttvärden.

## Ställa in konfigurationsvariabler

I JavaScript-implementeringar som använder `AppMeasurement.js` ställs konfigurationsvariabler vanligtvis in överst i JS-filen.

I implementeringar som använder Adobe Experience Platform-taggar hittas vanligtvis konfigurationsvariabler genom att Adobe Analytics-tillägget konfigureras:

1. Gå till `experience.adobe.com` och logga in när du uppmanas till det.
1. Välj [!UICONTROL Launch / Data Collection].
1. Klicka på [!UICONTROL Go to Launch / Data Collection] och välj sedan [!UICONTROL Tags].
1. Klicka på den egenskap som du vill redigera.
1. Klicka på fliken [!UICONTROL Extensions] och sedan på [!UICONTROL Configure] under Adobe Analytics.

>[!IMPORTANT]
>
>Kontrollera att alla konfigurationsvariabler är angivna innan du anropar en spårningsmetod ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)). Undvik att ange konfigurationsvariabler i funktionen [`doPlugins()`](../functions/doplugins.md).
