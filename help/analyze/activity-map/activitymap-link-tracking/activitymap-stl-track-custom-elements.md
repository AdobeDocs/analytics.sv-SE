---
title: Använd metoden tl() med Activity Map
description: Du kan använda metoden tl() för att spåra anpassade element och för att konfigurera övertäckningsåtergivning för dynamiskt innehåll.
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Använd `tl()` metod med Activity Map

Du kan använda `tl()` metod för att spåra anpassade element och för att konfigurera övertäckningsåtergivning för dynamiskt innehåll.

## Spåra anpassade element

Använda [`tl()` method](/help/implement/vars/functions/tl-method.md) som en del av modulen Activity Map AppMeasurement gör att du kan spåra alla objekt som du klickar på, även objekt som inte är ankartaggar eller bildelement. Använda `tl()`kan du spåra alla anpassade element som inte medför att sidan läses in.

I `tl()` -metoden, `linkName` parameter som används för att identifiera avslutslänkar, anpassade länkar osv. används nu även för att identifiera Link ID för variabeln Activity Map.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

Med andra ord, om du använder `tl()` för att spåra dina anpassade element hämtas länk-ID:t från värdet som skickas som den tredje parametern (länknamn) i `tl()` -metod. Den hämtas inte från standardalgoritmen för länkspårning som används för [standardspårning](activitymap-link-tracking-methodology.md) i Activity Map.

## Överläggsåtergivning för dynamiskt innehåll

När `tl()` -metoden anropas direkt från HTML-elementets on-click-händelse, kan Activity Map visa en övertäckning för det elementet när webbsidan läses in. Exempel:

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

När webbsidesinnehåll läggs till på sidan efter att den första sidan har lästs in visas `tl()` -metoden anropas indirekt och vi kan inte visa övertäckningar för det nya innehållet om det inte uttryckligen aktiveras/klickas. Därefter utlöses en ny länksamlingsprocess från Activity Map.

När `tl()` -metoden anropas inte direkt från HTML-elementets on-click-händelse. Activity Map kan bara visa övertäckning när användaren har klickat på elementet. Här är ett exempel där `tl()` metoden anropas indirekt:

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Det bästa sättet för Activity Map att täcka över länkar till dynamiskt innehåll är att ha en anpassad `ActivityMap.link` funktionen har ställts in för att anropa samma funktion vars returvärde skickas till `tl()`. Exempel:

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

Här har vi åsidosatt `ActivityMap.link` kan du göra något av tre saker när det anropas:

1. If `linkName` har passerats, sedan anropades detta av `tl()`så returnera vad `tl()` har skickats som `linkName`.
2. När det anropas av Activity Map vid rapporteringstidpunkten, en `linkName` har aldrig passerat, så ring `makeLinkName()` med länkelementet. Detta är det avgörande steget här - `makeLinkName(element)` anropet ska vara detsamma som `tl()` call&#39;s 3rd argument in the `<button>` -tagg. Detta innebär att när `tl()` anropas, vi spårar strängen som returneras av `makeLinkName()`. När Activity Map rapporterar på länkarna på sidan används samma anrop för att skapa en länk.
3. Den sista lösningen är bara att returnera det ursprungliga returvärdet för länkfunktionen ActivityMap. Om du behåller den här referensen för att anropa i standardfallet behöver du bara åsidosätta eller skriva egen kod för `makeLinkName()` och behöver inte visa ett länkreturvärde för alla länkar på sidan.
