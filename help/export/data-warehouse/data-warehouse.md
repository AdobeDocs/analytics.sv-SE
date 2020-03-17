---
description: Datalagret refererar till kopian av Analytics-data för lagring och anpassade rapporter, som du kan köra genom att filtrera data. Du kan begära rapporter för att visa avancerade datarelationer från rådata baserat på dina unika frågor. Datalagerrapporter skickas via e-post eller FTP och kan ta upp till 72 timmar att bearbeta. Bearbetningstiden beror på frågans komplexitet och mängden data som begärs.
title: Översikt över datalager
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Översikt över datalager

Datalagret refererar till kopian av Analytics-data för lagring och anpassade rapporter, som du kan köra genom att filtrera data. Du kan begära rapporter för att visa avancerade datarelationer från rådata baserat på dina unika frågor. Datalagerrapporter skickas via e-post eller FTP och kan ta upp till 72 timmar att bearbeta. Bearbetningstiden beror på frågans komplexitet och mängden data som begärs.

Adobe aktiverar Data Warehouse endast för användare på administratörsnivå för särskilda rapportsviter. (Den kan aktiveras för globala och underordnade rapportsviter, men inte för sammanslagningsrapportsviter.) Administratören kan skapa en grupp som har åtkomst till datalagret och sedan associera icke-administratörsnivåanvändare till den gruppen.

Data Warehouse packar automatiskt upp alla filer som är större än 1 MB. Den maximala storleken för e-postbilagor är 10 MB.

Datalagret kan bearbeta ett obegränsat antal rader i en enda begäran för enskilda schemalagda och nedladdade rapporter.

> [!NOTE] Datalagret rapporterar det första värdet som påträffats under rapporteringsperioden.

>[!IMPORTANT]
>
>När du segmenterar efter klassificerade värden behandlar Analysis Workspace och Data Warehouse &#39;unspecified&#39;-värden på olika sätt. &#39;Ospecificerad&#39; i arbetsytan avser värden som inte är klassificerade, medan &#39;Ospecificerad&#39; i datalagret refererar till värden som du klassificerat som &#39;Ospecificerad&#39;.

## Beskrivningar av förfrågningar från datalager {#section_F21C78ED36884C389C852E876AF5CDE8}

Tabellen beskriver fälten och alternativen på [!UICONTROL Data Warehouse Request] fliken.

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Namn på begäran</span> </td> 
   <td colname="col2"> Identifierar begäran. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Rapportdatum</span> </td> 
   <td colname="col2"> <p>Datum och kornighet för begäran. </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle"> Anpassad</span>: Ett datumintervall som du konfigurerar i kalendern. </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle"> Förinställning</span>: Ett förinställt intervall. Förinställningsintervallet är relativt rapportdatumet. </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle"> Kornighet</span>: Tidsgranulariteten. Giltiga värden är None, Hour, Day, Week, Month, Quarter och Year. </li> 
    </ul> <p>Datalagerrapportering för virtuella rapportsviter stöder den alternativa tidszon som har konfigurerats i den virtuella rapportsviten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tillgängliga segment</span> </td> 
   <td colname="col2"> <p>Gör att du kan markera den del av besökspopulationen som du vill granska och generera komplexa segment. Du kan läsa in förkonfigurerade segment, skapa nya segment och lagra segmentkomponenter i ett bibliotek och använda dem när du skapar ytterligare segment. </p> <p>Nu kan du stapla segment. När du markerar flera segment visas en kommaseparerad lista med namn (t.ex. Segment1, Segment2) i förhandsvisningsområdet, begärandehanteraren och popup-fönstret Frågedetaljer. </p> <p>Mer information finns i <a href="/help/components/c-segmentation/seg-home.md"> segmenteringshandboken</a> . </p> <p>Obs!  Du kan inte inkludera både ett segmentfilter och en uppdelning på samma segment i samma datalagerrapport. Om du gör det blir det ett fel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Uppdelningar</span> </td> 
   <td colname="col2"> <p>Gör att du kan kategorisera data med hjälp av uppdelningar. Segment och uppdelningar skiljer sig åt på så sätt att ett segment filtrerar data från en datauppsättning, medan en uppdelning delar upp data över alla giltiga värden för uppdelningen. </p> Du kan också dela upp en rapport i ett eller flera segment. Du kan dock inte inkludera både ett segmentfilter och en uppdelning på samma segment i samma datalagerrapport. Om du gör det blir det ett fel. <p> Du kan till exempel använda segment för att ta bort ett kön från datauppsättningen och använda en uppdelning för att se data separerade efter kön. </p> <p>När en begäran om datalager skickas med flera flervärdesdimensioner (t.ex. olika mobilrapporter), kan ett exponentiellt antal rader genereras från en enda träff. Antalet rader som kan skrivas ut från en enda träff är 100 (tidigare 1 000). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Mått</span> </td> 
   <td colname="col2">Gör att du kan lägga till mätvärden som du vill rapportera om. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Metrisk sortering</span> </td> 
   <td colname="col2">Tillhandahåller rankade uppdelningsrapporter, sorterade efter fallande måttvärde, som liknar det som visas i användargränssnittet för rapporter och analyser, Data Workbench osv. <a href="/help/export/data-warehouse/sorting-by-metric.md"  > Mer ...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Schemalägg leverans</span> </td> 
   <td colname="col2"> <p>Gör att du kan schemalägga begäranden om automatisk leverans vid valda intervall eller som en engångsrapport. Om du använder standardformatet kommer rapporten i ett e-postmeddelande som en CSV-fil. </p> <p>Lägg till datumintervallet genom att inkludera <span class="filepath"> %R</span> i filnamnet. Det här värdet representerar de datumvärden som begärs i rapporten. Om du till exempel begär data från 1 maj 2013 till 7 maj 2013 visar <span class="filepath"> %R</span> ett filnamn som inkluderar datumintervallet 20130501 till 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>

