---
description: Svar på frågor du kan ha när du implementerar Audience Analytics.
solution: Experience Cloud
title: Frågor och svar för Audience Analytics
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 0%

---

# Vanliga frågor

Svar på frågor du kan ha när du implementerar Audience Analytics.

## Frågor och svar {#section_B51CFC961C0B45A2BE5F4A4404620764}

<table id="table_22037CCB516C4231BF5820004FBB351A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>F: Hur vet jag om jag har PII (Personally Identiitable Information) i mina analysdata? Och om ja, vad gör jag åt det?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_71E0ECD5981D4B65BCDA065BE07A43AA"> 
     <li id="li_F8FF61A4D7B54BA39DAA6F28DB51D749">Om du har e-post/adresser/så vidare i ett utkast eller en eVar bör du överväga att hash-koda data under insamlingen. </li> 
     <li id="li_57A8B4C7BB784FFCBC1DC363B35D9FF7">Om ditt land anser att IP-adressen är PII, <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html"  > aktivera IP-förvrängning </a>. </li> 
     <li id="li_C7AA02B831AE47A59E783623126A7789">Tala med er Analytics Admin för att se vad ni samlar in. </li> 
     <li id="li_F6AAE868141E486AB8CAB291BD8EDB71">Tala med er juridiska avdelning för att se vad de anser vara PII. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>F: Hur vet jag om mina rapportsviter gör personalisering på plats eller målgruppsanpassning på plats eller utanför webbplatsen?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F0984CEF80DB4B589716BC55549E32B8"> 
     <li id="li_9BC3819784A9408F846D60FF0F20AAF9">Dessa gäller inte när du skickar Adobe Analytics-data till Adobe Audience Manager. </li> 
     <li id="li_050A1BF9978E436895B5C7E33A82527D">Fråga dig själv: Kommer ni att dela ett Analytics-delat segment med en MCA-dimension tillbaka till Experience Cloud? </li> 
     <li id="li_C52D969681B94F4AAA18FDEB21EC5B49">Exporterar du (t.ex. via dataflöden) ut till ett Business Intelligence-system (BI) som används för dessa ändamål? </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## AAM frågor och svar {#section_6BDF746BA6464359A6A89A64EB025D12}

