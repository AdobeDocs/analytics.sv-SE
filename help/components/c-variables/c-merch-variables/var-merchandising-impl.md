---
description: Beskriver hur du aktiverar och implementerar en försäljningsvariabel.
keywords: Analytics Implementation;merchandising;variable;product syntax;Conversion Variable Syntax;s.products
title: Implementera en försäljningsvariabel
topic: Developer and implementation
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementera en försäljningsvariabel

Beskriver hur du aktiverar och implementerar en försäljningsvariabel.

## Aktivera en marknadsföringsvariabel

Marknadsföring kan aktiveras för alla anpassade eVar under **[!UICONTROL Admin Tools]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Conversion Variables]**.

![](assets/merch-enable.png)

| Inställning | Beskrivning |
|--- |--- |
| Förfaller efter | Avgör hur länge försäljningsvärden ska vara. |
| Merchandising | **Produktsyntax:** Värdet anges inuti `s.products`.<br>**Konverteringsvariabelsyntax:**Värdet anges i den avsedda varuexponeringen eVar. |
| Marknadsföringsbindningshändelse (endast variabelsyntax för konvertering) | Anger när en produkt ska vara knuten till den aktuella marknadsföringskategorin. Du kan markera flera händelser genom att hålla ned Ctrl och klicka på flera objekt i listan. Du kan bara välja en händelse när du har valt &quot;Konverteringsvariabelsyntax&quot;. |

## Implementera med produktsyntax

När produktsyntax är aktiverat fylls försäljningskategorin i direkt i produktvariabeln, så det är inte nödvändigt att välja och ställa in en bindningshändelse. Detta är den rekommenderade metoden och bör användas om inte värdet inte är tillgängligt för att anges `s.products` när händelsen success inträffar.

### Syntax

```js
s.products="category;product;quantity;price;event_incrementer;eVarN=merch_category|eVarM=merch_category2";
```

### Exempel

```js
s.events="prodView";
s.products=";Snow Goggles;;;;eVar1=goggles";
```

Värdet &quot;goggles&quot; för eVar1 tilldelas produkten &quot;Snow Goggles&quot;. Alla efterföljande lyckade händelser (som produkttillägg, utcheckningar, inköp osv.) som berör den här produkten krediteras&quot;glasögon&quot;.

## Implementera med konverteringsvariabelsyntax

Konverteringsvariabelsyntax ska användas när eVar-värdet inte är tillgängligt att ange i `s.products`. Det betyder vanligtvis att sidan inte har något sammanhang för försäljningskanalen eller sökmetoden. I dessa fall måste du ange variabeln för försäljning innan du kommer till produktsidan, och värdet kvarstår tills bindningshändelsen inträffar.

När bindningshändelsen som väljs under konfigurationen inträffar, kopplas det beständiga värdet för eVar till produkten. Om prodView till exempel anges som bindningshändelse är marknadsföringskategorin bunden till den aktuella produktlistan endast när händelsen inträffar. Endast efterföljande bindningshändelser kan uppdatera en eVar för försäljning som redan har tilldelats en produkt.

### Syntax

Placera på samma eller föregående sida före bindningshändelsen:

```js
s.eVar1="merchandising_category";
```

Placera på sidan där bindningshändelsen inträffar:

```js
s.events="prodView";
s.products="category;product";
```

### Exempel

På sidan 1 av besöket ska det

```js
s.eVar1="Outdoors"
```

På sidan 2 av besöket ska det

```js
s.events="prodView";
s.products=";Snow Goggles";
```

Värdet &quot;Outdoor&quot; för eVar1 tilldelas produkten &quot;Snow Goggles&quot;. Alla efterföljande lyckade händelser (som produkttillägg, utcheckningar, inköp osv.) som berör den här produkten krediteras&quot;Snow Goggles&quot;. Dessutom är det aktuella värdet av variabeln merchandising knutet till alla efterföljande produkter tills något av följande villkor uppfylls:

* eVar förfaller (baserat på inställningen &quot;Förfaller efter&quot;)
* Försäljningen av eVar skrivs över med ett nytt värde.

## Extern ytterligare information

[Advanced Conversion Syntax Merchandising](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/) on [!DNL analyticsdemystified.com]
