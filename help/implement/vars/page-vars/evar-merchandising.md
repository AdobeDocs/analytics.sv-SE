---
title: eVar (Merchandising)
description: Egna variabler som knyts till enskilda produkter.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---


# eVar (Merchandising)

*Den här hjälpsidan beskriver hur du implementerar eVars för varuexponering. Mer information om hur du marknadsför eVars fungerar som en dimension finns i[eVars (Merchandising)](/help/components/dimensions/evar-merchandising.md)i användarhandboken för komponenter.*

## Konfigurera eVars i inställningarna för rapportsviten

Innan du använder eVars i implementeringen måste du konfigurera eVar till önskad syntax i rapportsvitens inställningar. Se [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.

>[!IMPORTANT] Om det inte går att konfigurera eVars för försäljning korrekt resulterar det i oväntade värden eller dataförlust för variabeln. Kontrollera att den är korrekt konfigurerad för din implementering.

## Implementera med produktsyntax

När Produktsyntax är aktiverat fylls kategorin i direkt i `products` variabeln, så det är inte nödvändigt att välja och ställa in en bindningshändelse. Detta är den rekommenderade metoden och bör användas om inte värdet inte är tillgängligt för att anges `products` när händelsen success inträffar.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

Värdet för `eVar1` tilldelas produkten. Alla efterföljande lyckade händelser som berör den här produkten krediteras eVar-värdet.

## Implementera med konverteringsvariabelsyntax

Konverteringsvariabelsyntax används när eVar-värdet inte är tillgängligt för att anges i `products` variabeln. Detta scenario innebär vanligtvis att sidan inte har något sammanhang för försäljningskanalen eller sökmetoden. I dessa fall ställer du in variabeln för försäljning innan du kommer till produktsidan, och värdet kvarstår tills bindningshändelsen inträffar.

När bindningshändelsen som väljs under konfigurationen inträffar, kopplas det beständiga värdet för eVar till produkten. Om `prodView` till exempel anges som bindningshändelse är marknadsföringskategorin bunden till den aktuella produktlistan endast när händelsen inträffar. Endast efterföljande bindningshändelser kan uppdatera en eVar för försäljning som redan har tilldelats en produkt.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

Värdet `"Aviary"` för `eVar1` tilldelas produkten `"Canary"`. Alla efterföljande lyckade händelser som berör den här produkten krediteras `"Canary"`. Dessutom är det aktuella värdet av variabeln merchandising knutet till alla efterföljande produkter tills något av följande villkor uppfylls:

* eVar förfaller (baserat på inställningen &quot;Förfaller efter&quot;)
* Försäljningen av eVar skrivs över med ett nytt värde.
