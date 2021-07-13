---
title: Använd metoden tl() med Activity Map
description: Du kan använda metoden tl() för att spåra anpassade element och för att konfigurera övertäckningsåtergivning för dynamiskt innehåll.
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# Använd metoden `tl()` med Activity Map

Du kan använda metoden `tl()` för att spåra anpassade element och för att konfigurera övertäckningsåtergivning för dynamiskt innehåll.

## Spåra anpassade element

Med metoden [`tl()`](/help/implement/vars/functions/tl-method.md) som en del av modulen Activity Map AppMeasurement kan du spåra alla objekt som du klickar på, även objekt som inte är ankartaggar eller bildelement. Med `tl()` kan du spåra alla anpassade element som inte resulterar i sidinläsning.

I metoden `tl()` används parametern `linkName` för att identifiera avslutslänkarna, anpassade länkar osv. används nu även för att identifiera Link ID för variabeln Activity Map.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

Med andra ord, om du använder `tl()` för att spåra dina anpassade element hämtas länk-ID:t från värdet som skickas som den tredje parametern (länknamn) i metoden `tl()`. Den hämtas inte från den standardalgoritm för länkspårning som används för [standardspårning](activitymap-link-tracking-methodology.md) i Activity Map.

## Överläggsåtergivning för dynamiskt innehåll

När metoden `tl()` anropas direkt från HTML-elementets on-click-händelse kan Activity Map visa en övertäckning för det elementet när webbsidan läses in. Exempel:

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

När webbsidesinnehåll läggs till på sidan efter att den första sidan har lästs in, anropas metoden `tl()` indirekt och vi kan inte visa övertäckningar för det nya innehållet om det inte uttryckligen aktiveras/klickas. Därefter utlöses en ny länksamlingsprocess från Activity Map.

När metoden `tl()` inte anropas direkt från HTML-elementets on-click-händelse, kan Activity Map bara visa övertäckning när användaren har klickat på det elementet. Här är ett exempel där metoden `tl()` anropas indirekt:

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Det bästa sättet för Activity Map att täcka över länkar för dynamiskt innehåll är att ha en anpassad `ActivityMap.link`-funktion inställd så att den anropar samma funktion vars returvärde skickas till `tl()`. Exempel:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName)
{
    // if this is a s.tl call, just return string passed
    return linkName ||      
    // this is ActivityMap reporting time
    makeLinkName(element) ||
    // our custom function didn't return anything, so just return the default ActivityMap Link
    originalLinkFunction(element,linkName);
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Här har vi åsidosatt funktionen `ActivityMap.link` för att göra en av tre saker när den anropas:

1. Om `linkName` skickas anropades detta av `tl()`, så returnera bara det `tl()` som skickades som `linkName`.
2. När det anropas av Activity Map vid rapporteringstidpunkten skickas aldrig en `linkName`, och anropa därför `makeLinkName()` med länkelementet. Detta är det avgörande steget här - anropet `makeLinkName(element)` ska vara samma som anropets tredje argument i taggen `<button>`. `tl()` Det innebär att när `tl()` anropas spåras strängen som returneras av `makeLinkName()`. När Activity Map rapporterar på länkarna på sidan används samma anrop för att skapa en länk.
3. Den sista lösningen är bara att returnera det ursprungliga returvärdet för länkfunktionen ActivityMap. Om du behåller den här referensen så att den anropas i standardfallet behöver du bara åsidosätta eller skriva anpassad kod för `makeLinkName()` och inte behöva ange ett länkreturvärde för alla länkar på sidan.
