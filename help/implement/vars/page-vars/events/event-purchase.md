---
title: Inköpshändelse
description: Använd inköpshändelsen för att samla in data för måtten"Beställningar","Enheter" och"Intäkter".
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 1%

---

# Inköpshändelse

Inköpshändelsen är ett värde i variabeln `events`. Det här värdet är användbart för organisationer som vill samla in data kring de intäkter som deras webbplats genererar. Den är starkt beroende av variablerna [`products`](../products.md) och [`purchaseID`](../purchaseid.md).

När du anger en köphändelse påverkas följande mått:

* Måtten för &quot;Beställningar&quot; ökar med 1
* Måttet Enheter ökas med antalet produkter i variabeln `products`
* Måttet Intäkter ökar med summan av prisparametrarna i variabeln `products`

>[!NOTE]
>
>Intäkter multipliceras inte med kvantitetsfältet. `s.products="Womens;Socks;5;4.50"` skickar till exempel inte $22.50 till intäkter; den skickar 4,50 dollar. Se till att implementeringen överför de totala intäkterna för den angivna kvantiteten. Exempel,`s.products="Womens;Socks;5;22.50"`.

## Ange köphändelsen med taggar i Adobe Experience Platform

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Events] och ställ in listrutan för händelser på [!UICONTROL purchase].

Andra beroende variabler som `products` och `purchaseID` har inte dedikerade fält i användargränssnittet för datainsamling. Använd den anpassade kodredigeraren efter AppMeasurement-syntax för dessa variabler.

## Ange inköpshändelsen i AppMeasurement och anpassad kodredigerare

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
* Om variabeln `purchaseID` är definierad, matchar den alla värden som redan samlats in i rapportsviten för alla besökare? I så fall betraktas bildbegäran som ett dubblettköp. Alla konverteringsvariabler, inklusive händelsen purchase, visas inte i rapporteringen.
