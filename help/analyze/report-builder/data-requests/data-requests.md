---
description: Det första steget när du skapar en begäran i Report Builder.
title: Databegäranden - Guiden Begär begäran, steg 1
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
source-git-commit: 244af34b463ea5df55eaca31f3b2df4ada552b5d
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Databegäranden - Guiden Begär begäran, steg 1

I begärandeguiden: Steg 1 väljer du rapportsviten, rapporttyp, segment och konfigureringsdatum.

![Skärmbild som visar Request Wizard: Steg 1.](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**: Listan med rapportsviter som är tillgängliga för dig baserat på dina inloggningsuppgifter. Se [Välj rapportsviter](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Intervallväljare**: Gör att du kan välja ett rapportsvits-ID från en cell i Excel. Se [Välj rapportsviter](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segment**: Segment är anpassade datadeluppsättningar eller data som filtreras efter regler som du skapar. Segmenten baseras på träffar, besök och besökare. Se [Segmenteringshandbok för analyser](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html) för mer information om segment.

   Du kan till exempel köra en [!UICONTROL Pages Report]och sedan tillämpa ett segment för förstagångsbesök.

1. **Tillåt åsidosättning av publiceringslista**: Publiceringslistor var en funktion i Rapporter och analyser som har [slutprodukt](https://new.express.adobe.com/webpage/WFCyq7w8kijmB?).

1. **Typ av rapportering**: Anger den basrapport som du vill köra i din databegäran. Du kör en rapport per begäran och den rapporten kan ha en-till-många-dimensioner och en-till-många-mått. Mätvärden och dimensioner för en rapporttyp visas på [!UICONTROL Request Wizard; Step 2] gränssnitt. Se [Välj rapporttyper](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **Datumintervall**: Definierar den tidsperiod som omfattas av begäran. Flera typer av begärandetidsperioder är tillgängliga, till exempel förinställning, fast och rullande. Det högsta antalet perioder är 366. Du kan också välja ett datumintervall som anges av en cell och spara datumintervall som mallar för senare bruk.  Se [Konfigurera rapportdatum](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **Använd granularitet**: Anger den tidsbaserade detaljnivå som ingår i rapporten. Se [Kornighet](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

## Felsökning

Ibland visas begärandeguiden utanför skärmen, särskilt för användare som växlar mellan skärminställningarna. Du kan till exempel använda en dockningsstation på jobbet och en skärm på din bärbara dator hemma. Om du klickar på Skapa igen när en begärandeguide redan är öppen visas följande fel:

&quot;Du måste först slutföra begärandeguiden innan du påbörjar en ny.&quot;

Problemet åtgärdas genom att begärandeguiden flyttas tillbaka till skärmen.

1. Öppna Microsoft Excel och logga in på Report Builder.
2. Klicka [!UICONTROL Create]som öppnar begärandeguiden utanför skärmen.
3. Tryck `[Alt]` + `[Space]`.
4. Tryck `[M]`.
5. Tryck på någon av piltangenterna.
6. Flytta musen som kopplar begärandeguiden till markören
7. Klicka med musen för att släppa begärandeguiden på skärmen.
