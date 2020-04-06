---
description: Beskriver hur instanser beräknas på försäljningsvariabler.
keywords: Analytics Implementation
title: Instanser av försäljningsvariabler
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Instanser av försäljningsvariabler

Beskriver hur instanser beräknas på försäljningsvariabler.

Instanser stöds för närvarande inte för försäljningsvariabler. Om du observerar instanser i en rapport som innehåller en försäljningsvariabel anger det att eVar anges på vissa platser utanför produktsträngen och inte ska betraktas som ett sant antal instanser för den valda försäljningsvariabeln.

Om du använder konverteringsvariabelsyntax räknas en instans varje gång variabeln ställs in. Instansen tilldelas emellertid till &quot;Ingen&quot; såvida inte följande inträffar varje gång variabeln anges:

* En bindningshändelse har angetts.
* Variabeln products anges.
* Försäljningen av eVar har ett värde.

Följande instans av eVar1 tilldelas till exempel &quot;Utomhus:Ski Goggles&quot;:

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

I nästa exempel tilldelas emellertid instansen av eVar1 till &quot;Inget&quot; eftersom alla villkor inte uppfylls när eVar är inställd (det finns ingen bindningshändelse och variabeln products är inte inställd):

Sidan 1 av besöket:

```js
s.eVar1="Outdoors:Ski Goggles"
```

Sidan 2 av besöket:

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

Allokering till Ingen sker om du anger ett värde för en eVar på en sida där ingen bindningshändelse inträffar, eller om du anger värdet eVar i produktsträngen utan en bindningshändelse.

>[!NOTE] Den aktuella funktionen för att räkna instanser av försäljningsvariabler granskas och är planerad att ändras i en kommande version.

