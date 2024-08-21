---
description: Hantera aviseringar.
title: Aviseringshanteraren - översikt
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 49324ef7fd45adeef2c31167d0444a7e67041d6d
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Varningshanteraren

Varningshanteraren är mycket strukturerad som [segmenthanteraren](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html) och [hanteraren för beräknade värden](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html).

![](assets/alert-manager.png)

## Öppna Alerts Manager

1. I Adobe Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Varningar**].

## Tillgängliga åtgärder i Varningshanteraren

I Varningshanteraren kan du:

* Öppna varningsverktyget genom att klicka på **[!UICONTROL + Add]**.
* Tagga varningar. På så sätt kan du ordna dem så att de blir lätta att använda.
* Ta bort aviseringar.
* Byt namn på aviseringar.
* Godkänn aviseringar.
* Kopiera aviseringar.
* Aktivera/inaktivera aviseringar.
* **Förnya** ett varningsutgångsdatum. När en eller flera aviseringar har valts kan de förnyas genom att klicka på **[!UICONTROL Renew]**. Detta utökar deras förfallodatum till 1 år från den dag **[!UICONTROL Renew]** klickades på, oavsett deras ursprungliga förfallodatum.
* Exportera en varning till en CSV-fil.
* Redigera aviseringar genom att dubbelklicka på varningens titel.
* Sök efter aviseringar.
* Lägg till aviseringar i andra rapportsviter.
* Ange/ändra ägare för en avisering.
* Lägg till andra filter.
* Definiera ett **utgångsdatum** för en avisering.

## Konfigurera kolumner

Du kan konfigurera den information som visas för varje varning i Varningshanteraren genom att konfigurera de kolumner som visas.

Så här konfigurerar du synliga kolumner i Varningshanteraren:

1. I Adobe Analytics väljer du fliken **[!UICONTROL Components]** och sedan **[!UICONTROL Alerts]**.

1. I Varningshanteraren väljer du ikonen **Anpassa kolumner** ![Anpassa kolumner](assets/customize-columns-icon.png) och markerar sedan de kolumner som du vill ska visas i Varningshanteraren.

   Följande kolumner är tillgängliga:

   | Kolumnrubrik | Beskrivning |
   |---|---|
   | Titel och beskrivning | Dessa värden finns i varningsverktyget. Om du vill redigera titeln och beskrivningen markerar du titellänken för att öppna varningsverktyget. |
   | Favoriter | Visar stjärnikoner bredvid varje varning, så att du kan markera varningar som favoriter. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Typ | Visar om aviseringen är en Analytics-datavarning eller en varning om användning av serveranrop. |
   | Aktiverad | Visar om aviseringen är aktiverad eller inaktiverad. |
   | Rapportsvit | Anger i vilken rapportsvit som aviseringen senast sparades. |
   | Ägare | Anger vem som äger aviseringen. Som icke-administratör kan du bara se aviseringar som du äger eller aviseringar som delats med dig. |
   | Taggar | Visar taggar som har tillämpats på aviseringen, antingen av dig eller av personer som delat aviseringen med dig. |
   | Utgångsdatum | Visar datumet och tiden då aviseringen förfaller. |
   | Ändrat den | Anger datumet då aviseringen senast ändrades. |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->


