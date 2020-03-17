---
description: Skapa en kohort och kör en kohortanalysrapport i Analysis Workspace.
keywords: Analysis Workspace
title: Köra en kohortanalysrapport
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Konfigurera en kohortanalysrapport

Skapa en kohort och kör en kohortanalysrapport i Analysis Workspace.

1. Klicka på **[!UICONTROL Visualizations]** ikonen i den vänstra listen på arbetsytan och dra en bild **[!UICONTROL Cohort Table]** till arbetsytan.

   ![](assets/cohort-table.png)

1. Definiera **[!UICONTROL Inclusion Criteria]**, **[!UICONTROL Return Criteria]**, **[!UICONTROL Cohort Type]** och **[!UICONTROL Settings]** enligt tabellen nedan.

| Element | Beskrivning |
|--- |--- |
| **[!UICONTROL Inclusion Criteria]** | Du kan använda upp till 10 inkluderingssegment och upp till 3 inkluderingsvärden. Måttet anger vad som placerar en användare i en kohort. Om inkluderingsmåttet till exempel är Order, inkluderas endast användare som har gjort en beställning under kohortanalysens tidsintervall i den initiala kohorten.<br>Standardoperatorn mellan mätvärden är AND, men du kan ändra den till OR. Dessutom kan du lägga till numerisk filtrering i dessa mätvärden. Till exempel: &quot;Besök >= 1&quot;.</br> |
| **[!UICONTROL Return Criteria]** | Du kan använda upp till 10 retursegment och upp till 3 returvärden. Måttet anger om användaren har behållits (kvarhållning) eller inte (bortfall). Om returvärdet till exempel är Videovyer visas bara de användare som visade videor under efterföljande tidsperioder (efter den period då de lades till i en kohort) som sparade. Ett annat mått som kvantifierar kvarhållandet är Besök. |
| **[!UICONTROL Granularity]** | Tidsgranulariteten för dag, vecka, månad, kvartal eller år. |
| **[!UICONTROL Type]** | **[!UICONTROL Retention]**(standard): En bevarandekohort mäter hur bra besökskohorterna återvänder till din egendom över tid. Det här är den standardkohort som vi alltid har haft och indikerar återkomst och upprepning av användarbeteende. En bevarandekohort anges med den gröna färgen i tabellen.<br>**[!UICONTROL Churn]**: En bortfallskohort (kallas även&quot;attrition&quot; eller&quot;utfall&quot;) mäter hur besökarkohorterna faller bort från din egendom över tiden. Kurn = 1 - Kvarhållning. Churn är ett bra mått på kantighet och möjligheter genom att visa hur ofta kunderna inte kommer tillbaka. Du kan använda urn för att analysera och identifiera fokusområden: vilka kohortsegment som skulle kunna behöva lite uppmärksamhet. En Churn Cohort indikeras av den röda färgen i tabellen (liknar den som används i vår **[!UICONTROL Flow]** visualisering).</br> |
| **[!UICONTROL Settings]** | **[!UICONTROL Rolling Calculation]**: Beräkna kvarhållande eller bortfall baserat på föregående kolumn, i stället för kolumnen Inkluderat (standard). Rullande beräkning ändrar beräkningsmetoden för dina&quot;returperioder&quot;. Vid den normala beräkningen hittas oberoende av användare som uppfyller&quot;returkriterierna&quot; och som var en del av inkluderingsperioden, oavsett om de var i kohorten för den föregående perioden eller inte. Rullande beräkning hittar i stället användare som uppfyller returkriterierna och som var en del av föregående period. Därför filtrerar och fördelar rullande beräkning de användare som kontinuerligt uppfyller&quot;returkriterierna&quot; under perioden. Returkriterier används för var och en av perioderna som leder fram till den valda perioden. </br><br>**[!UICONTROL Latency Table]**: En latenstabell anger den tid som har gått före och efter det att inkluderingshändelsen inträffade. Fördröjning är bra att använda för-/efteranalys. Om du till exempel har en kommande produkt eller en kampanjstart och du vill spåra beteendet innan samt se hur det fungerar efter, visar latenstabellen beteendet sida vid sida för att se den direkta effekten. Cellerna före inkludering i latenstabellen beräknas av användare som uppfyller&quot;inkluderingskriterierna&quot; i inkluderingsperioden och sedan uppfyller&quot;returkriterierna&quot; under perioderna före inkluderingsperioden. Observera att latenstabeller och Custom Dimension Cohort inte kan användas tillsammans.</br><br>**[!UICONTROL Custom Dimension Cohort]**: Skapa kohorter baserat på den valda dimensionen i stället för tidsbaserade kohorter (standard). Många kunder vill analysera sina kohorter med något annat än tid, och den nya funktionen Custom Dimension Cohort ger dig flexibilitet att skapa kohorter baserat på de mått de väljer. Använd dimensioner som marknadsföringskanal, kampanj, produkt, sida, region eller någon annan dimension i Adobe Analytics för att visa hur kvarhållandet ändras baserat på de olika värdena för dessa dimensioner. Segmentdefinitionen för Custom Cohort Dimension tillämpar endast dimensionsobjektet som en del av inkluderingsperioden, inte som en del av returdefinitionen.</br><br>När du har valt alternativet Egen dimensionskohort kan du dra och släppa vilken dimension du vill i släppzonen. På så sätt kan du jämföra liknande dimensionsobjekt under samma tidsperiod. Du kan t.ex. jämföra prestanda för städer sida vid sida, produkter, kampanjer osv. Den returnerar dina 14 främsta dimensionsobjekt. Du kan emellertid använda ett filter (öppna det genom att hålla muspekaren åt höger om dimensionen som dragits) för att visa endast önskade dimensionsobjekt. Det går inte att använda en anpassad dimensionskohort med funktionen för svarstabell.</br> |

1. Justera **[!UICONTROL Cohort Table Settings]** genom att klicka på kugghjulsikonen.

| Inställning| Beskrivning|| Visa endast procent| Tar bort talvärdet och visar bara procentvärdet. || Avrundar procent till närmaste heltal| Avrundar procentvärdet till närmaste heltal i stället för att visa decimalvärdet. || Visa genomsnittlig procentrad| Infogar en ny rad högst upp i tabellen och lägger sedan till medelvärdet för värdena i varje kolumn. |

## Skapa rapporten för kohortanalys

1. Klicka på **[!UICONTROL Build]**.

   ![Stegresultat](assets/cohort-report.png)

   I rapporten visas besökare som har gjort en beställning ( *`Included`* kolumn) och som har återvänt till din webbplats vid efterföljande besök. Genom att antalet besök minskar över tid kan du upptäcka problem och vidta åtgärder.
1. (Valfritt) Skapa ett segment av en markering.

   Markera celler (angränsande eller icke-angränsande) och högerklicka sedan > **[!UICONTROL Create Segment From Selection]**.

1. I [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html)redigerar du segmentet ytterligare och klickar sedan på **[!UICONTROL Save]**.

   Det sparade segmentet är tillgängligt för användning på [!UICONTROL Segment] panelen i Analysis Workspace.
1. Namnge och spara ditt kohortprojekt.
1. (Valfritt) [Kuratera och dela](/help/analyze/analysis-workspace/curate-share/curate.md) projektkomponenterna.

   >[!NOTE]
   >
   >Du måste spara projektet innan kursen är tillgänglig.

