---
description: Med Datumjämförelse i Analysis Workspace kan du ta vilken kolumn som helst som innehåller ett datumintervall och skapa en gemensam datumjämförelse, till exempel år för år, kvartal för kvartal, månad för månad.
title: Datumjämförelse
feature: Calendar
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 5%

---

# Datumjämförelse

Med Datumjämförelse i Analysis Workspace kan du ta vilken kolumn som helst som innehåller ett datumintervall och skapa en gemensam datumjämförelse, till exempel år-över-år, kvartal-över-kvartal, månad-över-månad osv.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Datumjämförelse](https://video.tv.adobe.com/v/30753?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]



## Jämför tidsperioder {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

>[!NOTE]
>[!UICONTROL Compare Time Periods] använder avancerade beräknade värden. Det innebär att det endast är tillgängligt för kunder med SKU:erna i Analytics Select, Prime och Ultimate.

Analysen kräver ett sammanhang, och ofta tillhandahålls detta sammanhang av en tidigare tidsperiod. Till exempel frågan&quot;Hur mycket bättre eller värre är det vi gör nu än i fjol?&quot; är grundläggande för att förstå er verksamhet. Datumjämförelse innehåller automatiskt en&quot;differenskolumn&quot;, som visar den procentuella ändringen jämfört med en angiven tidsperiod.

1. Skapa en frihandstabell med alla mått och mätvärden som du vill jämföra under en tidsperiod.
1. Högerklicka på en tabellrad och välj **[!UICONTROL Compare time periods]**.

   ![](assets/compare-time.png)

   >[!NOTE]
   >
   >Det här högerklicksalternativet är inaktiverat för måttrader, datumintervallrader och tidsdimensionsrader.

1. Beroende på hur du har angett tabellens datumintervall kan du göra följande jämförelser:

   | Alternativ | Beskrivning |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Jämför med vecka/månad/osv. omedelbart före detta datumintervall. |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Jämför med samma datumintervall för ett år sedan. |
   | **[!UICONTROL Custom date range to this date range]** | Gör att du kan välja ett anpassat datumintervall. |

   >[!NOTE]
   >
   >När du väljer ett anpassat antal dagar, till exempel 7 oktober-20 oktober (ett 14-dagarsintervall), får du bara två alternativ: **[!UICONTROL Prior 14 days before this date range]** och **[!UICONTROL Custom date range to this date range]**.

1. Jämförelsen ser ut så här:

   ![](assets/compare-time-result.png)

   Rader i kolumnen Procent ändring visas som röda för negativa värden och gröna för positiva värden.

1. (Valfritt) Som i andra Workspace-projekt kan du skapa visualiseringar baserat på dessa tidsjämförelser. Här är ett stolpdiagram:

   ![](assets/compare-time-barchart.png)

   Observera att om du vill visa den procentuella ändringen i stapeldiagrammet måste inställningen [!UICONTROL Percentages] vara markerad i [!UICONTROL Visualization Settings].

## Lägg till en tidsperiodkolumn för jämförelse {#section_93CC2B4F48504125BEC104046A32EB93}

Nu kan du lägga till en tidsperiod i varje kolumn i en tabell, så att du kan lägga till en annan tidsperiod än den som du har angett för kalendern. Detta är ett annat sätt att jämföra datum.

1. Högerklicka på en kolumn i tabellen och välj **[!UICONTROL Add time period column]**.

   ![](assets/add-time-period-column.png)

1. Beroende på hur du har angett tabellens datumintervall kan du göra följande jämförelser:

   | Alternativ | Beskrivning |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Lägger till en kolumn med veckan/månaden/osv. omedelbart före detta datumintervall. |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Lägger till samma datumintervall för ett år sedan. |
   | **[!UICONTROL Custom date range to this date range]** | Gör att du kan välja ett anpassat datumintervall. |

   >[!NOTE]
   >
   >När du väljer ett anpassat antal dagar, till exempel 7 oktober-20 oktober (ett 14-dagarsintervall), får du bara två alternativ: **[!UICONTROL Prior 14 days before this date range]** och **[!UICONTROL Custom date range to this date range]**.

1. Tidsperioden infogas ovanpå den markerade kolumnen:

   ![](assets/add-time-period-column2.png)

1. Du kan lägga till så många tidskolumner du vill och blanda och matcha olika datumintervall:

   ![](assets/add-time-period-column4.png)

1. Du kan dessutom sortera efter varje kolumn, vilket ändrar ordningen på dagar beroende på vilken kolumn du sorterar efter.

## Justera kolumndatum så att de startar på samma rad {#section_5085E200082048CB899C3F355062A733}

Du kan justera datumen från varje kolumn så att alla börjar på samma rad.

Om du till exempel väljer att justera datumen och gör en månadsvis jämförelse mellan oktober och september 2016, börjar den vänstra kolumnen med 1 oktober och den högra kolumnen börjar med 1 september:

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Tänk på följande när du använder det här alternativet:
>
>* Den här inställningen är aktiverad som standard för alla nya projekt.
>
>* Den här inställningen gäller för hela tabellen. Om du t.ex. ändrar den här inställningen för en uppdelning i tabellen, ändras inställningen för hela tabellen.
>

Om du vill aktivera den här inställningen om den inte redan är aktiverad:

1. I tabellen där du vill justera kolumndatum markerar du ikonen **Inställningar** i tabellhuvudet.

1. Välj **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]** på fliken [!UICONTROL **Inställningar**].

![](assets/date-comparison-setting.png)


