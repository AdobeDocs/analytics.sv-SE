---
description: Det här avsnittet är avsett för Adobe Analytics-administratörer. Det fokuserar på de nya parametrarna för länkspårning och hur de säkerställer att länkar är unika och enhetliga i olika webbläsare och enheter, samt förbättrar hanteringen av länkpositionering på en sida.
title: Metod för länkspårning
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: a6b38c6e7a34c876524ebe15514ac205898549d0
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 0%

---

# Metod för länkspårning

Det här avsnittet är avsett för Adobe Analytics-administratörer. Det fokuserar på de nya parametrarna för länkspårning och hur de säkerställer att länkar är unika och enhetliga i olika webbläsare och enheter, samt förbättrar hanteringen av länkpositionering på en sida.

>[!IMPORTANT]
>
>Alla länkar där texten (inte href) kan innehålla PII (personligt identifierbar information) ska implementeras explicit med [s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html) eller genom att utesluta ActivityMap-länksamlingen med [s.ActivityMap.linkExclusions eller s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars). Mer information om hur Activity Map kan samla in PII-data finns på [här](/help/analyze/activity-map/lnk-tracking-overview.md).

Activity Map baserar länkspårningen på följande två ID:

* Primärt ID: det här är länkens identifierbara parameter.
* Länkområde: Detta är en sekundär parameter som gör att användare kan ange en sträng som är representativ för det övergripande länkområdet på sidan eller i regionen. Den här parametern kan genereras automatiskt om den inte tillhandahålls av användaren.

## Primärt ID {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Om HTML har s_objectid används som standard det primära ID:t för s_objectid. I annat fall används följande parametrar som primärt ID (i den här prioritetsordningen):

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

## Länka område {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Med det här nya attributet kan användare ange en sträng som är representativ för det sidområde där länken finns.

Om du till exempel har en länk till&quot;Kontakta oss&quot; som finns i menyavsnittet på webbsidan kanske användaren vill skicka en parameter för&quot;Menu&quot;-region. På samma sätt kan regionsparametern anges till &quot;footer&quot; för en &quot;Contact Us&quot;-länk som finns i webbsidans sidfot.

Värdet för Länkområde anges inte för själva länken, utan för ett HTML-element i DOM-HTML-trädet som omfattar den regionen.
Att använda Länkregion har följande fördelar:

* Det hjälper till att skilja på länkar med samma primära ID.
* Trender för ett område påverkas inte lika mycket av webbsidans dynamiska proportioner.
* Användarna kan se de länkar som fungerar bäst i en region. Med Region som ankarpunkt kan vi visa övertäckningar av länkar som för närvarande inte är synliga på sidan (Ajax, Targeting).
* En region kan ersätta sidor eftersom ett visst område kan användas på många webbsidor. Det hjälper till att svara på frågor som: &quot;Fungerar regionen &quot;Product Offering&quot; bäst på Women&#39;s Landing Page eller Men&#39;s Landing Page?
* Regionen är i sig en viktig dimension för att analysera mycket dynamiska webbsidor. Det beror på att bruset tas bort på grund av ständigt ändrade länkar: en region för senaste nytt på CNN-landningssidan kan ha många föränderliga länkar. Men regionen finns alltid där. Det kan därför vara intressant att följa utvecklingen på regionnivå under många dagar.

**Anpassad regionspårning**

Du kan anpassa parametern Region för en länk (standard är länk-ID): En tagg med värdet&quot;ID&quot; använder alla HTML-element med en&quot;id&quot;-parameter som region. Om du ställer in regiontaggen på&quot;id&quot; returneras troligen många olika regioner (så många som det finns olika&quot;ID&quot; på sidan). Om du vill ha en mer anpassad implementering kan du ställa in regiontaggen på något mer specifikt, till exempel&quot;region_id&quot;.

Nedan kan du visa några exempel på HTML med hjälp av standardattributet för region-ID, &quot;id&quot;.

```
<div id="content">
  <div id="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

Om du vill kan du tagga element med en godtycklig strängidentifierare, i det här fallet &quot;lpos&quot;, och sedan lägga till attribut med namnet &quot;lpos&quot;.

```
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute = "lpos";
</script>
<div id="nav" lpos="navbar">
  <ul>
    <li>Menu Category A
      <ul>
        <li><a href="">Menu Item A 1</a>
        <li><a href="">Menu Item A 2</a>
      </ul>
    </li>
    <li>Menu Category B
      <ul>
        <li><a href="">Menu Item B 1</a>
        <li><a href="">Menu Item B 2</a>
      </ul>
    </li>
  </ul>
</div> 
  
<div id="content">
  <div id="breaking_news" lpos="breaking_news>
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

## Konfigurationsvariabler {#configuration-vars}

Observera att dessa variabler listas endast i referenssyfte. Activity Map bör vara korrekt konfigurerat, men du kan anpassa implementeringen med dessa variabler.

### `s.ActivityMap.regionIDAttribute`

Sträng som identifierar taggattributet som ska användas som region-ID från något överordnat element (parent, parent.parent, ...) i `s.linkObject`, dvs. **elementet som du klickade på**.

**Exempel**

Standardvärdet är &quot;id&quot;-parametern. Du kan ange den här till en annan parameter.

### `s.ActivityMap.link`

Funktion som tar emot klickade `HTMLElement` och ska returnera ett strängvärde som representerar länken som klickades på. Om returvärdet är false (null, undefined, empty string, 0) spåras ingen länk.

**Exempel**

```
// only ever use "title" attributes from A tags
function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

### `s.ActivityMap.region`

Funktion som tar emot det klickade HTMLElement och ska returnera ett strängvärde som representerar **det område där länken hittades när användaren klickar på den.** Om returvärdet är false (null, undefined, empty string, 0) spåras ingen länk.

**Exempel**

```
// only ever use lowercase version of tag name concatenated with first className as the region
function(clickedElement) {
  var regionId, className;
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

### `s.ActivityMap.linkExclusions`

Sträng som tar emot en kommaavgränsad lista med strängar att söka efter i länktext. Om den hittas utesluts länken från att spåras av Activity Map. Om den inte anges görs inget försök att stoppa spårningen av länken av Activity Map.

**Exempel**

```
// Exclude links tagged with a special linkExcluded CSS class
<style>
.linkExcluded {
  display: block;
  height: 1px;
  left: -9999px;
  overflow: hidden;
  position: absolute;
  width: 1px;
}
</style>
<a href="next-page.html">
  Link is tracked because link does not have hidden text matching the filter. 
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link1</span>
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link2</span>
</a>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2';
</script>
```

### `s.ActivityMap.regionExclusions`

Sträng som tar emot en kommaavgränsad lista med strängar som ska sökas efter i regionstext. Om den hittas utesluts länken från att spåras av Activity Map. Om den inte anges görs inget försök att stoppa spårningen av länken av Activity Map.

**Exempel**

```
// Exclude regions on the page from its links being trackable by ActivityMap
<div id="links-included">
  <a href="next-page.html">
    Link is tracked because s.ActivityMap.regionExclusions is set but does not match the filter.
  </a>
</div>
<div id="links-excluded"> 
  <a href="next-page.html">
    Link not tracked because s.ActivityMap.regionExclusions is set and this link matches the filter.
  </a>
</div>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.regionExclusions = 'links-excluded';
</script>
```
