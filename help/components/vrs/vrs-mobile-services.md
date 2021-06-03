---
description: Användargränssnittet för Adobe-mobiltjänster kombinerar mobilappsdata från Adobe Analytics rapporteringsprogram med möjligheten att skicka push-meddelanden och generera meddelanden i appen.
title: Stöd för VRS i Mobile Services
uuid: 1b11279e-d0d8-48c5-a5b5-8020d5ed39da
exl-id: 3082333a-514d-45c6-9432-da32bd27a2eb
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 6%

---

# Stöd för VRS i Mobile Services

Användargränssnittet för Adobe-mobiltjänster kombinerar mobilappsdata från Adobe Analytics rapporteringsprogram med möjligheten att skicka push-meddelanden och generera meddelanden i appen.

## Stöd för VRS i Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

Användargränssnittet för Adobe-mobiltjänster kombinerar mobilappsdata från Adobe Analytics rapporteringsprogram med möjligheten att skicka push-meddelanden och generera meddelanden i appen.

Adobe Mobile Services stöder virtuella rapportsviter. Om du tänker skapa en virtuell rapportsserie med flera program och du tänker utföra en meddelandeaktivitet, måste du ange det enskilda program-ID:t som en parameter. Om du skapar ett push-meddelande måste program-ID:t vara en av parametrarna för det segment som du använder. Om du skapar ett meddelande i appen måste program-ID:t vara en av parametrarna för de egenskaper som du anger för meddelandet. Om detta inte görs skickas/utlöses meddelandet till alla användare i alla appar som uppfyller villkoren för segment/utlösare.

Mer information finns i [Virtual Report Suites](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/c-mob-vrs.html) i dokumentationen för Adobe Mobile Services.
