---
title: Konfigurationsvariabler
description: Använd konfigurationsvariabler för att avgöra hur data samlas in.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 0%

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
>Kontrollera att alla konfigurationsvariabler är angivna innan du anropar en spårningsmetod ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)). Undvik att ange konfigurationsvariabler i [`doPlugins()`](../functions/doplugins.md) funktion.
