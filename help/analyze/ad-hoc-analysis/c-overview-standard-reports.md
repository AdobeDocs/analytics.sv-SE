---
description: Standardrapporter visar data för webbplats- och besöksaktivitet, trafikmönster, referensdata, annonskampanjer, besökarlojalitet, produktdata med mera. Du kan köra rapporter och sedan komma åt verktyg för att konfigurera segment, mätvärden och rapportjämförelser.
title: Översikt över rapporter
topic: Ad hoc analysis
uuid: 36722dcd-5dc9-4047-8a17-16de876193bf
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Översikt över rapporter

Standardrapporter visar data för webbplats- och besöksaktivitet, trafikmönster, referensdata, annonskampanjer, besökarlojalitet, produktdata med mera. Du kan köra rapporter och sedan komma åt verktyg för att konfigurera segment, mätvärden och rapportjämförelser.

## Översikt över rapporter {#concept_41459A705F2048EEA4EFA80F6BD9FFAB}

Standardrapporter visar data för webbplats- och besöksaktivitet, trafikmönster, referensdata, annonskampanjer, besökarlojalitet, produktdata med mera. Du kan köra rapporter och sedan komma åt verktyg för att konfigurera segment, mätvärden och rapportjämförelser.

Du kan samla in anpassade data för att skapa rapporter som är specifika för din webbplats. Om du till exempel har en sökfunktion på webbplatsen kan du spåra de sökord som skickats in och skapa en rapport som visar dessa termer och sökresultaten.

Standarduppsättningen med rapporter omfattar ämnen som är gemensamma för alla webbplatser. Rapporterna innehåller (men är inte begränsade till):

* Webbplatsdata
* Besöksdata
* Trafikmönster
* Referensdata
* Annonskampanjer
* Bevarande av besökare
* Produktinformation

Om ni använder marknadsföringsrapporter och analyser är rapporttyperna och menyerna bekanta. Ad hoc-analyser kategoriserar rapporter baserat på följande typer:

**Sammanfattningsrapporter**

Inkluderar rapporter som [!UICONTROL Totals Report]t.ex. Dessa är avsedda för chefer som vill ha en allmän översikt över data.

**Konverteringsrapporter**

Konverteringsrapporter ger omfattande, korrekt och detaljerad analys av kundaktiviteter. Mätvärden som kampanjhantering, säljcykel, bortfall och kundkonvertering gör att ni kan mäta e-handelstransaktioner, säljkällor, reklameffektivitet, kundlojalitet med mera.

**Trafikrapporter**

Trafikrapporter ger er djupgående insikter i hur besökarna interagerar med er webbplats.

* Analysera viktiga aspekter av besökarnas beteende.
* Övervaka och förstå trafikmönster.
* Bestäm populärt webbplatsinnehåll.
* Segmentera besökarna enligt mätbara kriterier.

## Kampanjer {#concept_A407CDF1D4AA49BAB396A1666E67FC87}

Visar information om hur effektiva era annonsinsatser är. Ni ser vilka typer av annonsinsatser som ger er mest trafik och vilka av era anställda som ansvarar för att driva dessa satsningar.

<!-- 

c_reports_campaigns.xml

 -->

