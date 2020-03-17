---
description: En trendrapport som visar hur många gånger webbplatsens sidor har visats för den valda tidsperioden (timme, dag, vecka, månad, kvartal eller år). Med den här rapporten kan du spåra sidvyer för varje sida på webbplatsen samt en sammanställning av sidvyer för hela webbplatsen.
title: Sidvyer
topic: Reports
uuid: c78260c6-9ad4-4b85-84fd-763627392e44
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sidvyer

En trendrapport som visar hur många gånger webbplatsens sidor har visats för den valda tidsperioden (timme, dag, vecka, månad, kvartal eller år). Med den här rapporten kan du spåra sidvyer för varje sida på webbplatsen samt en sammanställning av sidvyer för hela webbplatsen.

En [sidvy](/help/components/c-variables/c-metrics/metrics-page-view.md) är en begäran om ett helsidesdokument i stället för ett element på en sida, till exempel en bild eller video. Om en enskild besökare till exempel visar 15 sidor under ett besök räknas 15 sidvisningar. Om en besökare tittar på samma sida tre gånger under ett besök räknas tre sidvisningar.

**Rapportegenskaper**

* Den här rapporten refererar det antal gånger som funktionen [s.t()](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_the_s.t(.html)function) har anropats på din plats.
* Anrop till anpassad [länkspårning](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linktracking.html) [!DNL s.tl()] (t.ex. anpassade länkar, nedladdningar och avslutslänkar) använder funktionen och räknas inte i den här rapporten.

* Eftersom bildbegäranden skickas när användaren uppdaterar sidan eller klickar på bakåtknappen, innehåller den här rapporten även dessa åtgärder.
* Timuppdelningar baseras på rapportsvitens tidszon.
* Den här rapporten innehåller inga radartiklar. Därför kan rapporten bara visas i trendformat.
* Kornighet mellan timme, dag, vecka, månad, kvartal och år kan tillämpas. Denna granularitet är tillgänglig beroende på rapportens datumintervall.

**Produktspecifik information**

<table id="table_61F964F47D1D43508B271999F495F7F9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Rapporter och analyser </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Webbplatsinnehåll</span> &gt; <span class="uicontrol"> Sidvyer</span> </p> <p>Den här rapporten kan använda segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad hoc-analys </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DB66B8F9F6BF473A83EC7668F59776D0"> 
     <li id="li_D1CB486058F040859560D5BFDF3972EE"> Delar upp varje objekt i den här rapporten med alla andra rapporter och variabler, så att du kan se uppdelningar efter granularitet. </li> 
     <li id="li_BAADA9ADDD6F47B08D129FD30CD8EF2E">Ni kan använda alla konverterings- och trafikvärden i den här rapporten, samt olika allokeringar för alla konverteringsvärden. </li> 
     <li id="li_3696CA6E0BD54305B3609CCC80F851BA">Den här rapporten kan använda flera mycket avancerade segment. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