<table id="table_15B44592161240BDA79F3B020EA9CC9D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>F: Hur skapar jag ett Analytics-mål i Audience Manager?</b> </p> </td> 
   <td colname="col2"> Se <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html"  > Konfigurera ett analysmål i AAM </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: När du har skapat och sparat ett Analytics-mål, hur lång tid tar det tills data visas i de valda rapportsviterna?</b> </p> </td> 
   <td colname="col2"> <p>Det kan ta flera timmar att fylla i rapportsviterna med nya data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Jag har skapat ett nytt Analytics-mål, men det visas inte i avsnittet Destination Mappings i mina tillgängliga segment. Vart tog den vägen eller hur hittar jag den?</b> </p> </td> 
   <td colname="col2"> <p>Ett Analytics-mål tas bort från ett segments målmappningsavsnitt när du väljer <span class="uicontrol"> Mappa automatiskt alla aktuella och framtida segment </span> alternativ i <span class="uicontrol"> Segmentmappningar </span>. </p> <p><img placement="break" align="left"  src="assets/auto-mapping.png" id="image_670ED5A306784FCBA8A0B336AC1F0FC6" width="300px" /> </p> <p>Om du vill förhindra detta väljer du <span class="uicontrol"> Mappa segment manuellt </span> i stället för det automatiska alternativet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>F: Får jag all information från AAM i Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Nej, endast data som är relaterade till personer som kommer till er webbplats under eller efter det att Audience Manager-målgrupper aktiverats och under/efter det att segmentet kvalificerats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>F: Får jag en adresserbar målgrupp per segment?</b> </p> </td> 
   <td colname="col2"> <p>Egentligen inte. Här visas antalet besökare i det segmentet som kom till webbplatsen under eller efter en segmentkvalificering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>F: På vilket sätt skiljer sig detta från det gamla cookie-målet till Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Segmenten kvalificeras för och returneras i realtid - med samma träff. </p> <p>Eget namn visas automatiskt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Vad händer om vissa av mina rapporteringsprogram har personuppgifter och andra inte har det?</b> </p> </td> 
   <td colname="col2"> <p>Tips: Skapa två mål - lägg till rapporteringssviterna för personuppgifter till ett mål och rapporteringssviterna för icke-personliga data till ett annat. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Analysspecifika frågor {#section_67BFB1B1E48D4113A38B075C020931BA}

<table id="table_19AEAE0A3575423CB4F5F164DB5626D5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>F: Kommer den här integreringen att bli en dimension eller ett segment i Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Som dimensioner: Publikens ID och publikens namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Var kan jag använda de här dimensionerna i Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Nästan överallt. de behandlas på samma sätt som andra dimensioner som samlas in i Analytics. Det finns ett undantag: data kommer inte att vara i Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Varför ser jag inte data som kommer in i Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Du har troligtvis konflikter AAM sekretesskontrollerna mellan datakällor och mål. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Varför saknas några av mina segment i Analytics, trots att jag valde att skicka alla segment?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_B8938FD08C6F4F2387EDADDEF8089319"> 
     <li id="li_50A9BDF612304062913370F16BC882EF">Dina AAM för dataexport på målet och i segmentets datakällor kan vara i konflikt, vilket förhindrar att vissa segment skickas. </li> 
     <li id="li_AF5D6F883D6F4D3192E0BF23CF12ADEA">Om du använder dataegenskaper från tredje part i dina segment kan dessa segment inte delas med mål (en uppsättning rapportsviter) som innehåller personuppgifter. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Varför ser jag"Målgruppsgräns nådd" i min Analytics-rapport? (Obs! this kommer också att representeras som Audience ID = -1 och "::max_audiences_exceeded::" i Data warehouse)</b> </p> </td> 
   <td colname="col2"> <p>Som standard skickas alla segment som en besökare kvalificerar för till Analytics via integreringen Audience Analytics för AAM. Om en besökare tillhör mer än 150 AAM segment i en enda träff visas <b>150 senast kvalificerade segment</b> skickas till Analytics, medan den återstående listan trunkeras. </p> <p>En extra flagga skickas till Analytics som anger att segmentlistan trunkerades och visas som"Målgräns nådd" i dimensionen Målgruppsnamn och"-1" i dimensionen Målgrupps-ID. </p> <p>Det är osannolikt att en besökare kvalificerar sig för mer än 150 segment för en viss träff, men det kan hända en liten del av tiden. Om du upplever"Målgruppsgräns nådd" i din rapportering har du två alternativ: </p> 
    <ul id="ul_8E290B2E32DC49738F6FD00CB0CE2BBB"> 
     <li id="li_12F498981EA949B5BCBD40ECC954C339"><b>Alternativ 1</b>: Fortsätt att låta integreringen fungera i det färdiga läget och skicka de 150 senast kvalificerade segmenten för en viss besökare. </li> 
     <li id="li_CA4D5747AA4A4452929097807B604959"><b>Alternativ 2</b>: I AAM väljer du de 150 segment som är viktigast för ditt företag för integreringen. AAM kontrollerar sedan besökarna mot endast dessa 150 segment. Nackdelen med detta är att ni bara får dessa 150 segment över alla besökare. Å andra sidan kan alternativ 1-metoden leverera ett obegränsat antal segment på grund av integreringens per-träfftyp. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Faktureras ytterligare serversamtal till Analytics för den här integreringen?</b> </p> </td> 
   <td colname="col2"> <p>Nej. AAM Audiences ingår i Analytics på serversidan. Detta medför inte ytterligare serveranrop till Analytics (primär eller sekundär). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vanliga frågor och svar om vidarekoppling på serversidan (SSF) {#section_ADDE84ABCA0D4906B6235E92D185E0C6}

<table id="table_B7067B70FF85498896801F58D716202F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>F: Om jag har implementerat en äldre SSF-fil, måste jag då också gå till Analytics Admin och aktivera rapportsviten SSF?</b> </p> </td> 
   <td colname="col2"> <p>Ja. I AAM målinställningar visas endast rapportsviter som har SSF aktiverat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Varför kan jag inte aktivera vissa rapporteringsprogram för SWF i Analytics Admin?</b> </p> </td> 
   <td colname="col2"> <p>Endast sviter som är mappade till din Experience Cloud-organisation kan aktiveras. </p> </td> 
  </tr> 
 </tbody> 
</table>

Mer information om vanliga frågor om detta avsnitt finns i [Vanliga frågor om vidarebefordran på serversidan](/help/admin/admin/c-server-side-forwarding/ssf-faq.md).

## Allmänna frågor och svar {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

<table id="table_1F7C0C785F9C472286A96F8C25E8440B"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>F: Varför skiljer sig segmentbesökarnas antal mellan Audience Manager och Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Se <a href="/help/integrate/c-audience-analytics/visitor-count-reconciliation.md"  > Skillnader i antal besökare </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Vad är skillnaden mellan"målgrupper" i AAM och"segment" i Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Se <a href="/help/integrate/c-audience-analytics/aam-analytics-segments.md"  > Förstå segment i Analytics och Audience Manager </a>. </p> <p>AAM målgrupper skickas vidare och delas som"dimensionskomponenter" som ska användas i Analytics. De visas inte som segment i segmentbyggaren, till exempel, utan som dimensioner som du kan skapa segment med. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Vad är skillnaden mellan kundattribut och kunddata som är integrerade från AAM?</b> </p> </td> 
   <td colname="col2"> <p>Kundattribut är inte tidsbaserade; de tillämpar retroaktivt och går framåt. AAM integrerade data är tidsbaserade och kan bara vidareutvecklas. Dessutom är kundattribut ett sökregister för besökar-ID:n i Experience Cloud, medan AAM integrering är data som sammanfogas i varje träff för en besökare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Hur är det med äldre metoder för detta problem, till exempel gamla beta- eller konsultplugin-program för cookie-mål?</b> </p> </td> 
   <td colname="col2"> <p>Vi rekommenderar att du implementerar den nya integreringen och tar bort gamla destinationer. </p> </td> 
  </tr> 
 </tbody> 
</table>