Rapporterna är vanligtvis anpassade och skiljer sig därmed åt för alla analytiker. Mer information finns i [Campaign Manager](https://marketing.adobe.com/resources/help/en_US/reference/campaign_manager_admin.html) i [!DNL Admin Console] hjälpen.

## Statistiska beräkningar {#concept_83FF70DB7895435E985699FE9012D585}

Du kan anpassa standardstatistiken så att den visas i en rankad rapport.

<!-- 

c_Statistical_Calculation_ad_hoc.xml

 -->

Ytterligare statistiska standardberäkningar kan läggas till i rankade rapporter som baseras på hur de visas när du kör rapporten, inklusive medelvärde, median, standardavvikelse och andra matematiska beräkningar som utvärderas utifrån dina specifika rapporteringsbehov.

**Så här öppnar du de statistiska beräkningarna för rankade rapporter:**

1. Välj **[!UICONTROL Tools]** > **[!UICONTROL Ranked]** på menyn.

1. Välj **[!UICONTROL Settings]**.
1. Välj **[!UICONTROL Default Statistics]**.

**[!UICONTROL Ignore zeros in statistical calculations]**. Välj det här alternativet om du vill ignorera nollor och se till att de beräknade medelvärdena inte ändras när du lägger till ett annat mätvärde. All statistik påverkas av den här inställningen (även om Sum inte har någon effekt).

| Beräkning | Beskrivning |
|--- |--- |
| Max | Identifierar det maximala värdet för alla rader för en angiven datamängd. |
| Min | Identifierar det minsta värdet för alla rader för en angiven datamängd. |
| Summa | En beräkning av alla värden för varje rad i datauppsättningen.  Summan sammanställer till exempel alla besök av en besökare i stället för att bara räkna besökaren en gång (oavsett antalet besök). Det rör sig om en omfattande summa insamlade datapunkter. |
| Medel | Medelvärdet är det aritmetiska medelvärdet av raderna i en datauppsättning, beräknat som summan dividerat med antalet (summa/antal). Medelvärdet påverkas av avvikande data, till skillnad från medianvärdet som i allmänhet används för skev fördelning. |
| Standardavvikelse | Standardavvikelsen visar hur mycket variation som finns från det förväntade medelvärdet. En lägre standardavvikelse visar datapunkterna nära medelvärdet. En högre standardavvikelse visar att datapunkterna är spridda över ett stort värdeintervall. |
| Median | Medianvärdet är det numeriska värdet som skiljer den högre halvan av en data från den nedre halvan för raderna i en datauppsättning. Till skillnad från medelvärdet används det vanligtvis för att undvika underliggande värden. |
| Quartiles | En kvartil är den uppsättning värden i datauppsättningen som identifieras av tre punkter som delar upp datauppsättningen i fyra lika stora grupper, där var och en omfattar en fjärdedel av datauppsättningen. Den första kvartilen är den 25:e percentilen och den tredje kvartilen är den 75:e percentilen. (Den andra kvartilen är Median och den fjärde kvartilen är Sum.) |
| Antal | Returnerar antalet rader i en datauppsättning. |

## Exempel på beräkningar av medelvärde kontra måttsumma {#section_7C49196503964FB0A429FA347BC92D09}

Funktionen Medel beräknas ungefär som datakolumner i Microsoft Excel. Detta innebär framför allt att **medelvärdet** av en kvot (t.ex. att fastställa den genomsnittliga avhoppsfrekvensen) skulle vara medelvärdet av kvoterna, inte medelvärdet. Proportionerna för medelvärdena inkluderar **totalvärdet** för avhoppstakten.

<table id="table_9EC56B15C6A340DA8917CB0DBCAC2355"> 
 <thead> 
  <tr> 
   <th colname="col1" align="center" class="entry"> Datum </th> 
   <th colname="col2" align="center" class="entry"> Enstaka besök </th> 
   <th colname="col3" align="center" class="entry"> Poster </th> 
   <th colname="col4" align="center" class="entry"> Studsfrekvens </th> 
   <th colname="col5" align="center" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Juni 2013 </p> <p>Juli 2013 </p> <p>Augusti 2013 </p> </td> 
   <td colname="col2" align="center"> <p>344 </p> <p>297 </p> <p>41 </p> </td> 
   <td colname="col3" align="center"> <p>1000 </p> <p>1000 </p> <p>1000 </p> </td> 
   <td colname="col4" align="center"> <p>34.4% </p> <p>29.7% </p> <p>41.0% </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1" align="center" valign="middle"><b>Medel</b> </td> 
   <td colname="col2" valign="middle"> (344+297+41)/3 </td> 
   <td colname="col3" valign="middle"> (1000+1000+100)/3 </td> 
   <td colname="col4" valign="middle" align="right"> (34.4 + 29.7 + 41.0) / 3 = <b>35.0</b>% </td> 
   <td colname="col5" valign="middle"><b>Medelvärde för proportioner</b> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1" align="center" valign="middle"><b>Summa för mått</b> </td> 
   <td colname="col2" valign="middle"> 682 </td> 
   <td colname="col3" valign="middle"> 2100 </td> 
   <td colname="col4" valign="middle" align="right"> 682 / 2100 = <b>32.0</b>% </td> 
   <td colname="col5" valign="middle"><b>Förhållandet mellan medel</b> </td> 
  </tr> 
 </tbody> 
</table>

## Övertäckningar för statistikberäkning {#concept_97E1B32DAC734C7B9F8899717283CEEC}

Ad hoc-analys ger nu överläggsvisualiseringar av statistiska beräkningar för rapporter som visar data över tid (minuter, timmar, dagar, veckor).

<!-- 

c_overlay_calculations.xml

 -->

I en rapport som identifierar data över en tidsperiod kan du med **[!UICONTROL Statistics]** knappen välja beräkningar som ska visas som övertäckningar över rapportens tidslinje.

![](assets/overlay_calculations.png)

Förutom vanliga [statistiska beräkningar](/help/analyze/ad-hoc-analysis/c-overview-standard-reports.md#concept_83FF70DB7895435E985699FE9012D585)kan du välja den första, andra och tredje standardavvikelsen i övertäckningarna.

## Grupphanteraren {#concept_E1433974A61144858E87334C006982B2}

I stället för att använda en enda sida i en rapport kan du gruppera flera sidor och använda dem som kategorier för att starta, mellanlagra eller ange destinationsplats i [!UICONTROL Fallout] - och [!UICONTROL Site Analysis] -rapporterna. Du kan redigera grupper på huvudmenyn eller inifrån rapporten. Kategorier som du har skapat i marknadsföringsrapporter och analyser visas också i [!UICONTROL Checkpoint Selector] listan.

<!-- 

c_groups.xml

 -->

Klicka på **[!UICONTROL Tools]** > **[!UICONTROL Group Manager]**.
