---
description: Det första steget när du skapar en begäran i Report Builder.
title: Dataförfrågningar – frågeguiden steg 1
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
role: Business Practitioner, Administrator
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 2%

---

# Dataförfrågningar – frågeguiden steg 1

I Request Wizard: Steg 1-formulär väljer du rapportsviten, rapporttyp, segment och konfigureringsdatum.

![](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**: Listan med rapportsviter som är tillgängliga för dig baserat på dina inloggningsuppgifter. Se [Välj rapportsviter](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Intervallväljare**: Gör att du kan välja ett rapportpaket-ID från en cell i Excel. Se [Välj rapportsviter](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segment**: Segment är anpassade datadeluppsättningar eller data som filtreras efter regler som du skapar. Segmenten baseras på träffar, besök och besökare. Se [Analytics Segmentation Guide](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html) för mer information om segment.

   Du kan till exempel köra ett [!UICONTROL Pages Report]-segment och sedan använda ett förstagångssegment.

1. **Tillåt åsidosättning** av publiceringslista: När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution. Publiceringslistor konfigureras i **[!UICONTROL Analytics]** > **[!UICONTROL Admin tools]**. Rapportsviten för den här begäran ersätts av det rapportsvits-ID som tilldelats varje mottagare i publiceringslistan. Se [Tillåt åsidosättning av publiceringslista](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md).

1. **Typ** av rapportering: Anger den basrapport som du vill köra i din databegäran. Du kör en rapport per begäran och den rapporten kan ha en-till-många-dimensioner och en-till-många-mått. Mätvärden och dimensioner för en rapporttyp visas i gränssnittet [!UICONTROL Request Wizard; Step 2]. Se [Välj rapporttyper](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **Datumintervall**: Definierar den tidsperiod som omfattas av begäran. Flera typer av begärandetidsperioder är tillgängliga, till exempel förinställning, fast och rullande. Det högsta antalet perioder är 366. Du kan också välja ett datumintervall som anges av en cell och spara datumintervall som mallar för senare bruk.  Se [Konfigurera rapportdatum](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **Använd granularitet**: Anger den tidsbaserade detaljnivå som ingår i rapporten. Se [Kornighet](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

## Felsökning

Ibland visas begärandeguiden utanför skärmen, särskilt för användare som växlar mellan skärminställningarna. Du kan till exempel använda en dockningsstation på jobbet och en skärm på din bärbara dator hemma. Om du klickar på Skapa igen när en begärandeguide redan är öppen visas följande fel:

&quot;Du måste först slutföra begärandeguiden innan du påbörjar en ny.&quot;

Problemet åtgärdas genom att begärandeguiden flyttas tillbaka till skärmen.

1. Öppna Microsoft Excel och logga in på Report Builder.
2. Klicka på [!UICONTROL Create], som öppnar begärandeguiden utanför skärmen.
3. Tryck på `[Alt]` + `[Space]`.
4. Tryck på `[M]`.
5. Tryck på någon av piltangenterna.
6. Flytta musen som kopplar begärandeguiden till markören
7. Klicka med musen för att släppa begärandeguiden på skärmen.
