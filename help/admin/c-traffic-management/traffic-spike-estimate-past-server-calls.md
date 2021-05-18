---
description: Du kan få t.ex. förra årets dagliga serveranrop under en viss tidsperiod, plus en förväntad ökning av serversamtalsvolymen i år. Du kan sedan schemalägga en trafiktopp baserat på den här multiplikationsfaktorn.
title: Uppskatta tidigare serveranrop och schemalägg en trafiktopp
uuid: 38deb1df-afb0-437d-b541-69295f0dc8dc
exl-id: 1076ffbf-95a7-478c-a597-04bb3890e4a0
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 10%

---

# Uppskatta tidigare serveranrop och schemalägg en trafiktopp

Du kan få t.ex. förra årets dagliga serveranrop under en viss tidsperiod, plus en förväntad ökning av serversamtalsvolymen i år. Du kan sedan schemalägga en trafiktopp baserat på den här multiplikationsfaktorn.

1. Logga in på Analytics som administratör och gå till **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Traffic management]**.

1. Klicka på **[!UICONTROL Expand]** för att utöka rapportsvitlistan och klicka på **[!UICONTROL Select Report Suites]** för att välja flera rapportsviter.

1. Klicka på **[!UICONTROL Schedule Spikes]**.
1. Välj ett start- och slutdatum för de valda rapportsviterna under **[!UICONTROL Past Server Calls]**.

   Hur mycket serveranrop som går under högdager, toppdagars serversamtal och dagligt genomsnitt av serveranrop genereras.

1. Ange ett värde för multiplikationsfaktorn och klicka på **[!UICONTROL Click to multiply and set]**.

   Värdet för var och en av kolumnerna multipliceras för varje rapportserie.

1. Under **[!UICONTROL Set Spike Parameters]** skickar du toppparametrarna för de valda rapportsviterna.

   Spindeln är nu schemalagd för varje valt rapportpaket.

![](assets/past_server_calls.png)
