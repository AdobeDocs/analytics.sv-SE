---
description: Användargränssnittet för Adobes mobiltjänster kombinerar mobilappsdata från Adobe Analytics-rapportsviterna med möjligheten att skicka push-meddelanden och generera meddelanden i appen.
title: Stöd för VRS i mobiltjänster
uuid: 1b11279e-d0d8-48c5-a5b5-8020d5ed39da
translation-type: tm+mt
source-git-commit: 9193a520b13a0717a3383a32b39936f278c49d49

---


# Stöd för VRS i mobiltjänster

Användargränssnittet för Adobes mobiltjänster kombinerar mobilappsdata från Adobe Analytics-rapportsviterna med möjligheten att skicka push-meddelanden och generera meddelanden i appen.

## Stöd för VRS i mobiltjänster {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

Användargränssnittet för Adobes mobiltjänster kombinerar mobilappsdata från Adobe Analytics-rapportsviterna med möjligheten att skicka push-meddelanden och generera meddelanden i appen.

Adobe Mobile Services stöder virtuella rapportsviter. Om du tänker skapa en virtuell rapportsserie med flera program och du tänker utföra en meddelandeaktivitet, måste du ange det enskilda program-ID:t som en parameter. Om du skapar ett push-meddelande måste program-ID:t vara en av parametrarna för det segment som du använder. Om du skapar ett meddelande i appen måste program-ID:t vara en av parametrarna för de egenskaper som du anger för meddelandet. Om detta inte görs skickas/utlöses meddelandet till alla användare i alla appar som uppfyller villkoren för segment/utlösare.

Mer information finns i [Virtuella rapportsviter](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/c-mob-vrs.html) i dokumentationen för Adobe Mobile Services.
