---
title: Inköpshändelse
description: Använd inköpshändelsen för att samla in data för måtten"Beställningar","Enheter" och"Intäkter".
feature: Variables
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# Inköpshändelse

Inköpshändelsen är ett värde i `events` variabel. Det här värdet är användbart för organisationer som vill samla in data kring de intäkter som deras webbplats genererar. Den är starkt beroende av [`products`](../products.md) och [`purchaseID`](../purchaseid.md) variabler.

När du ställer in en köphändelse påverkas följande mått:

* Måtten för &quot;Beställningar&quot; ökar med 1
* Måttet Enheter ökas med antalet produkter i `products` variabel
* Inkomstmåttet ökar med summan av prisparametrarna i `products` variabel

>[!NOTE]
>
>Intäkter multipliceras inte med kvantitetsfältet. Till exempel: `s.products="Womens;Socks;5;4.50"` skickar inte 22,50 USD till intäkter, utan 4,50 USD. Se till att implementeringen överför de totala intäkterna för den angivna kvantiteten. Till exempel: `s.products="Womens;Socks;5;22.50"`.

## Ange inköpshändelsen med Web SDK

Om du använder [**XDM-objekt**](/help/implement/aep-edge/xdm-var-mapping.md) används följande XDM-fält för köphändelsen:

* Order mappas till `xdm.commerce.purchases.value`.
* Enheter mappas till summan av alla `xdm.productListItems[].quantity` fält.
* Intäkterna är mappade till summan av alla `xdm.productListItems[].priceTotal` fält.

Om du använder [**dataobjekt**](/help/implement/aep-edge/data-var-mapping.md), som köphändelsen använder `data.__adobe.analytics.events`, efter AppMeasurementen strängsyntax.

## Ange inköpshändelsen med Adobe Analytics-tillägget

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Events] och ange [!UICONTROL Events] nedrullningsbar lista till [!UICONTROL purchase].

Andra beroende variabler som `products` och `purchaseID` har inte dedikerade fält i Analytics-tillägget i Adobe Experience Platform Data Collection. Använd den anpassade kodredigeraren efter AppMeasurementen syntax för dessa variabler.

## Ange inköpshändelsen i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Inköpshändelsen är en sträng som anges som en del av händelsemariabeln.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Deduplicering av inköpshändelser

När du utlöser en köphändelse kontrollerar Adobe följande:

* Innehåller träffen `purchaseID` variabel? Annars använder Adobe information från träffen för att skapa ett&quot;tillfälligt köp-ID&quot;. Detta tillfälliga köp-ID gäller endast besökaren av träffen. De fem föregående tillfälliga inköps-ID:n lagras för varje besökar-ID per rapportsvit.
* Matchar det tillfälliga köp-ID:t något av de fem senast lagrade tillfälliga köp-ID:n? I så fall betraktas bildbegäran som ett dubblettköp. Alla konverteringsvariabler, inklusive händelsen purchase, visas inte i rapporteringen.
* Om `purchaseID` är definierad, matchar den alla värden som redan samlats in i rapportsviten för alla besökare? I så fall betraktas bildbegäran som ett dubblettköp. Alla konverteringsvariabler, inklusive händelsen purchase, visas inte i rapporteringen.
