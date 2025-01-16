---
description: Quick Insights är ett verktyg för nya Workspace-användare som vägleder dem när de bygger datatabeller och visualiseringar
title: Panelen Snabbinsikter
feature: Panels
role: User, Admin
exl-id: 29b26ec9-d410-43d6-a317-ca7587f5dd31
source-git-commit: 7bac64aed46d9d7a83dc61c3f55d33ad56564efe
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 1%

---

# Panelen Snabbinsikter {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_quickinsights_button"
>title="Snabba insikter"
>abstract="Skapa en panel för att snabbt skapa en frihandsritabell och medföljande visualisering för att analysera och hitta insikter snabbare."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*I den här artikeln visas panelen Snabbinsikter i **Adobe Analytics**.<br/>Se [Panelen Snabbinsikter](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/quickinsight) för **Customer Journey Analytics**-versionen av den här artikeln.*

>[!ENDSHADEBOX]


[!UICONTROL Quick Insights] ger vägledning till icke-analytiker och nya användare av [!UICONTROL Analysis Workspace] så att de kan lära sig att snabbt och enkelt svara på affärsfrågor. Det är också ett bra verktyg för avancerade användare som snabbt vill besvara en enkel fråga utan att själva behöva skapa en tabell.

När du börjar använda [!UICONTROL Analysis Workspace] kanske du undrar:

* vilka visualiseringar som skulle vara mest användbara,
* vilka dimensioner och mätvärden som kan underlätta insikter,
* var du kan dra och släppa objekt,
* var ett filter ska skapas,
* med mera.

För att hjälpa till med dessa frågor använder [!UICONTROL Quick insights] en algoritm som ger dig de populäraste dimensionerna, måtten, segmenten och datumintervallen som ditt företag använder. Den här algoritmen baseras på ditt företags användning av datakomponenter i [!UICONTROL Analysis Workspace]. Du ser faktiskt mått, mått och segment som taggats med [!UICONTROL POPULAR] i listrutan, vilket visas här:

![Panelen Snabbinsikter.](assets/popular-tag.png)

[!UICONTROL Quick Insights] hjälper dig

* Bygg en datatabell och en medföljande visualisering på rätt sätt i [!UICONTROL Analysis Workspace].
* Lär dig terminologi och vokabulär för grundläggande komponenter och delar av [!UICONTROL Analysis Workspace].
* Gör enkla uppdelningar av dimensioner, lägg till flera mätvärden eller jämför segment enkelt i en [!UICONTROL Freeform table].
* Ändra eller prova olika visualiseringstyper för att snabbt och intuitivt hitta sökverktyget för din analys.

## Grundläggande nyckelterminologi

Nedan följer några grundläggande termer som du måste känna till. Varje datatabell består av två eller flera byggstenar (komponenter) som du använder för att berätta din databerättelse.

| Byggblock (komponent) | Definition |
|---|---|
| **[!UICONTROL Dimension]** | Dimensioner är beskrivningar eller egenskaper för mätdata som kan visas, delas upp och jämföras i ett projekt. De är icke-numeriska värden och datum som delas upp i dimensionsobjekt. *webbläsare* eller *sida* är till exempel en dimension. |
| **[!UICONTROL Dimension item]** | Dimensioner är enskilda värden för en dimension. Dimensionsobjekten för webbläsardimensionen är till exempel *Chrome*, *Firefox*, *Edge* eller andra. |
| **[!UICONTROL Metric]** | Mätvärden är kvantitativ information om personaktivitet, t.ex. vyer, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare. |
| **[!UICONTROL Visualization]** | Workspace erbjuder [ett antal visualiseringar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) för att skapa visuella representationer av dina data. t.ex. stapeldiagram, mundiagram, histogram, linjediagram, kartor, punktdiagram med mera. |
| **[!UICONTROL Dimension Breakdown]** | En dimensionsuppdelning är ett sätt att dela upp en dimension efter andra dimensioner. Du kan till exempel bryta ned USA:s mobilenheter för att få mobilenhetsbesök per delstat. Eller så kan ni bryta ned mobila enheter efter mobilenhetstyper, efter regioner, efter interna kampanjer med mera. |
| **[!UICONTROL Segments]** | Med segment kan du identifiera delmängder av personer baserat på egenskaper eller webbplatsinteraktioner. Du kan till exempel skapa [!UICONTROL Visitor] segment baserat på <li>attribut: webbläsartyp, enhet, antal besök, land, kön eller</li><li>interaktioner: kampanjer, nyckelordssökning, sökmotor eller</li><li>lämnar och lämnar: besökare från Facebook, en definierad landningssida, hänvisande domän, eller</li><li> anpassade variabler: formulärfält, definierade kategorier, kund-ID. |

