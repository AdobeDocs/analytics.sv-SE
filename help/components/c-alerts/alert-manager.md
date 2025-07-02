---
description: Lär dig hur du hanterar aviseringar.
title: Hantera aviseringar
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 24dd47e995523aedba1385ee8882af5e11c7b128
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 0%

---


# Hantera aviseringar


Du kan filtrera, tagga, ta bort, byta namn på, kopiera, aktivera, inaktivera, förnya och exportera aviseringar från ett centralt [!UICONTROL Alerts]-hanteringsgränssnitt. Så här hanterar du aviseringar:

* Välj **[!UICONTROL Components]** i huvudgränssnittet och välj sedan **[!UICONTROL Alerts]**.

Varningshanteraren är strukturerad som [Segmenthanteraren](/help/components/segmentation/segmentation-workflow/seg-manage.md) och [hanteraren för beräknade värden](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md).


## Varningshanteraren

Varningshanteraren har följande gränssnittselement:

![Gränssnitt för filter](assets/alerts-manager.png)

### Varningslista

Aviseringslistan ➊ visar alla aviseringar som du äger, aviseringar som har omfattats av alla dina projekt och aviseringar som har delats med dig. Listan innehåller följande kolumner:

| Kolumn | Beskrivning |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Välj om du vill prioritera ![Star](/help/assets/icons/Star.svg) eller ![StarOutline](/help/assets/icons/StarOutline.svg) en varning. |
| **[!UICONTROL Title and description]** | Om du vill redigera varningen markerar du titellänken, som öppnar [Varningsverktyget](alert-builder.md#alert-builder). |
| **[!UICONTROL Type]** | Varningstypen: en Adobe Analytics-datavarning eller en varning om användning av serversamtal. |
| **[!UICONTROL Enabled]** | Varningen är aktiverad eller inaktiverad. |
| **[!UICONTROL Report suite]** | Rapporterna innehåller programsviter som den här varningen gäller för. |
| **[!UICONTROL Owner]** | Varningens ägare. Som icke-administratör visas endast aviseringar som du äger eller aviseringar som delas med dig. |
| **[!UICONTROL Tags]** | Taggarna för den här varningen. |
| **[!UICONTROL Expiration Date]** | Det datum och den tidpunkt då aviseringen förfaller. |
| **[!UICONTROL Date modified]** | Datum och tid då aviseringen senast ändrades. |

<!-- 

When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul>

-->

Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att ange vilka kolumner du vill visa.

### Åtgärdsfält

Du kan använda åtgärdsfältet ➋ för att utföra åtgärder för aviseringar. Åtgärdsfältet innehåller följande åtgärder:

| Ikon | Åtgärd | Beskrivning |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Lägg till ytterligare en avisering med [Varningsverktyget](alert-builder.md#alert-builder). |
| ![Sök](/help/assets/icons/Search.svg) | [!UICONTROL *Sök efter titel*] | Om ingen varning är markerad i listan söker du efter aviseringar med det här sökfältet. |
| ![Etikett](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Tagga de markerade varningarna. I dialogrutan **[!UICONTROL Tag Alert]** markerar eller avmarkerar du taggarna för de markerade aviseringarna. Välj **[!UICONTROL Save]** om du vill spara taggarna för de valda aviseringarna. |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de markerade aviseringarna. Du uppmanas att bekräfta åtgärden. |
| ![Redigera](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Byt namn på en enskild markerad varning. Om du väljer det här alternativet kan du byta namn på aviseringen. |
| ![Kopiera](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Kopiera den markerade varningen. Nya aviseringar skapas med samma namn och suffix `(Copy)`. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Enable]** eller **[!UICONTROL Disable]** | Aktivera eller inaktivera de markerade aviseringarna. |
| ![Uppdatera](/help/assets/icons/Refresh.svg) | **[!UICONTROL Renew]** | Förnyar aviseringens förfallodatum. Utgångsdatumet är ett år från den dag du väljer det här alternativet, oavsett det ursprungliga förfallodatumet. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Exportera aviseringarna till en `Alerts List.csv`-fil. |


### Aktivt filterfält

Filterfältet ➌ visar de aktiva filter som använts från filterpanelen till listan med varningar (om sådana finns). Du kan snabbt ta bort ett filter med ![CrossSize75](/help/assets/icons/CrossSize75.svg). Om fler än ett filter har angetts kan du ta bort alla filter med **[!UICONTROL Remove all]**.


### Panelen Filter

Du kan filtrera listan med varningar med hjälp av den vänstra panelen ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** ➍ . Filterpanelen visar typ av filter och antalet varningar som följer det specifika filtret.


1. Välj ![Filter](/help/assets/icons/Filter.svg) för att öppna panelen Filter. Om du behöver mer utrymme för varningslistan kan du välja ![Filter](/help/assets/icons/Filter.svg) en gång till för att stänga panelen.
1. Välj filter från något av de tillgängliga filteravsnitten.


#### Filteravsnitt för taggar

{{tagfiltersection}}


#### Rapporteringssvitens filteravsnitt

{{reportsuitefiltersection}}


#### Ägarfilteravsnitt

{{ownerfiltersection}}


#### Aktiverat statusfilteravsnitt

{{enabledstatusfiltersection}}


#### Textfilteravsnitt

{{typefiltersection}}


#### Andra filteravsnitt

{{otherfiltersfiltersection}}



## Redigera aviseringar

Du kan redigera en varning

* Markera aviseringens titel i listan [[!UICONTROL Alert]](#alerts-list).

Du använder [varningsverktyget](alert-builder.md#alert-builder) för att redigera varningen.

## Felsöka en varning

När du felsöker ett problem med en varning ska du ange JID-numret (Job Instance ID) till Adobe Support. JID-numret finns längst ned i e-postaviseringen som du får.

![Varningsmeddelande](assets/alerts-email.PNG)


<!--

# Manage alerts

You can manage existing alerts in the Alerts manager. You can perform various management tasks on alerts, such as tagging, renaming, deleting, and more.

The Alerts manager is structured very much like the [Segment Manager](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=sv-SE) and the [Calculated Metric Manager](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=sv-SE).

 ![](assets/alert-manager.png)

## Create alerts

To create alerts from the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select [!UICONTROL **Add**] (or [!UICONTROL **Create new alert**] if you don't have any existing alerts).

1. Select the alert type that corresponds to the alert that you want to create:

   * [!UICONTROL **Analytics data alert**]: An alert to notify you when abnormal events occur in your data. 

     If you select this option, continue with [Create alerts](/help/components/c-alerts/alert-builder.md) for more details about creating alerts.

   * [!UICONTROL **Server call usage alert**]: An alert to notify you of the risk or occurrence of an overage in your server call consumption and commitment data. 

     If you select this option, continue with [Server call usage alerts](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >You must be an Analytics administrator or a user with the Server call usage permission in order to have access to server call usage. 

## Manage existing alerts

You can perform various actions on existing alerts, such as tagging, renaming, deleting, and so forth.

To manage existing alerts in the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select one or more alerts that you want to manage.

   ![](assets/alert-manager-tasks.png)

1. In the action bar, select any of the following options:

   | Action | Function | 
   |---------|----------|
   | [!UICONTROL **Tag**] | Apply a tag to an alert. This helps you to organize alerts for ease of use. | 
   | [!UICONTROL **Delete**] | Deletes the alert. | 
   | [!UICONTROL **Rename**] | Renames the alert. |
   | [!UICONTROL **Approve**] | Mark the alert as Approved. |
   | [!UICONTROL **Copy**] | Creates a copy (duplicate) of the alert. |
   | [!UICONTROL **Disable**] | Disables an alert that is currently enabled. |
   | [!UICONTROL **Enable**] | Enables an alert that is currently disabled. |
   | [!UICONTROL **Renew**] | Renews the alert expiration date. This extends the  expiration date to be 1 year from the day you selected this option, regardless of the original expiration date. |
   | [!UICONTROL **Export to CSV**] | Exports the alert to a .CSV file. |

## Edit an alert

To edit an existing alert:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select the alert name in the [!UICONTROL **Title and description**] column.

1. Edit the alert as desired. 

   Following are some of the things you can do when editing an alert:

   * Add alerts to other report suites
   * Add or modify the description
   * Modify the time granularity
   * Modify the recipients 
   * Modify the expiration date
   * Modify the metrics and filters

1. Select [!UICONTROL **Save**].

## Configure columns 

You can configure the information displayed for each alert in the Alerts manager by configuring the columns that are displayed.

To configure the visible columns in the Alerts manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Alerts]**. 

1. In the Alert manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Alerts manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Title and description | These values are provided in the Alert builder. To edit the title and description, select the title link to open the Alert builder.  |
   | Favorites  | Displays star icons next to each alert, allowing you to mark alerts as favorites. |
   | Type | Shows whether the alert is an Analytics data alert or a Server call usage alert. |
   | Enabled | Shows whether the alert is currently enabled or disabled. | 
   | Report suite | Indicates in which report suite the alert was last saved.  |
   | Owner | Indicates who owns the alert. As a non-admin, you can see only alerts you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the alert, either by you or by people who shared the alert with you.  |
   | Expiration date | Shows the date and time when the alert is set to expire. |
   | Date modified | Indicates the date when the alert was last modified.  |

   {style="table-layout:auto"}
   
   
    When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> 
   
-->

