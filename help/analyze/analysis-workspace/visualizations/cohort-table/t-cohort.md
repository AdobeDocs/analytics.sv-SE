---
description: Skapa en kohort och kör en kohortanalysrapport i Analysis Workspace.
keywords: Analysis Workspace
title: Köra en kohortanalysrapport
feature: Cohort Analysis
role: User, Admin
exl-id: 523e6f62-b428-454b-9460-6b06e96742c3
source-git-commit: 9f309319d67adb96cef6b1951c3ce485a57cd8da
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 0%

---

# Konfigurera en [!UICONTROL Cohort Analysis] rapport

Skapa en kohort och kör en [!UICONTROL Cohort Analysis] rapportera i Analysis Workspace.

1. I Analysis Workspace klickar du på **[!UICONTROL Visualizations]** ikonen i den vänstra listen och dra en **[!UICONTROL Cohort Table]** till arbetsytan.

   ![](assets/cohort-table.png)

1. Definiera **[!UICONTROL Inclusion Criteria]**, **[!UICONTROL Return Criteria]**, **[!UICONTROL Cohort Type]** och **[!UICONTROL Settings]** enligt definitionen i tabellen nedan.

   | Element | Beskrivning |
   |--- |--- |
   | **[!UICONTROL Inclusion Criteria]** | Du kan använda upp till 10 inkluderingssegment och upp till 3 inkluderingsvärden. Måttet anger vad som placerar en användare i en kohort. Om inkluderingsmåttet till exempel är Order, inkluderas endast användare som har gjort en beställning under kohortanalysens tidsintervall i den initiala kohorten.<br>Standardoperatorn mellan mätvärden är AND, men du kan ändra den till OR. Dessutom kan du lägga till numerisk filtrering i dessa mätvärden. Till exempel: &quot;Besök >= 1&quot;.</br> |
   | **[!UICONTROL Return Criteria]** | Du kan använda upp till 10 retursegment och upp till 3 returvärden. Måttet anger om användaren har behållits (kvarhållning) eller inte (bortfall). Om returvärdet till exempel är Videovyer visas bara de användare som visade videor under efterföljande tidsperioder (efter den period då de lades till i en kohort) som sparade. Ett annat mått som kvantifierar kvarhållandet är Besök. |
   | **[!UICONTROL Granularity]** | Tidsgranulariteten för dag, vecka, månad, kvartal eller år. |
   | **[!UICONTROL Type]** | **[!UICONTROL Retention]**(standard): En bevarandekohort mäter hur bra besökskohorterna återvänder till din egendom över tid. Det här är den standardkohort som vi alltid har haft och indikerar återkomst och upprepning av användarbeteende. A [!UICONTROL Retention] Kohort indikeras av den gröna färgen i tabellen.<br>**[!UICONTROL Churn]**: En bortfallskohort (kallas även&quot;attrition&quot; eller&quot;utfall&quot;) mäter hur besökarkohorterna faller bort från din egendom över tiden. Kurn = 1 - Kvarhållning. [!UICONTROL Churn] är ett bra mått på hur kantig och möjlig kunden är genom att visa hur ofta kunderna inte kommer tillbaka. Du kan använda urn för att analysera och identifiera fokusområden: vilka kohortsegment som skulle kunna behöva lite uppmärksamhet. A [!UICONTROL Churn] Kohort indikeras av den röda färgen i tabellen (liknar den som finns i **[!UICONTROL Flow]**visualisering).</br> |
   | **[!UICONTROL Settings]** | **[!UICONTROL Rolling Calculation]**: Beräkna kvarhållande eller bortfall baserat på föregående kolumn, i stället för kolumnen Inkluderat (standard). [!UICONTROL Rolling Calculation] ändrar beräkningsmetoden för dina&quot;retur&quot;-perioder. Vid den normala beräkningen hittas oberoende av användare som uppfyller&quot;returkriterierna&quot; och som var en del av inkluderingsperioden, oavsett om de var i kohorten för den föregående perioden eller inte. Istället [!UICONTROL Rolling Calculation] söker efter användare som uppfyller returkriterierna och som ingick i föregående period. Därför [!UICONTROL Rolling Calculation] filtrerar och trattar de användare som kontinuerligt uppfyller&quot;returkriterierna&quot; under en period. [!UICONTROL Return] kriterier tillämpas på var och en av de perioder som leder fram till den valda perioden. </br><br>**[!UICONTROL Latency Table]**: A [!UICONTROL Latency] tabell anger tiden som har gått före och efter det att inkluderingshändelsen inträffade. [!UICONTROL Latency] är bra att använda för-/efteranalys. Om du t.ex. har en kommande produkt eller en kampanj och vill spåra beteendet innan samt se hur det fungerar efter, kan du [!UICONTROL Latency] tabellen visar pre- och post-beteendet sida vid sida för att se den direkta effekten. Cellerna före inkludering i [!UICONTROL Latency] Tabellen beräknas av användare som uppfyller [!UICONTROL Inclusion] kriterierna för inkluderingsperioden och uppfyller sedan [!UICONTROL Return] i perioderna före inkluderingsperioden. Observera att [!UICONTROL Latency] tabeller och [!UICONTROL Custom Dimension] Kohort kan inte användas tillsammans.</br><br>**[!UICONTROL Custom Dimension Cohort]**: Skapa kohorter baserat på den valda dimensionen i stället för tidsbaserade kohorter (standard). Många kunder vill analysera sina kohorter med något annat än tid, och med den nya funktionen Custom Dimension Cohort kan du skapa kohorter baserat på de mått de själva väljer. Använd dimensioner som marknadsföringskanal, kampanj, produkt, sida, region eller någon annan dimension i Adobe Analytics för att visa hur kvarhållandet ändras baserat på de olika värdena för dessa dimensioner. The [!UICONTROL Custom Dimension] Kohortsegmentsdefinitionen tillämpar endast dimensionsobjektet som en del av inkluderingsperioden, inte som en del av returdefinitionen.</br><br>När du har valt [!UICONTROL Custom Dimension] Alternativet Kohort, du kan dra och släppa vilken dimension du vill i släppzonen. På så sätt kan du jämföra liknande dimensionsobjekt under samma tidsperiod. Du kan t.ex. jämföra prestanda för städer sida vid sida, produkter, kampanjer osv. Den returnerar dina 14 främsta dimensionsobjekt. Du kan emellertid använda ett filter (öppna det genom att hålla muspekaren åt höger om dimensionen som dragits på) för att endast visa önskade dimensionsobjekt. A [!UICONTROL Custom Dimension] Kohort kan inte användas med [!UICONTROL Latency] Tabellfunktion.</br> |