## Använd

Så här använder du en **[!UICONTROL Quick insights]**-panel:

1. Skapa en **[!UICONTROL Quick insights]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).

1. När du först använder en **[!UICONTROL Quick insights]**-panel kanske du vill gå igenom den korta [!UICONTROL Intro tutorial] som lär dig grunderna. Välj ![HelpOutline](/help/assets/icons/HelpOutline.svg) bredvid paneltiteln Snabbinsikter och välj **[!UICONTROL Intro tutorial]** i popup-fönstret.

1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.


### Panelindata

Välj byggstenar:

* **[!UICONTROL Analyze]** - ange en dimension (orange)
* **[!UICONTROL by]** - ange ett mått (grönt)
* **[!UICONTROL filter by]** - ange ett segment (blått)
* **[!UICONTROL on]** - ange ett datumintervall (lila).

Du måste välja minst en dimension och ett mått för att visualiseringen ska fungera korrekt.



Du kan ange byggblocken på tre sätt:

* Dra och släpp komponenter från den vänstra panelen.
* Börja skriva i ett av byggblocksfälten. När indata påträffas fylls byggblocksfältet automatiskt i med möjliga värden.
* Ange en listruta för byggblock (till exempel `Country` i **[!UICONTROL Analyze]**) och sök i listan med möjliga värden (med ![Sparrhöger](/help/assets/icons/ChevronRight.svg)) efter det värde du vill använda (till exempel **[!UICONTROL Country code]**).

Välj **[!UICONTROL Clear]** om du vill rensa alla inmatningsfält.


### Panelutdata

1. När du har lagt till minst en dimension och ett mätvärde kan du se resultatet.

   ![Registret Frihand visar dimensionen lodrätt och måttet vågrätt.](assets/quick-insights-output.png)

   * En friformstabell med dimensionen ([!UICONTROL Country Site]) och måttet ([!UICONTROL Visits]), segmenterad av [!UICONTROL Visits] från [!UICONTROL Search Engines] för [!UICONTROL Last 12 months].

   * En åtföljande visualisering, i det här fallet ett [stapeldiagram](/help/analyze/analysis-workspace/visualizations/bar.md). Den visualisering som genereras baseras på den typ av data som du har lagt till i tabellen. Alla tidsbaserade data (till exempel [!UICONTROL Visits] per dag/månad) blir som standard ett [!UICONTROL Line]-diagram. Alla icke-tidsbaserade data (till exempel [!UICONTROL Visits] per [!UICONTROL Device]) blir som standard ett [!UICONTROL Bar]-diagram. Du kan ändra visualiseringstypen genom att klicka på listrutepilen bredvid visualiseringstypen.

