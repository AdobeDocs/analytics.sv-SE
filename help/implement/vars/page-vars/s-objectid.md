---
title: s_objectID
description: Hjälp Activity Map att identifiera unika länkar på er webbplats.
feature: Appmeasurement Implementation
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# s_objectID

Variabeln `s_objectID` ger en unik identifierare för en länk. Den används för att göra rapporter i [Activity Map](/help/analyze/activity-map/overview.md) mer korrekta. Om du har länkar på en sida som ändras ofta kan du använda variabeln `s_objectID` för att ange för Activity Map vilken unik länkplats som ska användas, så att data kan grupperas korrekt.

Om Activity Map-precision är viktig för din organisation rekommenderar Adobe att du inkluderar variabeln `s_objectID` i händelsen `onClick` för länkar på din webbplats.

## Objekt-ID som använder Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s_objectID i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s_objectID` är en global variabel, vilket innebär att den fungerar oberoende av Analytics-spårningsobjektet (`s` som standard). Giltiga värden för den här variabeln kan vara valfri sträng som är upp till 100 byte lång. Om variabeln inte är definierad används länktexten som identifierare för länken.

Den här variabeln ställs vanligtvis in i händelsen `onClick` för en HTML-länk.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>Inkludera alltid det semikolon som avslutar en JavaScript-programsats. Semikolon krävs för att Activity Map ska fungera.

## Användningsexempel

Variabeln `s_objectID` är värdefull när du vill ha större noggrannhet i Activity Map-rapportering.

### Sammanställa länkar från mycket dynamiskt innehåll

Vissa webbplatser har mycket dynamiskt innehåll, till exempel nyhetssajter eller butikssajter med ofta roterande objekt. Eftersom länkens URL används som standard i Activity Map är det svårt att förstå de områden där länkarna ändras ofta. Om du använder `s_objectID` i de här länkarna förstår Activity Map vilka länkar som kan aggregeras, oavsett vilka URL-adresser de pekar på.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Oavsett var länkarna pekar eller hur ofta du ändrar länkarna, samlar Activity Map in data baserat på värdet i `s_objectID`.

### Håll länkarna åtskilda på en sida

Vissa webbplatser har länkar som pekar på samma plats på olika platser. En länk till startsidan i sidhuvudet och sidfoten på webbplatsen. Eftersom de här länkarna har samma URL-adress sammanställer Activity Map deras data. Du kan separera dem med variabeln `s_objectID`:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Även om länkar pekar på samma URL kan Activity Map använda variabeln `s_objectID` för att skilja dem åt när de rapporteras korrekt.
