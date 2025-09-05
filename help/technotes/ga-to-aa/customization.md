---
title: Anpassa rapporter i Adobe Analytics
description: Lär dig hur du anpassar rapporter i Adobe Analytics
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Anpassa rapporter

På tredjepartsplattformar som Google Analytics finns flera anpassningsalternativ. Med dessa anpassningar kan användare skapa kontrollpaneler, anpassade rapporter, sparade rapporter och anpassade aviseringar. Eftersom Analysis Workspace låter användare skapa rapporter från en tom arbetsyta är de flesta anpassningar inbyggda direkt i verktyget.

Den här sidan förutsätter att användaren har grundläggande kunskaper om att använda [!UICONTROL Analysis Workspace]. Se [Skapa en grundläggande rapport i Analysis Workspace för Google Analytics-användare](reports/create-report.md) om du ännu inte känner till verktyget i Adobe Analytics.

## Kontrollpaneler

Arkitekturen [!UICONTROL Analysis Workspace] har skapats på ungefär samma sätt som för instrumentpanelswidgetar. Projekt i [!UICONTROL Analysis Workspace] motsvarar ungefär kontrollpaneler i Google Analytics. Visualiseringar i [!UICONTROL Analysis Workspace] är en ungefärlig motsvarighet till widgetar i Google Analytics.

### Lägga till innehåll i ett projekt

1. Klicka på ikonen [!UICONTROL Visualizations] till vänster och dra önskad visualisering till arbetsytan.
2. Klicka på ikonen [!UICONTROL Components] till vänster och dra önskade mått och mått till visualiseringen för att fylla i dem med data.
3. Dra i kanterna av visualiseringen för att ändra storlek på den och dra i titeln på visualiseringen för att flytta den.

Alla Google Analytics-widgetar är tillgängliga i [!UICONTROL Analysis Workspace]:

* Widgeten **Mått** är ungefär lika med visualiseringen [!UICONTROL Summary Number].
* Widgeten **Tidslinje** är ungefär densamma som visualiseringen [!UICONTROL Line].
* Widgeten **Geomap** är ungefär densamma som visualiseringen [!UICONTROL Map].
* **Tabellwidgeten** är ungefär densamma som visualiseringen för [!UICONTROL Freeform Table].
* **Cirkelwidgeten** är ungefär densamma som visualiseringen för [!UICONTROL Donut].
* Widgeten **Bar** är ungefär densamma som visualiseringen [!UICONTROL Bar].

[!UICONTROL Analysis Workspace] innehåller många fler visualiseringsalternativ för att presentera data på ett sätt som passar dina rapporteringsbehov bäst. Mer information finns i [Visualiseringar i Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) i användarhandboken för Analysera.

### Dela projekt

När du är klar med att lägga till innehåll i ett projekt kan du dela det.

* Om du vill dela projektet med dina kollegor går du till **[!UICONTROL Share > Share Project]**. Mottagare är andra användare i organisationen som har Adobe Analytics-konton.
* Gå till **[!UICONTROL Share > Get Project Link]** om du vill dela ditt projekt via en länk. Observera att detta fortfarande kräver inloggning på Adobe Analytics i din organisation.

### Exportera projekt

Förutom PDF erbjuder [!UICONTROL Analysis Workspace] en CSV-export.

1. Klicka på *[!UICONTROL Share]* > *[!UICONTROL Send File Now]* som öppnar ett modalt fönster.
2. Ange filtyp och mottagare.
3. Klicka på [!UICONTROL Send Now].

## Anpassade rapporter

När du skapar en anpassad rapport i Google Analytics liknar de obligatoriska fälten arbetsflödet när du skapar en visualisering i arbetsytan. Dimensions-, Metrics- och Filter-definitionerna är lika mellan plattformarna. I Analysis Workspace, i stället för att välja mått och mätvärden från en lista, dras mått och mätvärden till en frihandstabell.

### Beräknade mått i anpassade rapporter

Anpassade rapporter är ett av de få områden i Google Analytics som tillåter användning av beräknade mätvärden. Eftersom Analysis Workspace fungerar som en arbetsyta fungerar beräknade mätvärden retroaktivt och i alla sammanhang.

Så här skapar du ett beräknat mått:

1. Klicka på ikonen **+** nära måttlistan för att öppna [!UICONTROL Calculated Metric Builder].
2. Ge det beräknade måttet ett namn och ange ett format.
3. Dra metriska komponenter till definitionsområdet och använd listrutorna mellan varje komponent för att ange en operator.
4. När det beräknade måttet innehåller den önskade formeln klickar du på Spara för att gå tillbaka till arbetsytan.
5. Dra det nydefinierade beräknade måttet till arbetsytan.

   Läs mer om [Beräknade mått](/help/components/calculated-metrics/cm-overview.md) i användarhandboken för komponenter.

## Anpassade aviseringar

Varningar är tillgängliga på båda plattformarna. I Adobe Analytics använder du rubriknavigeringsmenyn och går till *[!UICONTROL Components]* > *[!UICONTROL Alerts]*. Mer information finns i [Översikt över aviseringar](/help/components/alerts/alerts-overview.md) i användarhandboken för komponenter.
