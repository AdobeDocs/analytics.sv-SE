---
title: Inköpshändelse
description: Använd inköpshändelsen för att samla in data för måtten"Beställningar","Enheter" och"Intäkter".
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# Inköpshändelse

Inköpshändelsen är ett värde i `events` variabeln. Det här värdet är användbart för organisationer som vill samla in data kring de intäkter som deras webbplats genererar. Den är starkt beroende av `products` variabler och `purchaseID` variabler.

När du anger en köphändelse påverkas följande mått:

* Måtten för &quot;Beställningar&quot; ökar med 1
* Måttet Enheter ökas med antalet produkter i `products` variabeln
* Måttet Intäkter ökar med summan av prisparametrarna i `products` variabeln

## Ställ in inköpshändelsen i Adobe Experience Platform Launch

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Events] avsnittet och ställ in listrutan för händelser på [!UICONTROL purchase].

Andra beroende variabler som `products` och `purchaseID` saknar dedikerade fält i Launch. Använd den anpassade kodredigeraren efter AppMeasurement-syntax för dessa variabler.

## Ställ in inköpshändelsen i AppMeasurement och Launch-kodredigeraren

Inköpshändelsen är en sträng som anges som en del av händelsemariabeln.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Avduplicering av inköpshändelser

När du utlöser en köphändelse kontrollerar Adobe följande:

* Innehåller träffen `purchaseID` variabeln? Annars använder Adobe information från träffen för att skapa ett&quot;tillfälligt köp-ID&quot;. Detta tillfälliga köp-ID gäller endast besökaren av träffen. De fem föregående tillfälliga inköps-ID:n lagras för varje besökar-ID per rapportsvit.
* Matchar det tillfälliga köp-ID:t något av de fem senast lagrade tillfälliga köp-ID:n? I så fall betraktas bildbegäran som ett dubblettköp. Alla konverteringsvariabler, inklusive händelsen purchase, visas inte i rapporteringen.
* Om variabeln är definierad, matchar den eventuella värden som redan samlats in i rapportsviten för alla besökare? `purchaseID` I så fall betraktas bildbegäran som ett dubblettköp. Alla konverteringsvariabler, inklusive händelsen purchase, visas inte i rapporteringen.
