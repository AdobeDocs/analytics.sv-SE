---
title: Konfigurationsvariabler
description: Använd konfigurationsvariabler för att avgöra hur data samlas in.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 4%

---

# Översikt över konfigurationsvariabler

Konfigurationsvariabler styr hur data hämtas och bearbetas vid rapportering. De innehåller vanligtvis inte mått- eller måttvärden.

## Ställa in konfigurationsvariabler

I implementeringar som använder Web SDK-tillägget eller Analytics-tillägget finns vanligtvis konfigurationsvariabler i tilläggets inställningar:

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Klicka på [!UICONTROL Extensions] -flik och sedan klicka [!UICONTROL Configure] under förlängningen.

I JavaScript-implementeringar med `AppMeasurement.js`, ställs konfigurationsvariabler vanligtvis in överst i JS-filen.

>[!IMPORTANT]
>
>Kontrollera att alla konfigurationsvariabler har angetts innan du anropar en spårningsmetod ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)). Undvik att ange konfigurationsvariabler i [`doPlugins()`](../functions/doplugins.md) funktion.
