---
description: Data warehouse refererar till kopian av Analytics-data för lagring och anpassade rapporter, som du kan köra genom att filtrera data. Du kan begära rapporter för att visa avancerade datarelationer från rådata baserat på dina unika frågor. Data warehouse-rapporter skickas via e-post eller FTP och kan ta upp till 72 timmar att behandla. Bearbetningstiden beror på frågans komplexitet och mängden data som begärs.
title: Översikt över Data Warehouse
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 1%

---

# Översikt över Data Warehouse

data warehouse refererar till kopian av Analytics-data för lagring och anpassade rapporter, som du kan köra genom att filtrera data. Du kan begära rapporter för att visa avancerade datarelationer från rådata baserat på dina unika frågor. Data warehouse-rapporter skickas via e-post eller FTP och kan ta upp till 72 timmar att behandla. Bearbetningstiden beror på frågans komplexitet och mängden data som begärs.

Adobe aktiverar endast Data warehouse för användare på administratörsnivå för särskilda rapportsviter. (Den kan aktiveras för globala och underordnade rapportsviter, men inte för sammanslagningsrapportsviter.) Administratören kan skapa en grupp som har åtkomst till Data warehouse och sedan associera icke-administratörsnivåanvändare till den gruppen.

data warehouse packar automatiskt alla filer som är större än 1 MB. Den maximala storleken för e-postbilagor är 10 MB.

data warehouse kan bearbeta ett obegränsat antal rader i en och samma begäran för enskilda schemalagda och nedladdade rapporter.

>[!NOTE]
>
>data warehouse rapporterar det första värdet som påträffats under rapporteringsperioden.

>[!IMPORTANT]
>
>Vid segmentering på klassificerade värden behandlar Analysis Workspace och Data warehouse &#39;ospecificerade&#39; värden annorlunda. &#39;Ospecificerad&#39; i arbetsytan avser värden som inte är klassificerade, medan &#39;Ospecificerad&#39; i Data warehouse avser värden som du klassificerat som &#39;Ospecificerad&#39;.

## Beskrivningar av förfrågningar från Data warehouse {#section_F21C78ED36884C389C852E876AF5CDE8}

Tabellen beskriver fälten och alternativen på [!UICONTROL Data Warehouse Request] -fliken.

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
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle"> Egen</span>: Ett datumintervall som du konfigurerar i kalendern. </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle"> Förinställning</span>: Ett förinställt intervall. Förinställningsintervallet är relativt rapportdatumet. </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle"> Kornighet</span>: Tidsgranulariteten. Giltiga värden är None, Hour, Day, Week, Month, Quarter och Year. </li> 
    </ul> <p>Rapportering från data warehouse i virtuella rapportsviter har stöd för den alternativa tidszon som har konfigurerats i den virtuella rapportsviten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tillgängliga segment</span> </td> 
   <td colname="col2"> <p>Gör att du kan markera den del av besökspopulationen som du vill granska och generera komplexa segment. Du kan läsa in förkonfigurerade segment, skapa nya segment och lagra segmentkomponenter i ett bibliotek och använda dem när du skapar ytterligare segment. </p> <p>Nu kan du stapla segment. När du markerar flera segment visas en kommaseparerad lista med namn (t.ex. Segment1, Segment2) i förhandsvisningsområdet, begärandehanteraren och popup-fönstret Frågedetaljer. </p> <p>Se <a href="/help/components/segmentation/seg-home.md"> Segmenteringshandbok</a> för mer information. </p> <p>Obs! Du kan inte inkludera både ett segmentfilter och en uppdelning på samma segment i samma Data warehouse-rapport. Om du gör det blir det ett fel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Uppdelningar</span> </td> 
   <td colname="col2"> <p>Gör att du kan kategorisera data med hjälp av uppdelningar. Segment och uppdelningar skiljer sig åt på så sätt att ett segment filtrerar data från en datauppsättning, medan en uppdelning delar upp data över alla giltiga värden för uppdelningen. </p> Du kan också dela upp en rapport i ett eller flera segment. Du kan dock inte inkludera både ett segmentfilter och en uppdelning på samma segment i samma Data warehouse-rapport. Om du gör det blir det ett fel. <p> Du kan till exempel använda segment för att ta bort ett kön från datauppsättningen och använda en uppdelning för att se data separerade efter kön. </p> <p>När en Data warehouse-begäran skickas med flera flervärdesdimensioner (t.ex. olika Mobile Reports), kan ett exponentiellt antal rader genereras från en enda träff. Antalet rader som kan skrivas ut från en enda träff är 100 (tidigare 1 000). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Mätvärden</span> </td> 
   <td colname="col2">Gör att du kan lägga till mätvärden som du vill rapportera om. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Metrisk sortering</span> </td> 
   <td colname="col2">Tillhandahåller rankade uppdelningsrapporter, sorterade efter fallande mätvärden, som liknar det som visas i användargränssnittet för Rapporter och analyser, Data Workbench osv. <a href="/help/export/data-warehouse/sorting-by-metric.md"  > Mer...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Schemalägg leverans</span> </td> 
   <td colname="col2"> <p>Gör att du kan schemalägga begäranden om automatisk leverans vid valda intervall eller som en engångsrapport. Om du använder standardformatet kommer rapporten i ett e-postmeddelande som en CSV-fil. </p> <p>Lägg till datumintervallet genom att inkludera <span class="filepath"> %R</span> i filnamnet. Det här värdet representerar de datumvärden som begärs i rapporten. Om du till exempel begär data från 1 maj 2013 till 7 maj 2013 är <span class="filepath"> %R</span> visar ett filnamn inklusive datumintervallet 20130501 - 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>
