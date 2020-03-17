---
description: Visar data om besökarens plats. GeoSegmentation-rapporterna omfattar Länder, Regioner, Städer, USA och USA DMA (Digital Marketing Area). GeoSegmenteringsrapporter är aktiverade för alla kunder.
title: GeoSegmentation
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# GeoSegmentation

Visar data om besökarens plats. GeoSegmentation-rapporterna omfattar Länder, Regioner, Städer, USA och USA DMA (Digital Marketing Area). GeoSegmenteringsrapporter är aktiverade för alla kunder.

Alla mätvärden som är tillgängliga för dig någon annanstans i Rapporter och analyser inkluderas automatiskt i rapporterna för länder, regioner, städer, USA och DMA: konverterings- och besöksbaserade mätvärden samt beräknade mätvärden. Mer information finns i det här Adobe- [blogginlägget](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) .

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rapport </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Länder </td> 
   <td colname="col2"> <p> Den största geografiska divisionen. Förutom de standardvyer för rankad och trender som finns i de flesta rapporter finns det också en kartvy som färgkodar länderna utifrån deras relativa bidrag till den totala trafiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Regioner </td> 
   <td colname="col2"> <p> Ett geografiskt område som är mindre än ett land men större än en stad. I vissa länder är en region en stat, provins eller prefektion. I andra områden är det ett land, en avdelning eller en storstadsregion. Landet i regionen visas också inom parentes till höger om varje region som visas. </p> <p>I tabelldetaljerna klickar du på Kör en stadsrapport för den här regionen (förstoringsglaset) för att köra en rapport som visar hur städerna i ett markerat område presterade jämfört med andra städer i regionen. </p> <p>Se <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > GeoSegmenteringsregioner och Postnummer per land</a> för att se vilka länder som använder regioner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Städer </td> 
   <td colname="col2"> <p> Den minsta geografiska divisionen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> USA </td> 
   <td colname="col2"> <p> En värmekarta som visar besökare i varje delstat i USA. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> U.S. DMA </td> 
   <td colname="col2"> <p> (Digital marketing area) Mediemarknadsindelningar för radio och tv i hela USA. Du kan filtrera rapporten så att den bara visar marknadsföringsområden i en viss stat. Dessa data tillhandahålls via ett partnerskap mellan Adobe och Nielsen Media Research, Inc. </p> <p>Obs!  The Unspecified entry in the U.S. DMA report anger besökare som inte kunde kopplas till en viss DMA. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rapportera noggrannhet </td> 
   <td colname="col2"> <p>Adobe samarbetar med Digital Envoy, en ledande leverantör av lösningar för IP-intelligens och -autentisering, för att kunna erbjuda GeoSegmentation, en geografisk mätfunktion som bygger på slutanvändarnas IP-adresser. Noggrannheten hos enskilda datauppsättningar kan variera, men i allmänhet ger Digital Envoy över 99 % precision på landsnivå, över 97 % precision på regionnivå och över 90 % precision på stadsnivå. </p> <p>Obs! Dessa nummer förutsätter att [inställningen] (/help/admin/admin/general-acct-settings-admin.md) för att ta bort den sista oktetten i IP-adressen INTE är aktiverad. </p> <p>IP-adresser mappas till postnummer och varje stad definieras av postnummer som definieras av den"lokala myndigheten" som en del av den staden. Exempelvis ingår inte Berlins förorter i definitionen av Berlin, men varje stad anges separat, förutsatt att IP-adresserna kan mappas korrekt till ett postnummer i någon av dessa städer. </p> <p>Några faktorer som kan påverka GeoSegmentation-data är: </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">IP-adresser som representerar företagsproxies. Dessa kan visas som trafik som kommer via användarens företagsnätverk, vilket faktiskt kan vara en annan plats om användaren arbetar fjärranslutet. </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">Mobila IP-adresser. Målgruppsanpassning för mobil IP fungerar på olika nivåer beroende på plats och nätverk. Ett antal transportföretag backar tillbaka IP-trafik genom centraliserade eller regionala POP. </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">IP-adresser som tillhör användare av Internet-leverantörer för satelliter. Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för den överordnade länken. </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">Militära och statliga immateriella tillgångar. Detta innebär ofta att personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade. </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">Våra GeoSegmentation/IP-data tillhandahålls av en tredjepartsleverantör och uppdateras regelbundet baserat på information från Internet-leverantörer och andra nätverkskällor. IP-sökningar är i sig instabila eftersom de köps och säljs ofta över hela världen. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

