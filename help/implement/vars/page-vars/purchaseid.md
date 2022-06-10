---
title: purchaseID
description: Deduplicera träffar baserat på en unik inköpsidentifierare.
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# purchaseID

The `purchaseID` variabeln förhindrar att träffar som innehåller samma köp får fler rapporter. Om en besökare till exempel kommer till din bekräftelsesida skickar du vanligtvis data runt intäkten som genererats från transaktionen till Adobe. Om användaren uppdaterar den här sidan flera gånger eller bokmärker sidan för att besöka den senare, kan dessa träffar generera rapporter. The `purchaseID` variabeln deduplicerar mått när mer än en träff har samma inköps-ID.

När Adobe identifierar en träff som ett dubblettköp visas inga konverteringsdata (som eVars och events) i rapporteringen. I dataflöden är `duplicate_purchase` kolumnen är inställd på `1`.

Inköp-ID gäller för alla besökare och upphör inte att gälla. Om en besökare ställer in ett visst köp-ID, kommer en annan besökare att ställa in samma köp-ID ett år senare, det andra köpet tas bort.

## Inköps-ID med Web SDK

Inköps-ID är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fältet `commerce.order.purchaseID`.

## Inköps-ID med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.purchaseID i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.purchaseID` variabeln är en sträng som innehåller en unik identifierare för ett köp. Den ställs in på samma träff som en köphändelse. Använd bara alfanumeriska tecken för att fylla i variabeln.

Denna variabel kan lagra högst 20 byte; värden som är längre än 20 byte trunkeras. Om det här trunkerade värdet matchar efterföljande trunkerade värden kommer dessa efterföljande träffar att dubbleras.

```js
s.purchaseID = "ABC123";
```

Om du använder `digitalData` [datalager](../../prepare/data-layer.md):

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>Använd inte en slumpgenereringsfunktion för att generera ett köp-ID.
