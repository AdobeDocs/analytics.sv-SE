---
description: Lär dig mer om hur du skapar beräknade mätvärden.
title: Arbetsflöde för beräknade mätvärden
feature: Calculated Metrics
exl-id: b3380d6b-53b5-40af-8e23-34772d79ae26
source-git-commit: 183f6e39fb1d14b7b29817e76da0302ba23cd5d6
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---

# Skapa beräknade mått

Som standard kan bara administratörer skapa beräknade värden. Användare har behörighet att visa beräknade värden, ungefär som hur användare visar andra komponenter (till exempel segment, anteckningar och annat).

Du kan skapa ett beräknat mått på följande sätt:

![Olika sätt att skapa ett mått](assets/create-metric.png)

* **A**. I huvudgränssnittet väljer du **[!UICONTROL Components]** och sedan **[!UICONTROL Calculated metrics]**. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] i [[!UICONTROL Calculated metrics] manager](cm-manager.md).
* **B**. I ett Workspace-projekt väljer du ![Lägg till](/help/assets/icons/Add.svg) vid ![Händelse](/help/assets/icons/Event.svg) **Mätvärden** från den vänstra panelen Komponenter.
* **C**. I ett Workspace-projekt väljer du **[!UICONTROL Create metric from selection]** på snabbmenyn i kolumnrubriken Mått. På undermenyn kan du välja en funktion eller välja **[!UICONTROL Open in calculated metric builder]**. <br/>Om du väljer en funktion definieras det beräknade måttet som ett projekttsmått. När du senare redigerar det här måttet visas ett meddelande i [verktyget för beräknade mätvärden](/help/analyze/analysis-workspace/components/use-components-in-workspace.md) via popup-fönstret [Komponentinformation](c-build-metrics/cm-build-metrics.md).
* **D**. I ett Workspace-projekt väljer du **[!UICONTROL Components]** på menyn och sedan **[!UICONTROL Create metric]**.
* **E**. Använd genvägen **[!UICONTROL shift+cmd+c]** (macOS) eller **[!UICONTROL shift+ctrl+c]** (Windows) i ett Workspace-projekt.

Om du vill definiera det nya beräknade måttet använder du verktyget [Beräknade mätvärden](c-build-metrics/cm-build-metrics.md).


## Arbetsflöde

Innan du skapar beräknade värden bör du tänka på följande arbetsflöde:

| Arbetsflödesuppgift | Beskrivning |
| --- | --- |
| Planera beräknade värden | I synnerhet för mätvärden som kommer att bli officiellt&quot;godkända&quot; är det rimligt att beskriva vilka beräknade mätvärden som kommer att användas i stor omfattning och hur de kommer att definieras. |
| [Bygg](c-build-metrics/cm-build-metrics.md) beräknade värden | Bygg och redigera beräknade och avancerade beräknade mätvärden för användning i [!DNL Analytics]-komponenter.  Se [exempel](c-build-metrics/cm-build-metrics.md) på hur du skapar beräknade mått. |
| [Tagg](cm-tagging.md) beräknade mått | Märk beräknade mätvärden för enkel organisation och delning. Se hur du planerar och tilldelar taggar för enkla och avancerade sökningar och organisation. |
| [Godkänn ](cm-approving.md) beräknade mått | Godkänn beräknade värden för att göra dem kanoniska. |
| Använd beräknade värden | Använd beräknade värden i dina projekt. |
| [Dela](cm-sharing.md) beräknade mått | Dela dina beräknade värden med andra individer, grupper eller organisationer. |
| [Filter](cm-filter.md) beräknade värden | Filtrera beräknade mätvärden efter taggar, ägare och andra filter (Visa alla, Min, Delas med mig, Favoriter och Godkänd). |
| Markera beräknade värden som [favoriter](cm-finding.md) | Att markera mätvärden som favoriter är ett annat sätt att ordna dem så att de blir lätta att använda. |
