---
title: eVar-variabler
description: Egna variabler som knyts till enskilda produkter.
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 0%

---

# eVar (Merchandising)

*Den här hjälpsidan beskriver hur du implementerar eVars för varuexponering. Mer information om hur eVars marknadsförs fungerar som en dimension finns i [eVars (Merchandising)](/help/components/dimensions/evar-merchandising.md) i användarhandboken för komponenter.*

Mer information om hur du marknadsför eVars finns i [Merchandising eVars and product finding methods](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=en).

## Konfigurera eVars i inställningarna för rapportsviten

Innan du använder eVars i implementeringen måste du konfigurera eVar till önskad syntax i rapportsvitens inställningar. Se [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.

>[!WARNING]
>
>Om det inte går att konfigurera eVars för försäljning korrekt resulterar det i oväntade värden eller dataförlust för variabeln. Kontrollera att den är korrekt konfigurerad för din implementering.

## Implementera med produktsyntax

När Produktsyntax är aktiverad fylls kategorin i direkt i `products` -variabel, så det är inte nödvändigt att välja och ställa in en bindningshändelse. Detta är den rekommenderade metoden och bör användas om inte värdet är tillgängligt för att anges i `products` när framgångshändelsen äger rum.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

Värdet för `eVar1` har tilldelats produkten. Alla efterföljande lyckade händelser som berör den här produkten krediteras eVar.

## Implementera med konverteringsvariabelsyntax

Konverteringsvariabelsyntaxen används när eVar inte är tillgängligt för att anges i `products` variabel. Det här scenariot innebär vanligtvis att sidan inte har något sammanhang för försäljningskanalen eller sökmetoden. I dessa fall ställer du in variabeln för försäljning innan du kommer till produktsidan, och värdet kvarstår tills bindningshändelsen inträffar.

När bindningshändelsen som väljs under konfigurationen inträffar, associeras det beständiga värdet för eVar med produkten. Om `prodView` anges som bindningshändelse, är marknadsföringskategorin knuten till den aktuella produktlistan endast när händelsen inträffar. Endast efterföljande bindningshändelser kan uppdatera en försäljningsprodukt som redan har tilldelats en eVar.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

Värdet `"Aviary"` for `eVar1` har tilldelats produkten `"Canary"`. Alla efterföljande lyckade händelser som berör den här produkten krediteras `"Canary"`. Dessutom är det aktuella värdet av variabeln merchandising knutet till alla efterföljande produkter tills något av följande villkor uppfylls:

* eVar förfaller (baserat på inställningen &quot;Förfaller efter&quot;)
* eVar för försäljning skrivs över med ett nytt värde.