1. Försök lägga till fler förbättringar enligt beskrivningen nedan under [Fler tips](#more-tips)

1. Du kanske vill spara projektet med **[!UICONTROL Project > Save]**.

## Fler tips

Andra användbara tips visas i [!UICONTROL Quick Insights Builder]. Vissa av dem beror på den senaste åtgärden.

* Först kanske du vill slutföra självstudiekursen **[!UICONTROL More tips]**. Den här självstudiekursen visar upp till 24 timmar efter att du har skapat ett projekt med minst en dimension och ett mått. Välj ![HelpOutline](/help/assets/icons/HelpOutline.svg) bredvid paneltiteln Snabbinsikter och välj **[!UICONTROL More tips]** i popup-fönstret.

  ![Meddelande från panelen Snabbinformation visas när du har valt hjälpikonen.](assets/qibuilder4.png)

* Du kan analysera flera dimensioner och mätvärden, kombinera eller jämföra segment och ange ett datumintervall:

  ![Resultat av verktyget för snabb Insights-byggaren](assets/qibuilder-result.png)

   * **[!UICONTROL Analyze]** dimension **[!UICONTROL Broken-Down by]**: Du kan använda upp till tre nivåer av uppdelningar på dimensioner för att gå ned till de data du verkligen behöver. Se ➊, ➋ och ➌.

   * Lägg till fler mätvärden **[!UICONTROL by]**: Du kan lägga till upp till två mätvärden till. Se och..

   * **[!UICONTROL filter by]**: Du kan lägga till upp till två segment till. Du kan till exempel lägga till Bokningar som ett segment och kombinera det segmentet med segmenten Vanliga bokningar och Första gången som du jämför. Se ➏, ➐ och ➑.

   * on: Du kan ange datumintervall. Se ➒.

## Kända begränsningar

Om du försöker redigera direkt i tabellen kan panelen [!UICONTROL Quick Insights] bli osynkroniserad. Välj **[!UICONTROL Resync Builder]** längst upp till höger på panelen om du vill återställa den till de tidigare [!UICONTROL Quick Insights] inställningarna.

Du får en varning innan du lägger till något direkt i tabellen:

![Alternativvarning för omsynkroniseringsverktyget.](assets/qibuilder-outofsync.png)

Om du skapar tabellen direkt fungerar den som en traditionell Freeform-tabell, utan de praktiska funktionerna för nya användare.


>[!MORELIKETHIS]
>
>[Skapa en panel](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>
<!--
# Quick Insights panel

[!UICONTROL Quick Insights] provides guidance for non-analysts and new users of [!UICONTROL Analysis Workspace] to learn how to answer business questions quickly and easily. It is also a great tool for advanced users who want to answer a simple question quickly without having to build a table themselves.

When you first start using this [!UICONTROL Analysis Workspace], you might wonder what visualizations would be most useful, which dimensions and metrics might facilitate insights, where to drag and drop items, where to create a segment, etc. 

To help with this, and based on your own company's usage of data components in [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] leverages an algorithm that will present you with the most popular dimensions, metrics, segments, and date ranges your company uses. In fact, you will see dimensions, metrics, and segments tagged as [!UICONTROL Popular] in the drop-down list, as shown here:

![](assets/popular-tag.png)

[!UICONTROL Quick Insights] helps you

* Properly build a data table and an accompanying visualization in [!UICONTROL Analysis Workspace].
* Learn the terminology and vocabulary for basic components and pieces of [!UICONTROL Analysis Workspace].
* Do simple breakdowns of dimensions, add multiple metrics, or compare segments easily within a [!UICONTROL Freeform table].
* Change or try out various visualization types to find the find tool for your analysis quickly and intuitively.

Here is a video overview of the [!UICONTROL Quick Insights] panel:

>[!VIDEO](https://video.tv.adobe.com/v/37248/?quality=12)

## Basic key terminology

Following are some of the basic terms you need to be familiar with. Each data table consists of 2 or more building blocks (components) that you utilize to tell your data story.

|Building block (Component)|Definition|
|---|---|
|[!UICONTROL Dimension]|Dimensions are descriptions or characteristics of metric data that can be viewed, broken down, and compared in a project. They are non-numeric values and dates that break down into dimension items. For example, "browser", or "page" are dimensions.|
|[!UICONTROL Dimension item]|Dimension items are individual values for a dimension. For example, dimension items for the browser dimension would be "Chrome", "Firefox", "Edge", etc.|
|[!UICONTROL Metric]|Metrics are quantitative information about visitor activity, such as views, click-throughs, reloads, average time spent, units, orders, revenue, and so on.|
|[!UICONTROL Visualization]|Workspace offers [a number of visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) to build visual representations of your data, such as bar charts, donut charts, histograms, line charts, maps, scatterplots, and others.|
|[!UICONTROL Dimension Breakdown]|A dimension breakdown is a way to literally break down a dimension by other dimensions. In our example, you could break down US States by Mobile Devices to get the mobile device visits per state, or you could break Mobile Devices down by Mobile Device types, by Regions, by Internal Campaigns, etc..|
|[!UICONTROL Segment]|Segments let you identify subsets of visitors based on characteristics or website interactions. For example, you can build [!UICONTROL Visitor] segments based on attributes: browser type, device, number of visits, country, gender, or based on interactions: campaigns, keyword search, search engine, or based on exits and entries: visitors from Facebook, a defined landing page, referring domain, or based on custom variables: form field, defined categories, customer ID.  |

## Get started with Quick Insights

1. Log in to Adobe Analytics using the credentials you have been provided with.
1. Go to [!UICONTROL Workspace] and click **[!UICONTROL Create New Project]** and then click **[!UICONTROL Quick Insights]**. (You can also access this panel from the **[!UICONTROL Panel]** menu in the left rail.)

    ![](assets/qibuilder.png)

    ![](assets/qi-panel.png)

1. When you first start out, go through the short tutorial that teaches you some of the [!UICONTROL Quick Insights panel] basics. Or, click to **[!UICONTROL Skip Tutorial]**.
1. Select your building blocks (also known as components): dimensions (orange), metrics (green), segments (blue), or date ranges (purple) You have to select at least one dimension and one metric for a table to be built automatically. 

    ![](assets/qibuilder2.png)

    You have three ways of selecting the building blocks:
    * Drag and drop them from the left rail.
    * If you know what you are looking for: Start typing and [!UICONTROL Quick Insights] will fill in the blanks for you.
    * Click on the drop-down and search the list.

1. When you have added at least one dimension and one metric, the following will be created for you:

    * A Freeform table with the dimension (here, US States) vertically and the metric (here, Visits) horizontally at the top. Check out this table: 

    ![](assets/qibuilder3.png)

    * An accompanying visualization, in this case a [bar chart](/help/analyze/analysis-workspace/visualizations/bar.md). The visualization that is generated is based on the type of data you added to the table. Any time-based data (such as [!UICONTROL Visits] per Day/Month) defaults to a [!UICONTROL Line] chart. Any non-time-based data (such as [!UICONTROL Visits] per [!UICONTROL Device]) defaults to a [!UICONTROL Bar] chart. You can change the type of visualization by clicking on the drop-down arrow next to the visualization type.

1. (Optional) Drill down on dimensions and see dimension items by clicking the > right-arrow next to the dimension.

1. Try adding some more refinements as described below under "More tips."

1. Save your project by clicking **[!UICONTROL Project > Save]**.

## More tips

Other useful hints will pop up in the [!UICONTROL Quick Insights Builder], some of them depending on your last action.

* First, complete the **[!UICONTROL More tips]** tutorial: Access it via the Help (?) icon next to the [!UICONTROL Quick Insights] title. This tutorial shows up 24 hours after you have created a project with at least one dimension and one metric.

    ![](assets/qibuilder4.png)

* **Breakdown by**: You can use up to 3 levels of breakdowns on dimensions to drill down to the data you really need.

    ![](assets/qibuilder5.png)

* **Add more metrics**: You can add up to 2 more metrics by using the AND operator to add them the table.

    ![](assets/qibuilder6.png)

* **Add more segments**: You can add up to 2 more segments by using the AND or OR operators to add them the table. Look at what happens to the table when you add Mobile Users OR Loyal Visitors. They are next to each other, above the metrics. If you added Mobile Users AND Loyal Visitors, you would see results from both segments together, and they would be stacked on top of each other in the table.

    ![](assets/qibuilder7.png)

## Known limitations

If you try to edit directly within the table, it will cause the [!UICONTROL Quick Insights] panel to become out of sync. You can restore it to the previous [!UICONTROL Quick Insights] settings by clicking **[!UICONTROL Resync Builder]** at the top right of the panel.

 ![](assets/qibuilder9.png)

You will get a warning before adding anything directly to the table:

 ![](assets/qibuilder8.png)

Otherwise, building directly will cause the table to now behave as a traditional Freeform table, without the helpful features for new users.

-->