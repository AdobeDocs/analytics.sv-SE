---
description: Visa dina data visuellt med visualiseringar.
keywords: Analysis Workspace
title: Översikt över visualiseringar
translation-type: tm+mt
source-git-commit: 60aacc2d2d5f7f66c08d270a41d2f6c86ee34a6b
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 3%

---


# Översikt över visualiseringar

Workspace erbjuder ett antal visualiseringar som gör att du kan generera visuella representationer av dina data, t.ex. stapeldiagram, dondiagram, histogram, linjediagram, kartor, punktdiagram med mera. De flesta visualiseringstyper är välbekanta för dig om du använder Adobe Analytics. Men Analysis Workspace har visualiseringsinställningar och många nya eller unika visualiseringstyper med interaktiva funktioner.

Du kan komma åt visualiseringar från den övre vänstra ikonen i arbetsytan, från en [tom panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html)eller från högerklicksmenyn i arbetsflödet.

![](assets/viz-rail.png)

Följande visualiseringstyper finns i Analysis Workspace:

| Visualiseringsnamn | Beskrivning |
| --- | --- |
| [Yta](/help/analyze/analysis-workspace/visualizations/area.md) | Som ett linjediagram, men med ett färgat område under linjen. Använd ett ytdiagram när du har flera mätvärden och vill visualisera området som uttrycks genom skärningspunkten för två eller flera mätvärden. |
| [Liggande](/help/analyze/analysis-workspace/visualizations/bar.md) | Visar lodräta staplar som representerar olika värden för ett eller flera mätvärden. |
| [Punktdiagram](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | Visar hur ett värde som du är intresserad av jämförs med eller mäter mot andra prestandaintervall (mål). |
| [Kohortabell](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | A *`cohort`* is a group of people sharing common characteristics over a specified period. Kohortanalys är användbart för analys av kvarhållande, bortfall eller fördröjning. |
| [Ringdiagram](/help/analyze/analysis-workspace/visualizations/donut.md) | På samma sätt som ett cirkeldiagram visar den här visualiseringen data som delar eller segment av en helhet. |
| [Utfall](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | Utfallsrapporter visar var besökarna lämnade (föll ned) och fortsatte igenom (föll igenom) en fördefinierad sidsekvens. Kan anges till sekvenser av typen slutlig eller exakt |
| [Flöde](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | Visar exakta kundvägar via era webbplatser och appar. |
| [Frihandstabell](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) | En friformstabell är inte bara en datatabell, utan också en interaktiv visualisering. Det är grunden för dataanalys i Workspace. |
| [Histogram](/help/analyze/analysis-workspace/visualizations/histogram.md) | Ett histogram lurar besökare, besök eller träffar i grupper baserat på en mätvolym. |
| [Vågrätt fält](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | Visar vågräta staplar som representerar olika värden för ett eller flera mätvärden. |
| [Linjediagram](/help/analyze/analysis-workspace/visualizations/line.md) | Representerar mätvärden med hjälp av en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram använder tid längs x-axeln. |
| [Mappa](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | Gör att du kan skapa en visuell karta över alla mått (inklusive beräknade värden). |
| [Spridningsdiagram](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | Visar relationen mellan dimensionsobjekt och upp till tre mätvärden. |
| [Sammanfattningsnummer](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | Visar den markerade cellen som ett stort tal. |
| [Sammanfattningsändring](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | Visar ändringen mellan de markerade cellerna som ett stort tal/procent. |
| [Text](/help/analyze/analysis-workspace/visualizations/text.md) | Gör att du kan lägga till användardefinierad text på arbetsytan. Användbar för att lägga till ytterligare kontext till analyser och insikter, utöver att utnyttja beskrivningar av paneler/visualisering |
| [Treemap-diagram](/help/analyze/analysis-workspace/visualizations/treemap.md) | Visar hierarkiska data (i trädstrukturer) som en uppsättning kapslade rektanglar. |
| [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) | Använder cirklar för att beskriva måttöverlappningen för upp till 3 segment. |

## Inställningar {#settings}

Varje visualisering har sina egna inställningar som du kan hantera. Klicka på [!UICONTROL Visualization Settings]kugghjulsikonen för att komma åt [!UICONTROL Visualization Settings] den.

![](assets/settings.png)

| Inställning | Beskrivning |
| --- | --- |
| Visualiseringstyp | Ändra den typ av visuell information som används för att avbilda data. |
| Kornighet | För trendvisualiseringar kan du ändra tidshalten (dag, vecka, månad osv.) från den här listrutan. Den här ändringen gäller även för datakälltabellen. |
| Procenttal | Visar värden i procent. |
| 100 % staplad | Den här inställningen för staplade ytor, staplade staplar eller vågräta staplade visualiseringar gör att diagrammet blir en&quot;100 % staplade&quot; visualisering. Exempel: ![Staplad 100 %](assets/stacked_100_percent.png) |
| Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för visualiseringen av Sammanfattningsnummer/Sammanfattningsändring. |
| Begränsa maximalt antal objekt | Gör att du kan begränsa antalet objekt som visas i en visualisering. |
| Ankra Y-axel vid noll | Om alla värden som är ritade i diagrammet ligger betydligt över noll, kommer diagrammets standardvärde att göra den nedre delen av y-axeln ICKE-ZERO. Om du markerar den här rutan kommer y-axeln att tvingas till noll (och diagrammet ritas om). |
| Normalisering | Tvingar måtten att ha samma proportioner. Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
| Visa dubbel axel | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för det andra måttet). Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
| Visa avvikelser | Förbättrar linjediagram och frihandstabeller genom att visa avvikelseidentifiering. Analysidentifiering i linjevisualiseringar inkluderar ett förväntat värde (streckad linje) och ett förväntat intervall (skuggat band). |

## Förklaring {#legend}

En visualiseringsförklaring hjälper dig att relatera datum i en källtabell till plottade serier i visualiseringen. Förklaringen är interaktiv - du kan klicka på ett förklaringsobjekt om du vill visa/dölja en serie i visualiseringen. Detta är praktiskt om du vill förenkla de data som visualiseras.

Dessutom kan du byta namn på förklaringsetiketter så att det blir lättare att använda bilderna. Note: legend editing does **not** apply to: Treemap, Bullet, Summary Change/Number, Text, Freeform, Histogram, Cohort or Flow visualizations.

Så här redigerar du en förklaringsetikett:

1. Högerklicka på någon av förklaringsetiketterna.
1. Klicka på **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. Ange den nya etikettexten.
1. Tryck för **[!UICONTROL Enter]** att spara.

Här är en [länk till en video](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html) om det här ämnet.

## Högerklicka på menyn {#right-click}

Ytterligare funktioner för en visualisering är tillgängliga genom att högerklicka på visualiseringsrubriken. Inställningarna varierar beroende på visualisering. Några av de tillgängliga inställningarna är:

![](assets/right-click.png)

| Inställning | Beskrivning |
| --- | --- |
| Infoga kopierad panel/visualisering | Gör att du kan klistra in (&quot;infoga&quot;) en kopierad panel eller visualisering på en annan plats i projektet, eller i ett helt annat projekt. |
| Kopiera visualisering | Högerklicka och kopiera en visualisering så att du kan infoga den på en annan plats i projektet eller i ett helt annat projekt. |
| [Hämta objekt som CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-items) | Hämta upp till 50 000 dimensionsobjekt för den valda dimensionen som en CSV-fil. |
| [Hämta data som CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-data) | Hämta en datakälla för visualisering som en CSV-fil. |
| Duplicera visualisering | Skapar en exakt kopia av den aktuella visualiseringen, som du sedan kan ändra. |
| Redigera beskrivning | Lägg till (eller redigera) en textbeskrivning för visualiseringen. |
| Hämta visualiseringslänk | Gör att du kan dirigera någon till en viss visualisering i ett projekt. När användaren klickar på länken måste mottagaren logga in innan den dirigeras till den exakta visualisering som är länkad till den. |
| Börja om | (Works for Flow, Venn, Histogram) Tar bort konfigurationen för den aktuella visualiseringen så att du kan konfigurera om den från början. |

## Ikonen Skapa visuell {#quick-viz}

Om du är osäker på vilken visualisering du ska välja klickar du på **[!UICONTROL Create Visual]** ikonen i valfri tabellrad (tillgänglig vid hovring). Det här är det snabbaste sättet att lägga till en visualisering. När du klickar på den uppmanas Analysis Workspace att göra en kvalificerad gissning där visualiseringen bäst passar dina data. Om du till exempel har markerat 1 rad skapas ett linjediagram. Om du har markerat 3 segmentrader skapas ett Venndiagram.

![](assets/quick-viz.png)
