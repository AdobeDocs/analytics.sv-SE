---
description: Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, datum, enheter, order, intäkter osv. Mätvärden och associerade data visas i rapportkolumnerna.
title: Mätvärden
uuid: ab9d8a45-0297-4757-b0f0-d8b0e0db8d67
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 3%

---


# Mätvärden

>[!IMPORTANT]
>
>Adobe flyttar Ad Hoc Analysis till livscykelns slutstatus den 1 mars 2021. [Läs mer...](https://adobe.ly/discoverworkspace).

Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, datum, enheter, order, intäkter osv. Mätvärden och associerade data visas i rapportkolumnerna.

## Mätvärden {#concept_46A67930CFDB4A078225C5B189688AF3}

Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, datum, enheter, order, intäkter osv. Mätvärden och associerade data visas i rapportkolumnerna.

Standardvärden är:

* **Trafik**: Visar data om besökarnas volym.
* **Konvertering**: Visa data om lyckade händelser på din webbplats. Framgångshändelser kan omfatta inköp, nedladdningar eller andra åtgärder som du vill att användarna ska utföra på din webbplats.
* **Beräknat**: Anpassningsbara mätvärden som skapats genom att andra mätvärden kombineras. Du kan till exempel skapa ett mätvärde som subtraherar nyckelordskostnaden och kostnaden för varor från intäkterna för att få nettointäkter. Du kan sedan dividera beloppet med det totala antalet order för att få en genomsnittlig nettointäkt per order.

Se [Mätdefinitioner](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metricslist.html) i *Analytics Reference* för information om hur mätvärden används i [!DNL Experience Cloud].

Du kan använda [!UICONTROL Organize Metrics] verktyget för att skapa nya mappar för dina mätvärden. Sedan kan ni gruppera mätvärden som ni vill. I Sorteraren kan du kopiera befintliga mått till dina anpassade mappar genom att dra och släppa.

Du kan skapa mappar, namnge dem och ordna måtten i dem hur du vill, men du kan inte ändra standardmapparna, förutom mapparna Favoriter och Beräknade mått.

## Organisera mått {#task_17C844A9387042EAA9983E1E554846B1}

Steg som beskriver hur du organiserar mätvärden och skapar mätmappar.

<!-- 

t_organize_metrics.xml

 -->

1. Klicka på i [!UICONTROL Metrics] verktygspanelen **[!UICONTROL More Actions]**. (  ![](assets/tools_icon.png)

   )
1. Klicka på **[!UICONTROL Organize Metrics]**.
1. Klicka **[!UICONTROL New]** för att skapa en mapp.
1. Välj mätvärden i andra mappar och dra sedan markeringen till den nya mappen.
1. Klicka på **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >När du tar bort en mapp tas alla mätvärden i mappen bort från det markerade projektet.

## Lägg till mått i en rapport {#task_747DD1718B3F4776B83A115D0BE8754C}

Steg som beskriver hur du lägger till mätvärden i en rapport.

<!-- 

t_add_metrics_dsc.xml

 -->

1. Leta reda på måtten i [!UICONTROL Metrics] verktygspanelen.

   Du kan hitta mätvärden i sökfältet eller genom att gå ned i mätmappar.

1. Dra mätvärdena till rapporttabellen eller [!UICONTROL Table Builder].

   Du kanske vill ange standardvärden i [!UICONTROL Settings] förväg om du vill minska behovet av att lägga till mått flera gånger i en rapport.

   Se [Rankad flik - Definitioner](/help/analyze/ad-hoc-analysis/c-global-settings.md#reference_FB9BADD7E3DA42C1BB2A02A6E9D5C1CF).

## Beräknad metrisk Builder {#concept_F8E213CE786A43FB93847C5BA883A29C}

Ad Hoc Analysis Calculated Metric Builder är nu knutet till Analytics Unified Calculated Metrics. Användargränssnittet liknar det i Analytics (Beräknad metrisk Builder).

<!-- 

c_calc_metric_builder.xml

 -->

Mer information om hur du skapar och hanterar beräknade mått finns i [Handboken](https://docs.adobe.com/content/help/sv-SE/analytics/components/calculated-metrics/cm-overview.html)för beräknade mått.

Så här kommer du åt verktyget Beräknade mätvärden i Ad Hoc Analysis:

1. Klicka på i [!UICONTROL Metrics] rutan **[!UICONTROL More Options]** och sedan **[!UICONTROL Calculated Metrics Builder]**.

   ![](assets/more_options_calc.png)

1. Med gränssnittet Calculated Metric Builder kan du dra och släppa mätvärden, segment och funktioner för att skapa anpassade mätvärden:

   ![](assets/calc_metrics.png)

