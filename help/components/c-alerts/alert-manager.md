---
description: Hantera aviseringar.
title: Aviseringshanteraren - översikt
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 9a6c2e7c2f83882f6df630f975b0c44e75a2ed7a
workflow-type: tm+mt
source-wordcount: '431'
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
   | Favoriter | Visar stjärnikoner bredvid varje varning, så att du kan markera varningar som favoriter. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Titel och beskrivning | Dessa värden finns i varningsverktyget. Om du vill redigera titeln och beskrivningen markerar du titellänken för att öppna varningsverktyget. |
   | Rapportsvit | Anger i vilken rapportsvit som aviseringen senast sparades. |
   | Ägare | Anger vem som äger aviseringen. Som icke-administratör kan du bara se aviseringar som du äger eller aviseringar som delats med dig. |
   | Taggar | Visar taggar som har tillämpats på aviseringen, antingen av dig eller av personer som delat aviseringen med dig. |
   | Delas med | Visar enskilda personer eller grupper (endast admin) eller Alla (endast admin) som du har delat aviseringen med. |
   | Ändrat den | Anger datumet då aviseringen senast ändrades. |
   | Senast använd | Visar datumet då aviseringen senast användes. <p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen, var den används och om den behöver tas bort eller ändras.</p><p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Den här informationen inkluderar inte användning från API, Report Builder eller Data Warehouse.</li><li>För vissa komponenter kanske den här kolumnen inte innehåller data om komponenten senast användes före september 2023.</li></ul> |

   {style="table-layout:auto"}
