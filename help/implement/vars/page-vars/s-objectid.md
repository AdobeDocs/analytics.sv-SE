---
title: s_objectID
description: Hjälpaktivitetskartan identifierar unika länkar på din webbplats.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# s_objectID

Variabeln ger `s_objectID` en unik identifierare för en länk. Det används för att göra rapporter i [aktivitetskartan](/help/analyze/activity-map/activity-map.md) mer korrekta. Om du har länkar på en sida som ändras ofta, kan du använda variabeln för att visa aktivitetskartan för en unik länkplats så att den kan gruppera data på rätt sätt. `s_objectID`

Om en korrekt aktivitetskarta är viktig för din organisation rekommenderar Adobe att du inkluderar variabeln i händelse `s_objectID` `onClick` av länkar på din webbplats. Mer information finns i [Användningsexempel för länkspårning](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) av aktivitetskarta i Användarhandboken för Analysera.

## Objekt-ID i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s_objectID i AppMeasurement och Launch, anpassad kodredigerare

Variabeln `s_objectID` är en global variabel, vilket innebär att den fungerar oberoende av Analytics-spårningsobjektet (`s` som standard). Giltiga värden för den här variabeln kan vara valfri sträng som är upp till 100 byte lång. Om variabeln inte är definierad används länkens URL som identifierare.

Den här variabeln ställs vanligtvis in i händelse `onClick` av en HTML-länk.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

> [!NOTE] Inkludera alltid det semikolon som avslutar en JavaScript-programsats. Semikolon krävs för att aktivitetskartan ska fungera.

## Användningsexempel

Variabeln är användbar när du vill ha större noggrannhet i rapportering av aktivitetskartor. `s_objectID`

### Sammanställa länkar från mycket dynamiskt innehåll

Vissa webbplatser har mycket dynamiskt innehåll, till exempel nyhetssajter eller butikssajter med ofta roterande objekt. Eftersom URL:en för länken används som standard i aktivitetskartan är det svårt att förstå de områden som du klickar mest på på sidor där länkarna ändras ofta. Om du använder länkarna `s_objectID` i de här länkarna förstår Activity Map vilka länkar som kan aggregeras, oavsett vilka URL:er de pekar på.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Oavsett var länkarna pekar eller hur ofta du ändrar dessa länkar, samlar Activity Map in data baserat på värdet i `s_objectID`.

### Håll länkarna åtskilda på en sida

Vissa webbplatser har länkar som pekar på samma plats på olika platser. En länk till startsidan i sidhuvudet och sidfoten på webbplatsen. Eftersom dessa länkar har samma URL, samlar Activity Map in deras data. Du kan separera dem med hjälp av `s_objectID` variabeln:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Även om länkar pekar på samma URL kan aktivitetskartan använda variabeln för att skilja dem från varandra på rätt sätt vid rapportering. `s_objectID`
