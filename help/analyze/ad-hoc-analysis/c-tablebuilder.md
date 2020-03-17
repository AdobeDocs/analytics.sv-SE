---
description: Använd tabellverktyget för att skapa en rapport med valfri konfiguration av mått, dimensioner och segment. Du kan till exempel lägga till flera mått i tabellverktyget och sedan använda segment på alla samtidigt. Du kan använda objekt från verktygspanelerna som rader och uppdelningar, eller som kolumner, och enkelt rotera tabellen för en annan vy. När du har skapat tabellen kan du interagera direkt med den resulterande datatabellen för ytterligare analys. Tänk på att när du genererar en datatabell från Table Builder körs en fråga och en ny datatabell skapas.
title: Table Builder
uuid: d5dbd05e-9ebd-4571-b3a5-3856c28b65f3
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Table Builder

Använd tabellverktyget för att skapa en rapport med valfri konfiguration av mått, dimensioner och segment. Du kan till exempel lägga till flera mått i tabellverktyget och sedan använda segment på alla samtidigt. Du kan använda objekt från verktygspanelerna som rader och uppdelningar, eller som kolumner, och enkelt rotera tabellen för en annan vy. När du har skapat tabellen kan du interagera direkt med den resulterande datatabellen för ytterligare analys. Tänk på att när du genererar en datatabell från Table Builder körs en fråga och en ny datatabell skapas.

## Table Builder {#concept_574FEDC73B244101935D3C86C39DB70F}

Använd tabellverktyget för att skapa en rapport med valfri konfiguration av mått, dimensioner och segment. Du kan till exempel lägga till flera mått i tabellverktyget och sedan använda segment på alla samtidigt. Du kan använda objekt från verktygspanelerna som rader och uppdelningar, eller som kolumner, och enkelt rotera tabellen för en annan vy. När du har skapat tabellen kan du interagera direkt med den resulterande datatabellen för ytterligare analys. Tänk på att när du genererar en datatabell från Table Builder körs en fråga och en ny datatabell skapas.

Det [!UICONTROL Table Builder] är inte tillgängligt för vissa betalningsrapporter som [!UICONTROL Site Analysis], [!UICONTROL Fallout]och [!UICONTROL Flow] [!UICONTROL Virtual Focus].

## Beskrivningar för tabellbyggaren {#section_4B7B96546B864142AB91DF3996918590}

<table id="table_C11D78E62DEF48A78B50EFB8669817BC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Rader/uppdelningar</span> </td> 
   <td colname="col2"> <p>Skapar rader och uppdelningar från tillagda objekt. Det första objektet som du drar till <span class="wintitle"> rader/uppdelningar</span> blir den vänstra kolumnen i datatabellen, eller det överordnade objektet i en uppdelning. Om du lägger till efterföljande objekt skapas uppdelningar. </p> <p>Om du t.ex. lägger till Page och sedan Cities-dimensioner, delas sidan upp efter städer. Med följande menyer kan du konfigurera hur många rader och uppdelningar som ska visas för varje objekt: </p> 
    <ul id="ul_702F215DFB814398B8F1879EDFEC103F"> 
     <li id="li_95C4DF2B33524C94BBD2E07397393300"> <span class="uicontrol"> Visa</span> och <span class="uicontrol"> dela upp</span>: Här kan du ange antalet objekt och uppdelningar som ska visas. </li> 
     <li id="li_D594C7F31A094D1EA1A070B80794E006"> <span class="uicontrol"> Standard</span>: Använder de inställningar som har konfigurerats i <span class="wintitle"> Egenskaper</span>för gruppindelning. </li> 
    </ul> <p>Du kan också konfigurera en lista med fasta värden så att du till exempel kan dela upp ett mätvärde med flera mätvärden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Egenskaper för uppdelning</span> </td> 
   <td colname="col2"> <p><img placement="inline"  src="assets/Settings_Illustrative.png" id="image_C46860621CF94E88AF592B8660F28E57"> </img> </p> <p>Här kan du ange standardinställningar för hur många rader och uppdelningar du vill visa, baserat på i vilken ordning du lägger till objekt. Du kan ange hur många totala resultat som ska visas per sida och hur många av raderna som ska delas upp. </p> <p>De inställningar du gör i <span class="wintitle"> tabellverktyget</span> åsidosätter standardinställningarna i <span class="wintitle"> Egenskaper</span>förnedbrytning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Redigera objekt</span> </td> 
   <td colname="col2"> <p><img  src="assets/Edit_Buttcon.png" id="image_E44BCC4B0BFF453D8564047E3DA2501A"> </img> </p> <p>Välj en lista med dimensionsobjekt om du vill skapa en fast lista för uppdelningar. När du lägger till objekt i den här listan blir de beständiga i en sparad rapport och komprimeras inte när du öppnar en sparad eller schemalagd rapport. </p> <p>Se <a href="/help/analyze/ad-hoc-analysis/c-reports-configure.md#task_29BEE0AF09DA4625B9B44BAB77D7C841"  > Dela upp tabelldata</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Kolumner</span> </td> 
   <td colname="col2"> <p>Gör att du kan skapa kolumner med objekt från dimensioner, segment och mätvärden. Du kan också vrida kolumnerna med hjälp av pilikonen som vrider X- och Y-axlarna. </p> <p> <span class="uicontrol"> Visa</span>: Du kan begränsa antalet kolumner som genereras i datatabellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Sammanfattning</span> </td> 
   <td colname="col2"> <p>Visar rapportens strukturlayout så att du vet hur många rader och kolumner som kommer att skapas. Sammanfattningen visar konfigurationen som anges i grupperna <span class="uicontrol"> Rader/Uppdelningar</span> och <span class="uicontrol"> Kolumner</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ersätt tabell</span> </td> 
   <td colname="col2"> <p>Skapar (och åsidosätter) den befintliga tabellen, baserat på din konfiguration av <span class="wintitle"> Table Builder</span> . </p> <p>Obs! Om du klickar på <span class="uicontrol"> Ersätt tabell</span> återskapas rapporten och data i tabellrutnätet åsidosätts. Om du lägger till objekt i tabellrutnätet är korrelationen mellan tabellen och <span class="wintitle"> tabellverktyget</span> inte längre giltig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Varning </td> 
   <td colname="col2"> <p><img id="image_619E1068C6084D41853DA3DD6B85DFC9"  src="assets/AlertRed_Illustrative.png" placement="inline" /> </p> <p>Anger att konfigurationen för <span class="wintitle"> tabellbyggaren</span>inte returnerar data eller att inga mått har valts. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Generera en rapport från Table Builder {#task_B04801AC9848485C93DF02E96C9A9902}

Steg som beskriver hur du använder [!UICONTROL Table Builder].

<!-- 

t_table_builder.xml

 -->

1. Om du vill få åtkomst till [!UICONTROL Table Builder]filen kör du en rapport som stöds och klickar sedan på **[!UICONTROL Table Builder]**.
1. Dra objekt (mått, mått, segment) från verktygspanelerna till [!UICONTROL Table Builder].
1. Konfigurera objekten som rader, uppdelningar och kolumner.
1. Klicka **[!UICONTROL Replace Table]** för att generera rapporten.

   När du klickar på **[!UICONTROL Replace Table]** körs en ny fråga och en ny datatabell skapas. Manuella redigeringar av detaljtabellen återspeglas inte i tabellverktyget.