1. (Valfritt) Justera **[!UICONTROL Cohort Table Settings]** genom att klicka på kugghjulsikonen.

   | Inställning | Beskrivning | | Visa endast procent | Tar bort talvärdet och visar bara procentvärdet. | | Avrundar procent till närmaste heltal | Avrundar procentvärdet till närmaste heltal i stället för att visa decimalvärdet. | | Visa genomsnittlig procentrad | Infogar en ny rad högst upp i tabellen och lägger sedan till medelvärdet för värdena i varje kolumn. |

## Bygg [!UICONTROL Cohort Analysis] rapport

1. Klicka på **[!UICONTROL Build]**.

   ![Stegresultat](assets/cohort-report.png)

   Rapporten visar besökare som har lagt en order ( *`Included`* ) och som återvände till din webbplats vid efterföljande besök. Genom att antalet besök minskar över tid kan du upptäcka problem och vidta åtgärder.
1. (Valfritt) Skapa ett segment av en markering.

   Markera celler (angränsande eller icke-angränsande) och högerklicka sedan > **[!UICONTROL Create Segment From Selection]**.

1. I [Segment Builder](/help/components/segmentation/segmentation-workflow/seg-build.md)redigerar du segmentet ytterligare och klickar sedan på **[!UICONTROL Save]**.

   Det sparade segmentet kan användas i [!UICONTROL Segment] panel i [!UICONTROL Analysis Workspace].
1. Namnge och spara ditt kohortprojekt.
1. (Valfritt) [Kuratera och dela](/help/analyze/analysis-workspace/curate-share/curate.md) projektkomponenterna.

   >[!NOTE]
   >
   >Du måste spara projektet innan kursen är tillgänglig.

## Ladda ned en kohortvisualisering

Precis som med andra visualiseringar i Analysis Workspace kan du hämta en kohortvisualisering som en CSV- eller PDF-fil. Mer information finns i [Hämta PDF eller CSV-filer](/help/analyze/analysis-workspace/curate-share/download-send.md).
