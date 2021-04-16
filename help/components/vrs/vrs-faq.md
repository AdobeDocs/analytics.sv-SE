---
description: Tips och bästa praxis för nya användare av virtuella rapportsviter.
keywords: Virtual Report Suite
title: Vanliga frågor om VRS
feature: Rapporter och analysgrunder
uuid: 91225743-765a-4145-9ce5-4268e80ea7e8
exl-id: ab961bec-5719-4b90-bc10-c929b63dc923
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 0%

---

# Vanliga frågor om VRS

Tips och bästa praxis för nya användare av virtuella rapportsviter.

<table id="table_4D9DE70984674B65AD7D40E3D1479CD2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Ska jag konsolidera min implementering från flera rapportsviter till en enda global rapportserie och sedan använda virtuella rapportsviter för att visa olika datasegment för mina användare?</b> </td> 
   <td colname="col2"> <p>Kanske. Här följer några omständigheter då du bör <b>överväga att fortsätta med enskilda rapportsviter</b>: </p> 
    <ul> 
     <li>Om du har variabler/dimensioner med ett stort antal unika värden, kan en konsolidering till en enda rapportserie göra att du överskrider månadens unika värdegränser i den här globala sviten, vilket kan leda till trunkering ("Låg trafik" som radartikel i rapporter). </li> 
     <li>Om du behöver realtidsrapportering eller"Aktuella data"-rapportering för enskilda segment (t.ex. varumärken, affärsenheter osv.) av era data. </li> 
     <li>Om de olika rapportsviterna var och en har unika krav på spårning (dvs. om de använder Adobe Analytics-variabler och händelser på mycket olika sätt), bör du tänka på att när du konsoliderar till en global rapportserie kommer du inte att få tillgång till ytterligare variabler eller händelser för spårning. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Vilka inställningar i virtuella rapportsviter ärvs från den överordnade rapportsviten?  </b> </td> 
   <td colname="col2"> <p>En VRS (Virtual Report Suite) ärver de flesta tjänstenivåerna i den överordnade rapportsviten, till exempel eVar, bearbetningsregler, klassificeringar osv. </p> <p>Följande inställningar är <b>NOT</b> ärvda: </p> 
    <ul> 
     <li>Rapportsvit-ID </li> 
     <li>Rapportsvitens namn </li> 
     <li>Behörighetsgrupper (virtuella rapportsviter kan tilldelas egna behörighetsgrupper) </li> 
    </ul> <p>Obs!  Detta inkluderar inte de flesta användarskapade entiteter som bokmärken, instrumentpaneler, schemalagda rapporter osv.; dessa objekt ärvs inte från det överordnade objektet och kan skapas och användas mot det virtuella systemet (mer information i nästa fråga). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hur skiljer sig ett virtuellt rapportpaket från ett basrapportpaket i analysgränssnittet?</b> </td> 
   <td colname="col2"> <p>När en virtuell rapportsvit har skapats behandlas den på samma sätt som en basrapportssvit i hela användargränssnittet och stöds i allmänhet för de flesta utökade funktioner. Exempel: </p> 
    <ul> 
     <li>Virtuella rapportsviter visas i Report Suite-väljaren och kan väljas individuellt precis som andra basrapportsviter. </li> 
     <li>DL-rapporter, bokmärken, instrumentpaneler, mål, aviseringar, segment, beräknade värden osv. kan alla skapas mot en virtuell rapportsserie och bete sig oberoende av den överordnade. </li> 
     <li>Virtuella rapportsviter kan läggas till individuellt i behörighetsgrupper på samma sätt som andra rapportsviter. </li> 
     <li>Segment kan fortfarande tillämpas när rapporter körs inom ramen för ett system för tidig varning och reaktion (VRS). de staplas automatiskt med den virtuella rapportsvitens segment när rapportdata hämtas. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hur behandlas virtuella rapportsviter i API:t för Admin Console och administratörer? Kan jag spara funktioner mot dem som basrapportsviter? </b> </td> 
   <td colname="col2"> <p>Nej, virtuella rapportsviter stöds <b>inte för de flesta administratörsfunktioner</b>. Som nämnts ovan ärver ett VRS de flesta tjänstenivåer och funktioner från det överordnade objektet (t.ex. eVar, bearbetningsregler, klassificeringar osv.), så om du vill ändra de ärvda inställningarna för ett VRS måste du ändra det överordnade rapportpaketet. </p> <p>Därför visas virtuella rapportsviter i användargränssnittet <b>endast här</b>: </p> 
    <ul> 
     <li>Virtual Report Suite Manager, där du skapar och redigerar VRS. <p>( <span class="ignoretag"> <span class="uicontrol"> Analytics </span> &gt; <span class="uicontrol"> Components </span> &gt; <span class="uicontrol"> Virtual Report Suites </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> Användarhanteringsgränssnittet, där du redigerar anpassade behörighetsgrupper. Detta gör att VRS-konton kan läggas till i en behörighetsgrupp och kan användas för att skapa en grupp som bara har åtkomst till virtuella rapportsviter (om administratören vill neka åtkomst till den överordnade gruppen och bara tillåta användare åtkomst till specifika segment). <p>( <span class="ignoretag"> <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Användarhantering </span> </span>) </p> </li> 
    </ul> <p>Obs!  När du använder API:t för webbtjänster och försöker spara funktionsinställningar mot ett VRS genereras ett undantag. Funktioner kan bara ställas in mot en basrapportsserie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Jag kollade"starta nytt besök vid lanseringen". Varför ser jag besök som fortfarande är mycket högre än starter?</b> </td> 
   <td colname="col2"> <p> När"starta nytt besök vid start" är markerat gäller timeout-värdet fortfarande. Om en användare använder appen i tio minuter med en paus på en minut mellan varje åtgärd, startar ett nytt besök vid lanseringen, så skapas ytterligare nio besök när besöket tar slut. Om du vill att starter och besök ska hållas så nära som möjligt när du använder alternativet"Starta nytt besök vid start" bör du använda en tidsgräns som är längre än den tidsgräns för sessioner som angetts i SDK. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Jag ställer in"starta nytt besök vid start" och ställer in en längre tidsgräns än min SDK. Varför är mina starter fortfarande mycket lägre än besök?</b> </td> 
   <td colname="col2"> <p> Om tidsgränsen är högre än det värde som angetts i SDK är det mycket troligt att din app skickar in träffar i bakgrunden och dessa träffar registreras som nya besök. Kontrollera detta genom att använda träfftypsdimensionen i den överordnade rapportsviten för att se om det finns några bakgrundstötningar. </p> <p> <p>Obs! Hår för bakgrund och förgrund skiljer sig endast åt i version 4.13.6 och senare av SDK. Om du använder en lägre version visas alla träffar som förgrund. Om du har rätt version av SDK bör du aktivera inställningen "Förhindra bakgrundstötningar från att starta ett nytt besök". </p> </p> <p> <p>Obs! Om du har inaktiverat tidigare bearbetning för bakgrundstötlar i Admin Console visas de inte i den överordnade rapportsviten utan visas i den virtuella rapportsviten. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Vilken version av SDK behöver jag för att spåra bakgrundstötar?</b> </td> 
   <td colname="col2"> <p> Du måste ha version 4.13.6 eller senare av SDK. </p> </td> 
  </tr> 
 </tbody> 
</table>
