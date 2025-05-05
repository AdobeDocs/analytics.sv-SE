---
description: Det finns två sätt att använda mätvärden i Analysis Workspace.
title: Mätvärden i Analysis Workspace
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: eb2b5e078fdb299ed7d82fed54e98e5a40059624
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 0%

---

# Mätvärden

Med mätvärden kan du kvantifiera datapunkter i Analysis Workspace. De används oftast som kolumner i en visualisering och är knutna till dimensioner.

## Typer av mätvärden

Adobe erbjuder flera typer av mätvärden som kan användas i Analysis Workspace:

* **Standardmått**: De flesta mätvärden som du använder i projekt är standardvärden. Exempel är [Sidvyer](/help/components/metrics/page-views.md), [Intäkter](/help/components/metrics/revenue.md) eller [Anpassade händelser](/help/components/metrics/custom-events.md). Mer information finns i [Metrisk översikt](/help/components/metrics/overview.md) i användarhandboken för komponenter.

  ![Standardmått](assets/standard-metric.png)

* **Beräknade mått**: Användardefinierade mått som baseras på standardvärden, statiska tal eller algoritmiska funktioner. Användardefinierade beräknade värden visar en räkneikon i listan över tillgängliga komponenter. Mer information finns i [Översikt över beräknade mått](/help/components/c-calcmetrics/cm-overview.md) i användarhandboken för komponenter.

  ![Beräknat mått](assets/calculated-metric.png)

* **Beräknade mätmallar**: Adobe-definierade mätvärden som beter sig på liknande sätt som beräknade mätvärden. Du kan använda dem som de är i Workspace-projekt eller spara en kopia för att anpassa dess logik. Mallar för beräknade mätvärden visar en Adobe-ikon i listan över tillgängliga komponenter.

  ![Mallen Beräknade mått](assets/calculated-metric-template.png)

## Använd mätvärden i Analysis Workspace

Mätvärden kan användas på olika sätt i Analysis Workspace. Mer information om hur du lägger till mått och andra typer av komponenter i Analysis Workspace finns i [Använda komponenter i Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Använd mätvärden](https://video.tv.adobe.com/v/40817?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

## Skapa beräknade mått

Beräknade mätvärden gör att du enkelt kan se hur mätvärdena relaterar till varandra med hjälp av enkla operatorer eller statistiska funktioner.

Det finns flera sätt att skapa beräknade mått. Den metod du väljer avgör om det beräknade måttet är tillgängligt från komponentlistan i alla projekt, eller bara i det projekt där det skapades.

### Skapa beräknade mätvärden för alla projekt

Du kan använda verktyget för beräknade mätvärden för att skapa beräknade mätvärden. När de skapas på det här sättet är beräknade värden tillgängliga i komponentlistan och kan sedan användas i projekt i hela organisationen.

Mer information om hur du får åtkomst till verktyget för beräknade värden finns i [Bygg mått](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

### Skapa beräknade mätvärden för ett enskilt projekt

Du kan snabbt skapa ett beräknat mått som bara är tillgängligt för det projekt där det skapades.

Så här skapar du ett beräknat mått för ett enskilt projekt:

1. Öppna det projekt i Analysis Workspace där du vill skapa det beräknade måttet.

1. Högerklicka på kolumnrubriken i en kolumn i en frihandstabell.

   eller

   Markera två kolumner samtidigt som du håller ned Skift och högerklicka sedan på en av de markerade kolumnerna.

1. Välj **[!UICONTROL Create metric from selection]**

   ![Markering av panelen Workspace Skapa från markering](assets/create-metric-from-selection.png)

1. Om du vill skapa ett beräknat mått för endast det här projektet väljer du bland de tillgängliga alternativen.

   När en kolumn är markerad är följande alternativ tillgängliga:

   * [!UICONTROL **Medel**]: Skapar en ny kolumn som visar medelvärdet i uppsättningen med dimensionselement för kolumnen. Detta använder funktionen [Medel](/help/components/c-calcmetrics/cm-reference/cm-functions.md#mean).

   * [!UICONTROL **Median**]: Skapar en ny kolumn som visar medianvärdet i uppsättningen med dimensionselement för kolumnen. Detta använder funktionen [Median](/help/components/c-calcmetrics/cm-reference/cm-functions.md#median).

   * [!UICONTROL **Kolumn max**]: Skapar en ny kolumn som visar det största värdet i uppsättningen med dimensionselement för kolumnen. Detta använder funktionen [Kolumnmaximum](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-maximum).

   * [!UICONTROL **Kolumn min**]: Skapar en ny kolumn som visar det minsta värdet i uppsättningen med dimensionselement för kolumnen. Detta använder funktionen [Kolumnminimum](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-minimum).

   * [!UICONTROL **Kolumnsumma**]: Skapar en ny kolumn som lägger till alla numeriska värden för ett mått i en kolumn (över elementen i en dimension). Detta använder funktionen [Kolumnsumma](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-sum).

   När två kolumner är markerade är följande alternativ tillgängliga:

   * [!UICONTROL **Dela upp**]: Skapar en ny kolumn som delar värdena för de två markerade kolumnerna.

   * [!UICONTROL **Subtrahera**]: Skapar en ny kolumn som subtraherar värdena för de två markerade kolumnerna.

   * [!UICONTROL **Lägg till**]: Skapar en ny kolumn som lägger till värdena för de två markerade kolumnerna.

   * [!UICONTROL **Multiplicera**]: Skapar en ny kolumn som multiplicerar värdena för de två markerade kolumnerna.

   * [!UICONTROL **Procentuell ändring**]: Skapar en ny kolumn som visar procentändringen mellan de två markerade kolumnerna.

[Beräknade mått: Mätvärden utan implementering](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=sv-SE) (3:42)

## Jämför mätvärden med olika attribueringsmodeller

Om du snabbt vill jämföra en attribueringsmodell med en annan högerklickar du på ett mått och väljer **[!UICONTROL Compare Attribution Models]**:

![Jämför attribuering](assets/compare-attribution.png)

Med den här genvägen kan du jämföra en attribueringsmodell med en annan utan att dra i ett mätresultat och konfigurera det två gånger.

## Använd funktionen [!UICONTROL cumulative average] för att använda måttutjämning

Här är en video om ämnet:


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Kumulativt genomsnitt](https://video.tv.adobe.com/v/27068?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

