---
title: Konfigurera inställningar för Report Builder
description: Lär dig konfigurera inställningar för Report Builder.
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---

# Report Builder-inställningar


Använd rutan **Inställningar** om du vill konfigurera programnivåinställningar, t.ex. det språk som visas i användargränssnittet eller om du vill arbeta i offlineläge eller inte. Inställningarna används omedelbart och ställs in för alla framtida sessioner tills de ändras.

Så här ändrar du Report Builder-inställningar

1. Välj ikonen **Inställningar** .

1. Gör ändringar i [aktivera inaktiverat offlineläge](#off-line-mode), [välj ett språk](#language) eller [aktivera felsökning](#troubleshooting).

1. Välj **[!UICONTROL Apply]**.

   ![Report Builder datumintervallfönster med knappen Avbryt och använd.](./assets/report-builder-settings.png){zoomable="yes"}

## Offline-läge

När du skapar och redigerar ett datablock i offlineläge hämtas inga data. I stället används simuleringsdata så att du snabbt kan arbeta utan att vänta på att begäran ska köras. När du är online igen väljer du ![Uppdatera](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]** eller ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** om du vill uppdatera datablocken med aktuella data.

Aktivera offline-läge

1. Välj ![Inställning](/help/assets/icons/Setting.svg).

1. Växla **[!UICONTROL Enable off-line mode]** på.

1. Ange ett positivt heltal i fältet **[!UICONTROL Display metric data]** som.

1. Välj **[!UICONTROL Apply]**.


## Språk

Du kan välja språk för Report Builder-gränssnittet. Alla Customer Journey Analytics-språk som stöds finns tillgängliga.

Så här väljer du vilket språk som ska användas i Report Builder-gränssnittet:

1. Välj ett språk i listrutan **[!UICONTROL Language]**.

1. Välj **Använd.**

## Felsökning

Inställningen **[!UICONTROL Troubleshooting logs]** loggar alla klient-/serverdata till en lokal fil. Använd det här alternativet för att lösa supportärenden.

Om du vill aktivera felsökningsloggar kontrollerar du **[!UICONTROL Log report builder request to local file]**.

<!--
Use the **Settings** pane to configure application-level settings such as the language displayed by the UI or whether or not to work in off-line mode. The settings are applied immediately and they are set for all future sessions until they're changed.

To change Report Builder settings

1. Click the **Settings** icon.

1. Make changes to Enable off-line mode, select a Language, or enable Troubleshooting log settings.

1. Click **Apply**.

    ![Report Builder settings.](./assets/image38.png)

## Off-line mode

When creating and editing a data block in off-line mode, data is not retrieved. Instead, simulation data is used so that you can quickly create and edit a data block without waiting for the request to run. When you are back online, the *Refresh data block* command or *Refresh all data blocks* command refreshes the data blocks that you created with actual data.

To enable off-line mode

1. Click the **[!UICONTROL Settings]** icon.

1. Select **[!UICONTROL Enable off-line mod]e**.

1. Enter a positive integer in the **[!UICONTROL Display metric data as]** field.

1. Click **[!UICONTROL Apply]**.

## Language

You can choose the language for the Report Builder UI. All supported Adobe Analytics languages are available.

To select the language used in the Report Builder UI

 1. Click Settings.

 1. Select a language from the **[!UICONTROL Language]** drop down menu.

     ![Report Builder date range pane showing the Language list with English selected.](./assets/image39.png)

 1. Click **[!UICONTROL Apply].**

## Troubleshooting

Use the Troubleshooting setting to log all client/server data to a local file. Use this option to help resolve support tickets.

To enable the Troubleshooting option, select **[!UICONTROL Log report builder data block to web console]**.
-->