---
title: purchaseID
description: Deduplicera träffar baserat på en unik inköpsidentifierare.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---


# purchaseID

Variabeln `purchaseID` förhindrar att träffar som innehåller samma köp fyller i rapporter. Om en besökare till exempel kommer till din bekräftelsesida skickar du vanligtvis data runt intäkten som genererats från transaktionen till Adobe. Om användaren uppdaterar den här sidan flera gånger eller bokmärker sidan för att besöka den senare, kan dessa träffar generera rapporter. Variabeln `purchaseID` avduplicerar mått när fler än en träff har samma inköps-ID.

När Adobe identifierar en träff som ett dubblettköp visas inga konverteringsdata (som eVars och events) i rapporteringen. I dataflöden ställs kolumnen in på `duplicate_purchase` `1`.

Inköp-ID gäller för alla besökare och upphör inte att gälla. Om en besökare ställer in ett visst köp-ID kommer en annan besökare att ställa in samma köp-ID ett år senare, det andra köpet tas bort.

## Inköps-ID i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.purchaseID i AppMeasurement och Launch custom code editor

Variabeln `s.purchaseID` är en sträng som innehåller en unik identifierare för ett köp. Den ställs in på samma träff som en köphändelse. Använd bara alfanumeriska tecken för att fylla i variabeln.

Denna variabel kan lagra högst 20 byte; värden som är längre än 20 byte trunkeras. Om det här trunkerade värdet matchar efterföljande trunkerade värden kommer dessa efterföljande träffar att dubbleras.

```js
s.purchaseID = "ABC123";
```

Om du använder `digitalData` datalagret [](../../prepare/data-layer.md):

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>Använd inte en slumpgenereringsfunktion för att generera ett köp-ID.