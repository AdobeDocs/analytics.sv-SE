---
description: Hantera aviseringar.
title: Aviseringshanteraren - översikt
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 373a1ecffafdcefe3c7b60954f14c2f3a5ca386d
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Varningshanteraren

Du kan hantera befintliga aviseringar i Varningshanteraren. Du kan utföra olika hanteringsåtgärder för varningar, som taggning, namnbyte, borttagning med mera.

Varningshanteraren är mycket strukturerad som [segmenthanteraren](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html) och [hanteraren för beräknade värden](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html).

![](assets/alert-manager.png)

## Skapa aviseringar

Så här skapar du aviseringar från Alerts Manager:

1. Välj **[!UICONTROL Components]** > **[!UICONTROL Alerts]** för att komma åt Alerts Manager i Adobe Analytics.

   ![](assets/alert-manager.png)

1. Välj [!UICONTROL **Lägg till**] (eller [!UICONTROL **Skapa ny avisering**] om du inte har några befintliga aviseringar).

1. Välj den varningstyp som motsvarar den varning som du vill skapa:

   * [!UICONTROL **Analysdatavarning**]: En avisering som meddelar dig när onormala händelser inträffar i dina data.

     Om du väljer det här alternativet kan du fortsätta med [Skapa aviseringar](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md) om du vill ha mer information om hur du skapar aviseringar.

   * [!UICONTROL **Varning om användning av serveranrop**]: En varning som meddelar dig om risken eller förekomsten av ett överskott i serveranropets förbrukning och åtagandedata.

     Om du väljer det här alternativet fortsätter du med [varningar om användning av serversamtal](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >Du måste vara Analytics-administratör eller en användare med användarbehörighet för serversamtal för att få åtkomst till serversamtalsanvändning.

## Hantera befintliga aviseringar

Du kan utföra olika åtgärder på befintliga aviseringar, som taggning, namnbyte, borttagning och så vidare.

Så här hanterar du befintliga aviseringar i Varningshanteraren:

1. Välj **[!UICONTROL Components]** > **[!UICONTROL Alerts]** för att komma åt Alerts Manager i Adobe Analytics.

   ![](assets/alert-manager.png)

1. Välj en eller flera aviseringar som du vill hantera.

   ![](assets/alert-manager-tasks.png)

1. Välj något av följande alternativ i åtgärdsfältet:

   | Åtgärd | Funktion |
   |---------|----------|
   | [!UICONTROL **Tagg**] | Använd en tagg på en varning. Det gör det enklare att ordna varningar. |
   | [!UICONTROL **Ta bort**] | Tar bort varningen. |
   | [!UICONTROL **Byt namn**] | Byter namn på aviseringen. |
   | [!UICONTROL **Godkänn**] | Markera aviseringen som Godkänd. |
   | [!UICONTROL **Kopiera**] | Skapar en kopia (dubblett) av varningen. |
   | [!UICONTROL **Inaktivera**] | Inaktiverar en avisering som är aktiverad. |
   | [!UICONTROL **Aktivera**] | Aktiverar en varning som är inaktiverad. |
   | [!UICONTROL **Förnya**] | Förnyar aviseringens förfallodatum. Detta utökar förfallodatumet till 1 år från den dag du valde det här alternativet, oavsett det ursprungliga förfallodatumet. |
   | [!UICONTROL **Exportera till CSV**] | Exporterar varningen till en CSV-fil. |

## Redigera en varning

Så här redigerar du en befintlig varning:

1. Välj **[!UICONTROL Components]** > **[!UICONTROL Alerts]** för att komma åt Alerts Manager i Adobe Analytics.

   ![](assets/alert-manager.png)

1. Markera varningsnamnet i kolumnen [!UICONTROL **Titel och beskrivning**].

1. Redigera varningen efter behov.

   Nedan följer några av de saker du kan göra när du redigerar en varning:

   * Lägg till aviseringar i andra rapportsviter
   * Ändra ägare
   * Uppdatera filtren
   * Uppdatera förfallodatumet

1. Redigera varningen och välj sedan [!UICONTROL **Spara**].

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


