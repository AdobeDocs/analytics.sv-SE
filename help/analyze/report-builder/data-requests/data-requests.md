---
description: 'null'
title: Databegäranden - Guiden Begär begäran, steg 1
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Databegäranden - Guiden Begär begäran, steg 1

I Request Wizard: Steg 1-formulär väljer du rapportsviten, rapporttyp, segment och konfigureringsdatum.

![](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**: Listan med rapportsviter som är tillgängliga för dig baserat på dina inloggningsuppgifter. Se [Välj rapportsviter](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Intervallväljare**: Gör att du kan välja ett rapportpaket-ID från en cell i Excel. Se [Välj rapportsviter](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segment**: Segment är anpassade datadeluppsättningar eller data som filtreras efter regler som du skapar. Segmenten baseras på träffar, besök och besökare. Mer information om segment finns i [segmentguiden](https://marketing.adobe.com/resources/help/en_US/analytics/segment/) för analys.

   Du kan till exempel köra ett [!UICONTROL Pages Report]och sedan använda segmentet Första gången du besöker.

1. **Tillåt åsidosättning** av publiceringslista: När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution. Publiceringslistor konfigureras i **[!UICONTROL Analytics]** > **[!UICONTROL Admin tools]**. Rapportsviten för den här begäran ersätts av det rapportsvits-ID som tilldelats varje mottagare i publiceringslistan. Se [Tillåt åsidosättning](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)av publiceringslista.

1. **Typ** av rapportering: Anger den basrapport som du vill köra i din databegäran. Du kör en rapport per begäran och den rapporten kan ha en-till-många-dimensioner och en-till-många-mått. Mätvärden och dimensioner för en rapporttyp visas i [!UICONTROL Request Wizard; Step 2] gränssnittet. Se [Välj rapporttyper](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **Datumintervall**: Definierar den tidsperiod som omfattas av begäran. Flera typer av begärandetidsperioder är tillgängliga, till exempel förinställning, fast och rullande. Det högsta antalet perioder är 366. Du kan också välja ett datumintervall som anges av en cell och spara datumintervall som mallar för senare bruk.  Se [Konfigurera rapportdatum](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **Använd granularitet**: Anger den tidsbaserade detaljnivå som ingår i rapporten. Se [Kornighet](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

>[!MORELIKETHIS]
>
>* [Skapa en dataförfrågan](/help/analyze/report-builder/data-requests/t-create-a-data-request.md)

