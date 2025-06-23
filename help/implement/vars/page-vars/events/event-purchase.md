---
title: Inköpshändelse
description: Använd inköpshändelsen för att samla in data för måtten"Beställningar","Enheter" och"Intäkter".
feature: Appmeasurement Implementation
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# Inköpshändelse

Inköpshändelsen är ett värde i variabeln `events`. Det här värdet är användbart för organisationer som vill samla in data kring de intäkter som deras webbplats genererar. Den är starkt beroende av variablerna [`products`](../products.md) och [`purchaseID`](../purchaseid.md).

När du ställer in en köphändelse påverkas följande mått:

* Måtten för &quot;Beställningar&quot; ökar med 1
* Måttet Enheter ökas med antalet produkter i variabeln `products`
* Måttet för Intäkter ökar med summan av prisparametrar i variabeln `products`

>[!NOTE]
>
>Intäkter multipliceras inte med kvantitetsfältet. `s.products="Womens;Socks;5;4.50"` skickar till exempel inte 22,50 USD till intäkt, utan 4,50 USD. Se till att implementeringen överför de totala intäkterna för den angivna kvantiteten. Exempel: `s.products="Womens;Socks;5;22.50"`.

## Ställ in inköpshändelsen med Web SDK

Om du använder [**XDM-objektet**](/help/implement/aep-edge/xdm-var-mapping.md) använder inköpshändelsen följande XDM-fält:

* Beställningar har mappats till `xdm.commerce.purchases.value`.
* Enheter mappas till summan av alla `xdm.productListItems[].quantity` fält. Mer information finns i [`products`](../products.md).
* Intäkter mappas till summan av alla `xdm.productListItems[].priceTotal` fält.

```json
{
  "xdm": {
    "commerce": {
      "purchases": {
        "value": 1
      }
    }
  }
}
```

Om du använder [**dataobjektet**](/help/implement/aep-edge/data-var-mapping.md) använder inköpshändelsen `data.__adobe.analytics.events` och följande AppMeasurement-strängsyntax.

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "events": "purchase"
      }
    }
  }
}
```

## Ange inköpshändelsen med Adobe Analytics-tillägget

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Events] och ställ in listrutan [!UICONTROL Events] på [!UICONTROL purchase].

Andra beroende variabler som `products` och `purchaseID` har inte dedikerade fält i Analytics-tillägget i Adobe Experience Platform Data Collection. Använd den anpassade kodredigeraren efter AppMeasurement-syntax för dessa variabler.

## Ange inköpshändelsen i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Inköpshändelsen är en sträng som anges som en del av händelsemariabeln.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Deduplicering av inköpshändelser

När du utlöser en köphändelse kontrollerar Adobe följande:

* Innehåller träffen variabeln `purchaseID`? Annars använder Adobe information från träffen för att skapa ett&quot;tillfälligt köp-ID&quot;. Detta tillfälliga köp-ID gäller endast besökaren av träffen. De fem föregående tillfälliga inköps-ID:n lagras för varje besökar-ID per rapportsvit.
* Matchar det tillfälliga köp-ID:t något av de fem senast lagrade tillfälliga köp-ID:n? I så fall betraktas bildbegäran som ett dubblettköp. Alla konverteringsvariabler, inklusive händelsen purchase, visas inte i rapporteringen.
* Om variabeln `purchaseID` är definierad, matchar den eventuella värden som redan samlats in i rapportsviten för alla besökare? I så fall betraktas bildbegäran som ett dubblettköp. Alla konverteringsvariabler, inklusive händelsen purchase, visas inte i rapporteringen.
