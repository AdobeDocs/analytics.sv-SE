---
title: transactionID
description: Använd den här variabeln för att länka samman online- och offlinedata.
feature: Appmeasurement Implementation
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# transactionID

Variabeln `transactionID` identifierar en transaktion unikt så att träffen kan ge dimensionsvärden till data som överförts via [datakällor för transaktions-ID](/help/import/data-sources/transactionid.md). Den här variabeln är värdefull när du vill fylla i offlinekanaldata med värden som samlats in från onlinekanaldata.

>[!NOTE]
>
>Kontrollera att [!UICONTROL Transaction ID Storage] är aktiverat i en rapportserie innan du använder den här variabeln. Mer information finns i [Allmänna kontoinställningar](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) i användarhandboken för Admin.

När du anger `transactionID` för en träff tar Adobe en ögonblicksbild av alla analysvariabler som angetts eller sparats vid den tidpunkten. I [Datakällor för transaktions-ID](/help/import/data-sources/transactionid.md) finns en lista med dimensioner som ingår i ögonblicksbilden. Adobe kommer ihåg alla transaktions-ID-värden (länkade och olänkade) i upp till 25 månader.

## Transaktions-ID med Web SDK

Transaktions-ID mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.payments[3].transactionID` eller `xdm.commerce.order.payments.transactionID`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.transactionID` eller `data.__adobe.analytics.xact`

## Transaktions-ID med Adobe Analytics-tillägg

Du kan ange transaktions-ID när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Actions]-åtgärd under [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Transaction ID].

Du kan ange transaktions-ID till vilket strängvärde som helst, inklusive dataelement.

## s.transactionID i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.transactionID` är en sträng som innehåller en unik identifierare för en transaktion. Giltiga värden är alfanumeriska tecken som är upp till 100 byte långa. Dess standardvärde är en tom sträng.

```js
s.transactionID = "ABC123";
```

Om du har fler än ett transaktions-ID för en träff kan du avgränsa varje träff med kommatecken. Flera transaktions-ID:n omfattas fortfarande av 100 byte-gränsen.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!TIP]
>
>Om du integrerar flera offlinekanaler med den här variabeln måste du se till att olika kanaler inte överlappar transaktions-ID:n. Om du till exempel har ett transaktions-ID för kundtjänst på `1234` och ett värde för lead-transaktion-ID på `1234` kan de orsaka en konflikt och oväntade resultat. Se till att transaktions-ID:n innehåller unika format per offlinekanal och differentiera dem om det behövs. Du kan till exempel ange ditt transaktions-ID för kundtjänst till `call_1234` och ditt transaktions-ID för säljlead `lead_1234` i både Datakällor och AppMeasurement.
