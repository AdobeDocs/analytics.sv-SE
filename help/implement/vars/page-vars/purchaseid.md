---
title: purchaseID
description: Deduplicera träffar baserat på en unik inköpsidentifierare.
feature: Appmeasurement Implementation
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# purchaseID

Variabeln `purchaseID` hjälper till att förhindra träffar som innehåller samma köp från att generera fler rapporter. Om en besökare till exempel kommer till din bekräftelsesida skickar du vanligtvis data runt intäkterna från transaktionen till Adobe. Om användaren uppdaterar den här sidan flera gånger eller bokmärker sidan för att besöka den senare, kan dessa träffar generera rapporter. Variabeln `purchaseID` avduplicerar mått när fler än en träff har samma inköps-ID.

När Adobe identifierar en träff som ett dubblettköp visas inga konverteringsdata (som eVars och events) i rapporter. I dataflöden är kolumnen `duplicate_purchase` inställd på `1`.

Inköp-ID gäller för alla besökare och upphör efter 37 månader. Om en besökare ställer in ett visst köp-ID, kommer en annan besökare att ställa in samma köp-ID ett år senare, det andra köpet tas bort.

## Inköps-ID med webb-SDK

Inköps-ID är mappat till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.purchaseID`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.purchaseID`

## Inköps-ID med Adobe Analytics-tillägget

Du kan ange inköps-ID när du konfigurerar Analytics-tillägget (globala variabler) eller enligt regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Purchase ID].

Du kan ange ett inköps-ID till ett värde eller ett dataelement. Du kan också kopiera värdet från en annan Analytics-variabel.

## s.purchaseID i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.purchaseID` är en sträng som innehåller en unik identifierare för ett köp. Den ställs in på samma träff som en köphändelse. Använd bara alfanumeriska tecken för att fylla i variabeln.

Den här variabeln kan lagra högst 20 byte. Värden som är längre än 20 byte trunkeras. Om det här trunkerade värdet matchar efterföljande trunkerade värden kommer dessa efterföljande träffar att dubbleras.

```js
s.purchaseID = "ABC123";
```

Om `digitalData` [datalagret](../../prepare/data-layer.md) används:

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>Använd inte en slumpgenereringsfunktion för att generera ett köp-ID.
