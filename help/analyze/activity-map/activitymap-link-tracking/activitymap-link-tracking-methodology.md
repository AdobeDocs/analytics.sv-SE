---
description: Det här avsnittet är avsett för Adobe Analytics-administratörer. Det fokuserar på de nya parametrarna för länkspårning och hur de säkerställer att länkar är unika och enhetliga i olika webbläsare och enheter, samt förbättrar hanteringen av länkpositionering på en sida.
title: Metod för länkspårning
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---


# Metod för länkspårning

Det här avsnittet är avsett för Adobe Analytics-administratörer. Det fokuserar på de nya parametrarna för länkspårning och hur de säkerställer att länkar är unika och enhetliga i olika webbläsare och enheter, samt förbättrar hanteringen av länkpositionering på en sida.

>[!IMPORTANT]
>
>Alla länkar där texten (inte href) kan innehålla PII (personligt identifierbar information) ska implementeras explicit med [s_objectID](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/page-variables.html) eller genom att utesluta ActivityMap-länksamlingen med [s.ActivityMap.linkExclusions eller s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars). Mer information om hur Activity Map kan samla in PII-data finns [här](/help/analyze/activity-map/lnk-tracking-overview.md).

Activity Map baserar länkspårningen på följande två ID:

* Primärt ID: det här är länkens identifierbara parameter.
* Länkområde: Detta är en sekundär parameter som gör att användare kan ange en sträng som är representativ för det övergripande länkområdet på sidan eller i regionen. Den här parametern kan genereras automatiskt om den inte tillhandahålls av användaren.

## Primärt ID {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Om HTML-koden har s_objectid används som standard s_objectid som primärt ID. I annat fall används följande parametrar som primärt ID (i den här prioritetsordningen):

* Innertext
* AltText
* Titel
* Källa
* Åtgärd

## Använda InnerText jämfört med att använda länkåtgärd (URL) {#section_70C3573E22274522A8CC035BF18EC468}

Länkåtgärd är den åtgärd som webbsidan utför när någon klickar på länken, vanligtvis den URL som besöks efter att länken har klickats på. Några av de problem du kan stöta på när du använder länkåtgärden är:

* har två eller flera distinkta länkar med samma ID
* länkens läsbarhet
* en länk med flera åtgärder (beroende på vilken enhet du visar länken på)

Därför använder vi InnerText med följande fördelar jämfört med att använda länkåtgärd (URL):

* Det är en bra representation av länkidentiteten. Dubblering av primärt ID är betydligt mindre eftersom det inte är vanligt att ha flera länkar med samma text.
* Det säkerställer enhetlighet för det primära ID:t på olika enheter och webbläsartyper.
* Den påverkas inte av en omplacering av länkar på sidan.
* Det förbättrar läsbarheten så att användare kan börja analysera rapporter om länkspårning utanför Activity Map.

## Länkområde {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Med det här nya attributet kan användare ange en sträng som är representativ för det sidområde där länken finns.

Om du till exempel har en länk till&quot;Kontakta oss&quot; som finns i menyavsnittet på webbsidan kanske användaren vill skicka en parameter för&quot;Menu&quot;-region. På samma sätt kan regionsparametern anges till &quot;footer&quot; för en &quot;Contact Us&quot;-länk som finns i webbsidans sidfot.

Värdet för Länkområde anges inte för själva länken, utan för ett HTML-element i DOM HTML-trädet som omfattar den regionen.
Att använda Länkregion har följande fördelar:

* Det hjälper till att skilja på länkar med samma primära ID.
* Trender för ett område påverkas inte lika mycket av webbsidans dynamiska proportioner.
* Användarna kan se de länkar som fungerar bäst i en region. Med Region som ankarpunkt kan vi visa övertäckningar av länkar som för närvarande inte är synliga på sidan (Ajax, Targeting).
* En region kan ersätta sidor eftersom ett visst område kan användas på många webbsidor. Det hjälper till att svara på frågor som: &quot;Fungerar regionen &quot;Product Offering&quot; bäst på Women&#39;s Landing Page eller Men&#39;s Landing Page?
* Regionen är i sig en viktig dimension för att analysera mycket dynamiska webbsidor. Det beror på att bruset tas bort på grund av ständigt ändrade länkar: en region för senaste nytt på CNN-landningssidan kan ha många föränderliga länkar. Men regionen finns alltid där. Det kan därför vara intressant att följa utvecklingen på regionnivå under många dagar.

**Anpassad regionspårning**

Du kan anpassa parametern Region för en länk (standard är länk-ID): En tagg med värdet &quot;ID&quot; använder alla HTML-element med parametern &quot;id&quot; som region. Om du ställer in regiontaggen på&quot;id&quot; returneras troligen många olika regioner (så många som det finns olika&quot;ID&quot; på sidan). Om du vill ha en mer anpassad implementering kan du ställa in regiontaggen på något mer specifikt, till exempel&quot;region_id&quot;.

Nedan kan du visa HTML-exempelkod med standardattributet för region-ID, &quot;id&quot;.

```
<div id="content"> 
  <div id="breaking_news"> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
```

Om du vill kan du tagga element med en godtycklig strängidentifierare, i det här fallet &quot; lpos&quot;, och sedan lägga till attribut med namnet &quot;lpos&quot;.

