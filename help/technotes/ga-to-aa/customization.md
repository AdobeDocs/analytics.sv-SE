---
title: Anpassa rapporter i Adobe Analytics
description: Lär dig hur du anpassar rapporter i Adobe Analytics
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Anpassa rapporter

På tredjepartsplattformar som Google Analytics finns flera anpassningsalternativ tillgängliga. Med dessa anpassningar kan användare skapa kontrollpaneler, anpassade rapporter, sparade rapporter och anpassade aviseringar. Eftersom Analysis Workspace tillåter användare att skapa rapporter från en tom arbetsyta är de flesta anpassningar inbyggda direkt i verktyget.

På den här sidan förutsätts att användaren har grundläggande kunskaper i Analysis Workspace. Se [Skapa en grundläggande rapport i Analysis Workspace för Google Analytics-användare](reports/create-report.md) om du ännu inte känner till verktyget i Adobe Analytics.

## Kontrollpaneler

Analysis Workspaces har en arkitektur som liknar konceptet med instrumentpanelswidgetar. Projekt i Analysis Workspace är ungefär likvärdiga med kontrollpaneler i Google Analytics. Visualiseringar i Analysis Workspace motsvarar widgetar i Google Analytics.

### Lägga till innehåll i ett projekt

1. Klicka på ikonen Visualiseringar till vänster och dra önskad visualisering till arbetsytan.
2. Klicka på ikonen Komponenter till vänster och dra önskade mått och mätvärden till visualiseringen för att fylla i den med data.
3. Dra i kanterna av visualiseringen för att ändra storlek på den och dra i titeln på visualiseringen för att flytta den.

Alla Google Analytics-widgetar är tillgängliga i Analysis Workspace:

* Widgeten **Mått** är ungefär densamma som visualiseringen av sammanfattningsnummer.
* Widgeten **Tidslinje** är ungefär densamma som linjevisualiseringen.
* Widgeten **Geomap** är ungefär densamma som mappningsvisualiseringen.
* Widgeten **Tabell** är ungefär densamma som visualiseringen av frihandstabell.
* Cirkelwidgeten **är ungefär densamma som** dockningsvisualiseringen.
* Widgeten **Bar** är ungefär densamma som visualiseringen av staplar.

Analysis Workspace innehåller många fler visualiseringsalternativ för att presentera data på ett sätt som passar dina rapporteringsbehov bäst. Mer information finns i [Visualiseringar på arbetsytan](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) för analyser i användarhandboken för Analysera.

### Dela projekt

När du är klar med att lägga till innehåll i ett projekt kan du dela det.

* Om du vill dela projektet med dina kollegor går du till Dela > Dela projekt. Mottagare är andra användare i organisationen som har Adobe Analytics-konton.
* Om du vill dela ditt projekt via en länk går du till Dela > Hämta projektlänk. Observera att detta fortfarande kräver inloggning på Adobe Analytics i organisationen.

### Exportera projekt

Förutom PDF erbjuder Analysis Workspace en CSV-export.

1. Klicka *[!UICONTROL Share]* > *[!UICONTROL Send File Now]*, vilket öppnar ett modalt fönster.
2. Ange filtyp och mottagare.
3. Klicka på [!UICONTROL Send Now].

## Anpassade rapporter

När du skapar en anpassad rapport i Google Analytics liknar fälten som krävs arbetsflödet när du skapar en visualisering i arbetsytan. Dimensions-, Metrics- och Filter-definitionerna är lika mellan plattformarna. I Analysis Workspace, i stället för att välja mått och mätvärden från en lista, dras mått och mätvärden till en frihandstabell.

### Beräknade mått i anpassade rapporter

Anpassade rapporter är ett av de få områden i Google Analytics som tillåter användning av beräknade värden. Eftersom Analysis Workspace fungerar som en arbetsyta fungerar beräknade mätvärden retroaktivt och i alla sammanhang.

Så här skapar du ett beräknat mått:

1. Klicka på **+** -ikonen bredvid mätningslistan för att öppna verktyget för beräkning av mått.
2. Ge det beräknade måttet ett namn och ange ett format.
3. Dra metriska komponenter till definitionsområdet och använd listrutorna mellan varje komponent för att ange en operator.
4. När det beräknade måttet innehåller den önskade formeln klickar du på Spara för att gå tillbaka till arbetsytan.
5. Dra det nydefinierade beräknade måttet till arbetsytan.

   Läs mer om [Beräknade mått](/help/components/c-variables/c-metrics/calculated-metric.md) i användarhandboken för komponenter.

## Anpassade aviseringar

Varningar är tillgängliga på båda plattformarna. Använd rubriknavigeringsmenyn i Adobe Analytics och gå till *[!UICONTROL Components]* > *[!UICONTROL Alerts]*. Mer information finns i [Intelligent Alerts](/help/components/c-alerts/intellligent-alerts.md) i användarhandboken för komponenter.
