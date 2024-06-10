---
title: purchaseID
description: Deduplicera träffar baserat på en unik inköpsidentifierare.
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
source-git-commit: 4bd46fd5a9b98bcca67a66c87c9bca67fa00061a
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# purchaseID

The `purchaseID` variabeln förhindrar att träffar som innehåller samma köp får fler rapporter. Om en besökare till exempel kommer till din bekräftelsesida skickar du vanligtvis data runt intäkten som genererats från transaktionen till Adobe. Om användaren uppdaterar den här sidan flera gånger eller bokmärker sidan för att besöka den senare, kan dessa träffar generera rapporter. The `purchaseID` variabeln deduplicerar mått när mer än en träff har samma inköps-ID.

När Adobe identifierar en träff som ett dubblettköp visas inga konverteringsdata (som eVars och events) i rapporteringen. I dataflöden är `duplicate_purchase` kolumnen är inställd på `1`.

Inköp-ID gäller för alla besökare och upphör efter 37 månader. Om en besökare ställer in ett visst köp-ID, kommer en annan besökare att ställa in samma köp-ID ett år senare, det andra köpet tas bort.

## Inköps-ID med Web SDK

Inköps-ID är mappat till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.purchaseID`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.purchaseID`

## Inköps-ID med Adobe Analytics-tillägget

Du kan ange inköps-ID när du konfigurerar Analytics-tillägget (globala variabler) eller enligt regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Purchase ID] -avsnitt.

Du kan ange ett inköps-ID till ett värde eller ett dataelement. Du kan också kopiera värdet från en annan Analytics-variabel.

## s.purchaseID i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.purchaseID` variabeln är en sträng som innehåller en unik identifierare för ett köp. Den ställs in på samma träff som en köphändelse. Använd bara alfanumeriska tecken för att fylla i variabeln.

Den här variabeln kan lagra högst 20 byte. Värden som är längre än 20 byte trunkeras. Om det här trunkerade värdet matchar efterföljande trunkerade värden kommer dessa efterföljande träffar att dubbleras.

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
