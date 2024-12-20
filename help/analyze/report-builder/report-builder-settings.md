---
title: Konfigurera inställningar för Report Builder i Adobe Analytics
description: Beskriver hur du anger inställningar för offlineläge, språk, aktuellt läge och felsökning.
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
source-git-commit: ec14dde5b0e91a9fcfb217a811d36af2eea5f772
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Inställningar för Report Builder

Använd rutan **Inställningar** om du vill konfigurera programnivåinställningar, t.ex. det språk som visas i användargränssnittet eller om du vill arbeta i offlineläge eller inte. Inställningarna används omedelbart och ställs in för alla framtida sessioner tills de ändras.

Så här ändrar du inställningarna för Report Builder

1. Klicka på ikonen **Inställningar** .

1. Gör ändringar i Aktivera offlineläge, välj ett språk eller aktivera inställningarna för felsökningsloggen.

1. Klicka på **Använd**.

   Inställningar för ![Report Builder.](./assets/image38.png)

## Offline-läge

Data hämtas inte när du skapar och redigerar ett datablock i offlineläge. I stället används simuleringsdata så att du snabbt kan skapa och redigera ett datablock utan att vänta på att begäran ska köras. När du är online igen uppdaterar kommandot *Uppdatera datablock* eller *Uppdatera alla datablock* de datablock som du har skapat med aktuella data.

Aktivera offline-läge

1. Klicka på ikonen **[!UICONTROL Settings]**.

1. Välj **[!UICONTROL Enable off-line mod]e**.

1. Ange ett positivt heltal i fältet **[!UICONTROL Display metric data as]**.

1. Klicka på **[!UICONTROL Apply]**.

## Språk

Du kan välja språk för användargränssnittet i Report Builder. Alla Adobe Analytics-språk som stöds finns tillgängliga.

Välj det språk som ska användas i användargränssnittet i Report Builder

1. Klicka på Inställningar.

1. Välj ett språk i listrutan **[!UICONTROL Language]**.

   ![Datumintervallfönstret Report Builder visar språklistan med engelska markerat.](./assets/image39.png)

1. Klicka på **[!UICONTROL Apply].**

## Felsökning

Använd felsökningsinställningen för att logga alla klient-/serverdata till en lokal fil. Använd det här alternativet för att lösa supportärenden.

Om du vill aktivera felsökningsalternativet väljer du **[!UICONTROL Log report builder data block to web console]**.
