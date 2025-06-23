---
title: Konfigurationsvariabler
description: Använd konfigurationsvariabler för att avgöra hur data samlas in.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 0%

---

# Översikt över konfigurationsvariabler

Konfigurationsvariabler styr hur data hämtas och bearbetas vid rapportering. De innehåller vanligtvis inte mått- eller måttvärden.

## Ställa in konfigurationsvariabler

I implementeringar som använder Web SDK-tillägget eller Analytics-tillägget finns vanligtvis konfigurationsvariabler i tilläggets inställningar:

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Klicka på fliken [!UICONTROL Extensions] och sedan på [!UICONTROL Configure] under tillägget.

I JavaScript-implementeringar där `AppMeasurement.js` används ställs konfigurationsvariabler vanligtvis in överst i JS-filen.

>[!IMPORTANT]
>
>Kontrollera att alla konfigurationsvariabler har angetts innan du anropar en spårningsmetod ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)). Undvik att ange konfigurationsvariabler i funktionen [`doPlugins()`](../functions/doplugins.md).