```
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute="lpos";
</script> 
   
<div id="nav" lpos="navbar"> 
  <ul> 
     <li> Menu Category A 
    <ul> 
      <li><a href="">Menu Item A 1</a> 
      <li><a href="">Menu Item A 2</a> 
     </ul> 
    </li> 
     <li> Menu Category B 
     <ul> 
      <li><a href="">Menu Item B 1</a>  
      <li><a href="">Menu Item B 2</a> 
  
   </ul> 
</ul> 
</div> 
  
<div id="content" > 
  <div id="breaking_news" lpos="breaking_news> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
</div>
```

## Konfigurationsvariabler {#configuration-vars}

Observera att dessa variabler listas endast i referenssyfte. Activity Map bör vara korrekt konfigurerat, men du kan anpassa implementeringen med dessa variabler.

<table id="table_7BC8DC3F35CF49288D94BA707F06B283"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabelnamn </th> 
   <th colname="col2" class="entry"> Exempel </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionIDAttribute </td> 
   <td colname="col2"> Standardvärdet är "id"-parametern. Du kan ange den här till en annan parameter. </td> 
   <td colname="col3"> Sträng som identifierar det taggattribut som ska användas som region-ID från något överordnat element (parent, parent.parent, ...) i s.linkObject, dvs. <b>elementet som klickades på</b>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.link </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;only&nbsp;ever&nbsp;use&nbsp;"title"&nbsp;attributes&nbsp;from&nbsp;A&nbsp;tags function(clickedElement){ &nbsp;&nbsp;&nbsp;var&nbsp;linkId; &nbsp;&nbsp;&nbsp;if(clickedElement&nbsp;&amp;&amp;&nbsp;clickedElement.tagName.toUpperCase()&nbsp;===&nbsp;'A'){ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;linkId&nbsp;=&nbsp;clickedElement.getAttribute('title'); &nbsp;&nbsp;&nbsp;} &nbsp;&nbsp;&nbsp;return&nbsp;linkId; } 
    </code> </td> 
   <td colname="col3"> Funktion som tar emot det klickade HTMLElement och ska returnera ett strängvärde som representerar <b>länken som klickades på</b>. <p>Om returvärdet är false (null, undefined, empty string, 0) spåras ingen länk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.region </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;only&nbsp;ever&nbsp;use&nbsp;lowercase&nbsp;version&nbsp;of&nbsp;tag&nbsp;name&nbsp;concatenated&nbsp;with&nbsp;first&nbsp;className&nbsp;as&nbsp;the&nbsp;region function(clickedElement){ &nbsp;&nbsp;&nbsp;var&nbsp;regionId,className; &nbsp;&nbsp;&nbsp;while(clickedElement&nbsp;&amp;&amp;&nbsp;(clickedElement=&nbsp;clickedElement.parentNode)){ &nbsp;regionId&nbsp;=&nbsp;clickedElement.tagName; &nbsp;if(regionId){ &nbsp;return&nbsp;regionId.toLowerCase(); &nbsp;} &nbsp;} } 
    </code> </td> 
   <td colname="col3"> Funktion som tar emot det klickade HTMLElement-objektet och ska returnera ett strängvärde som representerar <b>regionen där länken påträffades när användaren klickade på</b>. <p>Om returvärdet är false (null, undefined, empty string, 0) spåras ingen länk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;Exclude&nbsp;links&nbsp;tagged&nbsp;with&nbsp;a&nbsp;special&nbsp;linkExcluded&nbsp;CSS&nbsp;class &nbsp;&lt;style&gt; .linkExcluded{ &nbsp;&nbsp;display:&nbsp;block; &nbsp;&nbsp;height:&nbsp;1px; &nbsp;&nbsp;left:&nbsp;-9999px; &nbsp;&nbsp;overflow:&nbsp;hidden; &nbsp;&nbsp;position:&nbsp;absolute; &nbsp;&nbsp;width:&nbsp;1px; } &lt;/style&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;link&nbsp;does&nbsp;not&nbsp;have&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.&nbsp;&lt;/a&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter. &nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link1&lt;/span&gt; &lt;/a&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter. &nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link2&lt;/span&gt; &lt;/a&gt; &lt;script&gt; &nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid'); &nbsp;&nbsp;s.ActivityMap.linkExclusions&nbsp;=&nbsp;'exclude-link1,exclude-link2'; &lt;/script&gt; 
    </code> </td> 
   <td colname="col3"> <p>Sträng som tar emot en kommaavgränsad lista med strängar att söka efter i länktext. Om den hittas utesluts länken från att spåras av Activity Map. Om den inte anges görs inget försök att stoppa spårningen av länken av Activity Map. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;Exclude&nbsp;regions&nbsp;on&nbsp;the&nbsp;page&nbsp;from&nbsp;its&nbsp;links&nbsp;being&nbsp;trackable&nbsp;by&nbsp;ActivityMap &lt;div&nbsp;id="links-included"&gt;&nbsp; &nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;but&nbsp;does&nbsp;not&nbsp;match&nbsp;the&nbsp;filter.&lt;/a&gt; &lt;/div&gt; &lt;div&nbsp;id="links-excluded"&gt;&nbsp; &nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;matches&nbsp;the&nbsp;filter.&lt;/a&gt; &lt;/div&gt; &lt;script&gt; &nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid'); &nbsp;&nbsp;s.ActivityMap.regionExclusions&nbsp;=&nbsp;'links-excluded'; &lt;/script&gt;
    </code> </td> 
   <td colname="col3"> <p>Sträng som tar emot en kommaavgränsad lista med strängar som ska sökas efter i regionstext. Om den hittas utesluts länken från att spåras av Activity Map. Om den inte anges görs inget försök att stoppa spårningen av länken av Activity Map. </p> </td> 
  </tr> 
 </tbody> 
</table>
