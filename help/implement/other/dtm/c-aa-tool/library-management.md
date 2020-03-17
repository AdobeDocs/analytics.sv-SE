---
description: Beskrivningar av fälten och alternativen i inställningarna för bibliotekshantering i Dynamic Tag Management.
keywords: library management;page code;load library at;managed by adobe;custom;code hosted;s_code hosted
solution: Experience Cloud,Dynamic Tag Management
title: Bibliotekshantering
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Bibliotekshantering

Beskrivningar av fälten och alternativen i inställningarna för bibliotekshantering i Dynamic Tag Management.

**[!UICONTROL  *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Library Management]**

> [!NOTE] Om mer än ett Adobe Analytics-verktyg används i en enda webbegenskap måste varje verktyg ha ett unikt spårningsvariabelnamn. Dubbla objektvariabelnamn mellan Adobe Analytics-verktyg i en enda webbegenskap orsakar konflikter.

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sidkoden finns redan </p> </td> 
   <td colname="col2"> <p> Hindrar Dynamic Tag Management från att installera <span class="keyword"> Adobe Analytics</span> -sidkoden om koden redan finns på din plats. </p> <p>Med den här funktionen kan du använda dynamisk tagghantering för att lägga till i den befintliga implementeringen i stället för att börja från början. Var noga med att ange spårningsvariabelns namn när du markerar den här rutan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Läs in bibliotek på &lt;<span class="term"> Page Top</span> or <span class="term"> Page Bottom</span>&gt; </p> </td> 
   <td colname="col2"> <p>Anger var och när sidkoden ska läsas in. Oavsett vad du väljer måste alla regler som använder analysverktyget ha samma inställning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hanteras av Adobe (rekommenderas) </p> </td> 
   <td colname="col2"> <p>Aktivera dynamisk tagghantering för att hantera ditt bibliotek. </p> <p>Om du väljer det här alternativet blir följande alternativ tillgängligt: </p> <p> <b>Biblioteksversion: </b>Välj den senaste versionen på menyn <span class="wintitle"> Biblioteksversion</span> . Dynamisk tagghantering meddelar dig när nya versioner finns tillgängliga. Du kan vid behov återgå till en tidigare version. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Egen </p> </td> 
   <td colname="col2"> <p>Du kan konfigurera bibliotekskoden. </p> <p>Om du väljer det här alternativet blir följande alternativ tillgängliga: </p> <p> <b>Ange rapportsviter med hjälp av anpassad kod nedan: </b>När den här rutan är markerad söker Dynamic Tag Management efter en variabel i din anpassade kod som heter <span class="varname"> s_account</span>. Variabeln ska innehålla en kommaavgränsad lista över de rapportsviter som du vill skicka data till. </p> <p> <b>Kod som är värd: </b>Välj ett alternativ för att vara värd för <span class="filepath"> s_code</span>: </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>I DTM</b>: Du kan vara värd för <span class="filepath"> s_code</span> i Dynamic Tag Management. Klicka på <span class="uicontrol"> Redigera kod</span> för att klippa ut och klistra in filen direkt i redigeraren. </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL</b>: Om du har en bra <span class="filepath"> s_code</span> -fil och är nöjd med processen att uppdatera den, kan du ange URL:en till filen här. Dynamisk tagghantering förbrukar sedan <span class="filepath"> s_code</span> -filen för implementeringen av <span class="keyword"> Adobe Analytics</span>. </li> 
    </ul> <p> <b>Öppna redigerare:</b> Används för att <a href="/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md"  >infoga AppMeasurement-kärnkod</a>. Den här koden fylls i automatiskt när den automatiska konfigurationsmetoden som beskrivs i <a href="/help/implement/other/dtm/c-aa-tool/analytics-dtm.md"  >Adobe Analytics-inställningarna</a> används. </p> <p> <b>Spårarvariabelnamn: </b>Om du vill köra två instanser av <span class="keyword"> Adobe Analytics</span> parallellt (en inom Dynamic Tag Management och en internt) kan du byta namn på <span class="term"> huvudobjektet</span> . Om du byter objektnamn undviker du kollisioner. </p> </td> 
  </tr> 
 </tbody> 
</table>

