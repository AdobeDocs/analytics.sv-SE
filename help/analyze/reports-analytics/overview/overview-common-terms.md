---
description: En introduktion till vanliga webbanalystermer som används i marknadsföringsrapporter.
title: Vanliga termer
uuid: 0560dc7d-9f92-46d4-848b-3cf297073382
feature: Rapporter, rapporter och analyser
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 3%

---


# Vanliga termer

En introduktion till vanliga Adobe Analytics-termer.

<table id="table_58F5D292485F45F9902B372E4E1E3103"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Term </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Report Suite </p> </td> 
   <td colname="col2"> <p>En rapportsvit definierar den fullständiga, oberoende rapporteringen på en vald webbplats, en uppsättning webbplatser eller en delmängd av webbplatssidor. Vanligtvis är en rapportserie en webbplats, men den kan vara ett globalt segment där du har kombinerat flera webbplatsers nummer för att få summor. En rapportsvit kan dessutom vara mindre än en webbplats om du vill köra rapporter för en del av webbplatsen. </p> <p>Om till exempel inloggade användare och icke inloggade användare använder din webbplats på ett annat sätt, och du har olika personer som tittar på rapporterna för varje grupp, kan du kategorisera rapportsviterna baserat på sidor som kräver autentisering och sidor som inte gör det. </p> <p>När du loggar in väljer du en rapportserie som ska användas (förutom när du använder sammanslagningar som kombinerar rapportsviter). </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Mått </p> </td> 
   <td> <p>Kvantitativ information om aktivitet på webbplatsen, t.ex. Vyer, klickningar, Läs in igen, Genomsnittlig tid, Datum, Enheter och så vidare. </p> <p>Mer information finns i <a href="/help/analyze/reports-analytics/metrics.md">Metrisk</a>. </p> </td> 
  </tr> 
  <tr> 
   <td> <p> Dimension </p> </td> 
   <td> <p>Beskrivningar eller egenskaper för mätdata som kan visas och jämföras, t.ex. kön, månad, ålder, lojalitet, skärmupplösning osv. </p> </td> 
  </tr> 
  <tr> 
   <td> <p> Rapport </p> </td> 
   <td> <p>Basen på funktioner för marknadsföringsrapporter. Du kan köra onlinerapporter på alla insamlade data. </p> <p>Mer information finns i <a href="/help/analyze/reports-analytics/reports.md"> Rapporttyper</a>. </p> </td> 
  </tr> 
  <tr> 
   <td> <p> Sidvisning </p> </td> 
   <td> <p>En enda webbsida som läses in i besökarens webbläsare. En sidvy är en körning av JavaScript-koden för den sidan. Systemet räknar exakt hur många gånger en sida läses in, även om besökaren uppdaterar sidan ofta eller använder webbläsarknapparna <span class="uicontrol"> Tillbaka</span> och <span class="uicontrol"> Läs in</span> igen. En sidvy räknar hela sidan, inte enskilda element eller träffar. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Gå in på </p> </td> 
   <td> <p>En sekvens med sidvisningar under en session. Besöken upphör först efter 30 minuters inaktivitet eller efter 12 timmars kontinuerlig aktivitet. (Den här gången är mätningen branschstandarden för webbanalys.) Besök spåras av cookies. Ett besök börjar när en läsare öppnar en sida. Ett besök kallas ibland för en <span class="term">-session</span>, men det är inte en webbläsarsession. Om du går till en annan webbplats, stänger webbläsaren eller till och med startar om datorn avslutas inte besöket. </p> <p> Om tidsgränsen för inaktivitet inträffar när en besökare läser en sida, stängs besöket och behandlas. Ett nytt besök börjar när besökaren klickar till en annan sida. </p> <p>Om datumet ändras under ett besök, t.ex. vid besök på en webbplats vid midnatt, beror besöket på den dag då besöket inleddes. </p> </td> 
  </tr> 
  <tr> 
   <td> <p> Unik besökare </p> </td> 
   <td> <p>Unika besökarrapporter anger antalet olika personer som besöker webbplatsen under en vald tid. Det finns sex olika unika besökarrapporter: </p> 
    <ul id="ul_863B8DE8B9E74DE4A93C2C2931EEFB6D"> 
     <li id="li_21C835B71EF64B4DA821B674416C8B85">Varje timme </li> 
     <li id="li_36A498AE7D7A455C8DEB3AA0F025B597">Dagligen </li> 
     <li id="li_30F26F8DAC664E1FA823B7BDDB7B0F8B">Veckovis </li> 
     <li id="li_09263F6B1E114A8DB477793B560A0417">Månadsvis </li> 
     <li id="li_A0B2CA3D44564045B02B55AF6E392F76">Kvartalsvis </li> 
     <li id="li_296BC5B02921460690F35128B1192800">Årlig </li> 
    </ul> <p>En person kan besöka webbplatsen flera gånger och visa flera sidor under en viss period, men i rapporten Unika besökare registreras den personen som en unik besökare. </p> <p> <b>Avduplicering</b> av besökare: Datainsamlingen tar bort dubbletter av besökare baserat på rapportrubriken, oberoende av kalendervalet. En besökare som till exempel besöker fyra separata dagar i en rapportvecka räknas som en i <span class="wintitle"> Veckounik besökarrapport</span>. I en <span class="wintitle"> daglig unik besökarrapport</span> som sträcker sig över den veckan räknas samma besökare fyra gånger. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Konverteringshändelser (slutförda) </p> </td> 
   <td> <p>Konverteringshändelser är de aktiviteter på din webbplats som du vill att andra ska göra (viktiga resultatindikatorer). För en e-handelsplats kan konverteringshändelser vara en detaljerad produktvy, en utcheckning eller ett köp. För en leadgenereringsplats kan händelsen vara en formulärkomplettering. Konverteringshändelser räknas på webbplatsen och har egna rapporter som visar hur många av dem som hände. Dessa händelser blir också mätvärden som kan användas i andra rapporter och kan visa varför konverteringshändelserna inträffade eller vad som bidrog till att de inträffade. </p> <p>Undantaget från regeln att en händelse ska bli ett mått är händelsen Purchase, som genererar tre mått: Intäkter, beställningar och enheter. </p> <p>Det finns fler konverteringsmått som inte definieras här, men konverteringsvärden utgör grunden för webbanalysen, som bygger på andra mätvärden och rapporter. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Kanal </p> </td> 
   <td> <p> Definierade avsnitt eller kategorier på din plats. Webbplatser som har två huvudkategorier, som <span class="term"> väder</span> och <span class="term"> nyheter</span>, har två kanaler. Du kan gruppera statistik för alla sidvyer som förekommer i valfri kanal på webbplatsen. </p> </td> 
  </tr> 
 </tbody> 
</table>

