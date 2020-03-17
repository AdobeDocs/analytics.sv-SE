---
description: Du kan använda metoden s.tl() för att spåra anpassade element och för att konfigurera övertäckningsåtergivning för dynamiskt innehåll.
title: Använda metoden s.tl()
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 290526ecc1b040f93d0734a5deaf2d79ab1bde10

---


# Använda `tl` metoden

Du kan använda metoden för att spåra anpassade element och för att konfigurera överläggsåtergivning för dynamiskt innehåll. `tl`

## Spåra anpassade element {#section_5D6688DFFFC241718249A9A0C632E465}

Med hjälp av [`tl` metoden](/help/implement/vars/functions/tl-method.md) som en del av Activity Map AppMeasurement-modulen kan du spåra alla objekt som du klickar på, även objekt som inte är ankartaggar eller bildelement. Med s.tl kan du spåra alla anpassade element som inte medför att sidan läses in.

I `tl` metoden är det den `linkName` parameter som används för att identifiera avslutslänkar, anpassade länkar osv. används nu även för att identifiera länk-ID:t för aktivitetskartan.

```js
s.tl(this,linkType,linkName,variableOverrides)
```

Med andra ord, om du använder `s.tl` för att spåra dina anpassade element hämtas länk-ID:t från värdet som skickas som den tredje parametern (linkName) i `s.tl` metoden. Den hämtas inte från den standardalgoritm för länkspårning som används för [standardspårning](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) i aktivitetskartan.

## Överläggsåtergivning för dynamiskt innehåll {#section_FD24B61A732149C7B58BA957DD84A5E7}

När funktionen s.tl() anropas direkt från HTML-elementets on-click-händelse kan aktivitetskartan visa en övertäckning för det elementet när webbsidan läses in. Exempel:

```html
<div onclick="s.tl(this,'o','Example custom link')">Example link text</a>
```

När webbsidesinnehåll läggs till på sidan efter att den första sidan har lästs in, anropas metoden indirekt och vi kan inte visa övertäckningar för det nya innehållet om det inte uttryckligen aktiveras/klickas. `tl` Därefter utlöses en ny länksamlingsprocess från aktivitetskartan.

När `tl` metoden inte anropas direkt från HTML-elementets on-click-händelse kan aktivitetskartan bara visa övertäckning när användaren har klickat på elementet. Här är ett exempel där `tl` metoden anropas indirekt:

```html
<div onclick="someFn(event)"></div>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Det bästa sättet för Activity Map att täcka över länkar med dynamiskt innehåll är att ha en anpassad ActivityMap.link-funktion inställd så att den anropar samma funktion vars returvärde skickas till `s.tl`. Exempel:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName) {
    return linkName ||      // if this is a s.tl call, just return string passed
        makeLinkName(element) || // this is ActivityMap reporting time
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Här har vi åsidosatt funktionen ActivityMap.link för att göra en av tre saker när den anropas:

1. Om linkName skickas anropas detta av s.tl(), så returnera bara det som s.tl skickade som linkName.
2. Detta anropas av Activity Map vid rapporttidpunkten, så linkName skickas aldrig och anropa makeLinkName() med link-elementet. Det här är det avgörande steget här - anropet &quot;makeLinkName(element)&quot; ska vara detsamma vid s.tl-anropets tredje argument i `<button>` -taggen. Det innebär att när s.tl anropas spåras strängen som returneras av makeLinkName. När aktivitetskartan rapporterar på länkarna på sidan används samma anrop för att skapa en länk.
3. Den sista lösningen är bara att returnera det ursprungliga returvärdet för länkfunktionen ActivityMap. Om du behåller den här referensen så att den anropas i standardfallet behöver du bara åsidosätta eller skriva anpassad kod för makeLinkName och inte behöva ange ett länkreturvärde för alla länkar på sidan.
