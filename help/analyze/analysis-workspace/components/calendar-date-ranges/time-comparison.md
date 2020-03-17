---
description: Med Datumjämförelse på arbetsytan för analyser kan du ta valfri kolumn som innehåller ett datumintervall och skapa en gemensam datumjämförelse, till exempel år-över-år, kvartal-över-kvartal, månad-över-månad.
title: Datumjämförelse
uuid: ef18f9d9-b6ad-4859-b7c9-9750ca0df519
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Datumjämförelse

Med Datumjämförelse på arbetsytan för analyser kan du ta valfri kolumn som innehåller ett datumintervall och skapa en gemensam datumjämförelse, till exempel: år-över-år, kvartal-över-kvartal, månad-över-månad osv.

## Jämför tidsperioder {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

Analysen kräver ett sammanhang, och ofta tillhandahålls detta sammanhang av en tidigare tidsperiod. Till exempel frågan&quot;Hur mycket bättre/sämre gör vi nu än i fjol?&quot; är grundläggande för att förstå er verksamhet. Datumjämförelse innehåller automatiskt en&quot;differenskolumn&quot;, som visar den procentuella ändringen jämfört med en angiven tidsperiod.

1. Skapa en frihandstabell med alla mått och mätvärden som du vill jämföra under en tidsperiod.
1. Högerklicka på en tabellrad och välj **[!UICONTROL Compare Time Periods]**.

   ![](assets/compare-time.png)

   >[!IMPORTANT]
   >
   >Det här högerklicksalternativet är inaktiverat för måttrader, datumintervallrader och tidsdimensionsrader.

1. Beroende på hur du har angett tabellens datumintervall kan du göra följande jämförelser:

   | Alternativ | Beskrivning |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Jämför med vecka/månad/osv. omedelbart före detta datumintervall. |
   | **[!UICONTROL This week/month/quarter/year last year]** | Jämför med samma datumintervall för ett år sedan. |
   | **[!UICONTROL Select range]** | Gör att du kan välja ett anpassat datumintervall. |

   >[!NOTE]
   >
   >När du väljer ett anpassat antal dagar, till exempel 7 oktober-20 oktober (ett 14-dagarsintervall), får du bara två alternativ: **[!UICONTROL Prior 14 days before this date range]**, och **[!UICONTROL Select range]**.

1. Jämförelsen ser ut så här:

   ![](assets/compare-time-result.png)

   Rader i kolumnen Procent ändring visas som röda för negativa värden och gröna för positiva värden.

1. (Valfritt) Som i andra Workspace-projekt kan du skapa visualiseringar baserat på dessa tidsjämförelser. Här är ett stolpdiagram:

   ![](assets/compare-time-barchart.png)

   Observera att om du vill visa den procentuella ändringen i stapeldiagrammet måste inställningen vara markerad i [!UICONTROL Percentages] fältet [!UICONTROL Visualization Settings].

## Lägg till en tidsperiodkolumn för jämförelse {#section_93CC2B4F48504125BEC104046A32EB93}

Nu kan du lägga till en tidsperiod för varje kolumn i en tabell, så att du kan lägga till en annan tidsperiod än den som du har angett för kalendern. Detta är ett annat sätt att jämföra datum.

1. Högerklicka på en kolumn i tabellen och välj **[!UICONTROL Add Time Period Column]**![](assets/add-time-period-column.png)

1. Beroende på hur du har angett tabellens datumintervall kan du göra följande jämförelser:

   | Alternativ | Beskrivning |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Lägger till en kolumn med veckan/månaden/osv. omedelbart före detta datumintervall. |
   | **[!UICONTROL This week/month/quarter/year last year]** | Lägger till samma datumintervall för ett år sedan. |
   | **[!UICONTROL Select range]** | Gör att du kan välja ett anpassat datumintervall. |

   >[!NOTE]
   >
   >När du väljer ett anpassat antal dagar, till exempel 7 oktober-20 oktober (ett 14-dagarsintervall), får du bara två alternativ: **[!UICONTROL Prior 14 days before this date range]**, och **[!UICONTROL Select range]**.

1. Tidsperioden infogas ovanpå den markerade kolumnen:

   ![](assets/add-time-period-column2.png)

1. Du kan lägga till så många tidskolumner du vill och blanda och matcha olika datumintervall:

   ![](assets/add-time-period-column4.png)

1. Du kan dessutom sortera efter varje kolumn, vilket ändrar ordningen på dagar beroende på vilken kolumn du sorterar efter.

## Justera kolumndatum så att de börjar på samma rad {#section_5085E200082048CB899C3F355062A733}

Du kan använda en ny inställning för alla tabeller **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]**. &quot;Gäller hela tabellen&quot; betyder att om du t.ex. gör en uppdelning i tabellen, och om du ändrar den här inställningen för uppdelningen, så ändras inställningen för hela tabellen.

![](assets/date-comparison-setting.png)

>[!IMPORTANT]
>
>Den här inställningen är **inaktiverad** (avmarkerad) för alla befintliga projekt och **aktiverad** (markerad) för alla nya projekt.

Exempel: Om du väljer att justera datumen och gör en månadsvis jämförelse mellan oktober och september 2016 börjar den vänstra kolumnen med 1 oktober och den högra kolumnen börjar med 1 september:

![](assets/add-time-period-column3.png)

<!-- 

<p>See Jonny Moon's email from November 3. </p>

 -->

