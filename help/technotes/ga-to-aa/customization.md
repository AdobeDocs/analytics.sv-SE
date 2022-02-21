---
title: Anpassa rapporter i Adobe Analytics
description: Lär dig hur du anpassar rapporter i Adobe Analytics
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# Anpassa rapporter

På tredjepartsplattformar som Google Analytics finns flera anpassningsalternativ tillgängliga. Med dessa anpassningar kan användare skapa kontrollpaneler, anpassade rapporter, sparade rapporter och anpassade aviseringar. Eftersom Analysis Workspace låter användare skapa rapporter från en tom arbetsyta är de flesta anpassningar inbyggda direkt i verktyget.

Den här sidan förutsätter att användaren har grundläggande kunskaper om att använda [!UICONTROL Analysis Workspace]. Se [Skapa en grundläggande rapport i Analysis Workspace för användare av Google Analytics](reports/create-report.md) om du ännu inte känner till verktyget i Adobe Analytics.

## Kontrollpaneler

The [!UICONTROL Analysis Workspace] arkitekturen har skapats på liknande sätt som konceptet med instrumentpanelswidgetar. Projekt i [!UICONTROL Analysis Workspace] är det ungefärliga som motsvarar kontrollpaneler i Google Analytics. Visualiseringar i [!UICONTROL Analysis Workspace] är den ungefärliga motsvarigheten till widgetar i Google Analytics.

### Lägga till innehåll i ett projekt

1. Klicka på [!UICONTROL Visualizations] till vänster och dra önskad visualisering till arbetsytan.
2. Klicka på [!UICONTROL Components] till vänster och dra önskade mått och mätvärden till visualiseringen för att fylla i den med data.
3. Dra i kanterna av visualiseringen för att ändra storlek på den och dra i titeln på visualiseringen för att flytta den.

Alla Google Analytics-widgetar är tillgängliga i [!UICONTROL Analysis Workspace]:

* The **Måttwidget** är ungefär lika med [!UICONTROL Summary Number] visualisering.
* The **Widget för tidslinje** är ungefär lika med [!UICONTROL Line] visualisering.
* The **Geomap-widget** är ungefär lika med [!UICONTROL Map] visualisering.
* The **Tabellwidget** är ungefär lika med [!UICONTROL Freeform Table] visualisering.
* The **Cirkelwidget** är ungefär lika med [!UICONTROL Donut] visualisering.
* The **Stolpwidget** är ungefär lika med [!UICONTROL Bar] visualisering.

[!UICONTROL Analysis Workspace] innehåller många fler visualiseringsalternativ för att presentera data på det sätt som passar bäst för dina rapporteringsbehov. Se [Visualiseringar i Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) i Analysera användarhandboken för mer information.

### Dela projekt

När du är klar med att lägga till innehåll i ett projekt kan du dela det.

* Om du vill dela projektet med dina kollegor går du till **[!UICONTROL Share > Share Project]**. Mottagare är andra användare i organisationen som har Adobe Analytics-konton.
* Om du vill dela ditt projekt via en länk går du till **[!UICONTROL Share > Get Project Link]**. Observera att detta fortfarande kräver inloggning på Adobe Analytics i din organisation.

### Exportera projekt

Förutom PDF [!UICONTROL Analysis Workspace] erbjuder en CSV-export.

1. Klicka *[!UICONTROL Share]* > *[!UICONTROL Send File Now]*, som öppnar ett modalt fönster.
2. Ange filtyp och mottagare.
3. Klicka på [!UICONTROL Send Now].

## Anpassade rapporter

När du skapar en anpassad rapport i Google Analytics liknar de fält som behövs arbetsflödet när du skapar en visualisering i arbetsytan. Definitionerna för Dimensioner, mått och filter är desamma mellan olika plattformar. I Analysis Workspace, i stället för att välja mått och mätvärden från en lista, dras mått och mätvärden till en frihandstabell.

### Beräknade mått i anpassade rapporter

Anpassade rapporter är ett av de få områden i Google Analytics som tillåter användning av beräknade värden. Eftersom Analysis Workspace fungerar som en arbetsyta fungerar beräknade mätvärden retroaktivt och i alla sammanhang.

Så här skapar du ett beräknat mått:

1. Klicka på **+** -ikonen nära metrisk lista för att öppna [!UICONTROL Calculated Metric Builder].
2. Ge det beräknade måttet ett namn och ange ett format.
3. Dra metriska komponenter till definitionsområdet och använd listrutorna mellan varje komponent för att ange en operator.
4. När det beräknade måttet innehåller den önskade formeln klickar du på Spara för att gå tillbaka till arbetsytan.
5. Dra det nydefinierade beräknade måttet till arbetsytan.

   Läs mer om [Beräknade mått](/help/components/c-calcmetrics/cm-overview.md) i användarhandboken för komponenter.

## Anpassade aviseringar

Varningar är tillgängliga på båda plattformarna. I Adobe Analytics använder du rubriknavigeringsmenyn och går till *[!UICONTROL Components]* > *[!UICONTROL Alerts]*. Se [Intelligenta aviseringar](/help/components/c-alerts/intellligent-alerts.md) i användarhandboken för komponenter om du vill ha mer information.
