---
title: transactionID
description: Använd den här variabeln för att länka samman online- och offlinedata.
feature: Variables
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
role: Admin, Developer
source-git-commit: e281d43204e1c5b10508661f04b880125fe8671c
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# transactionID

Variabeln `transactionID` identifierar en transaktion unikt så att träffen kan koppla till data som överförts via datakällor. Den här variabeln är värdefull när du vill använda data från andra kanaler och länka den till data som samlats in med AppMeasurement.

>[!NOTE]
>
>Kontrollera att [!UICONTROL Transaction ID Storage] är aktiverat i en rapportserie innan du använder den här variabeln. Mer information finns i [Allmänna kontoinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) i användarhandboken för Admin.

När du anger `transactionID` för en träff tar Adobe en ögonblicksbild av alla analysvariabler som angetts eller sparats vid den tidpunkten. Data som överförs via datakällor med ett matchande transaktions-ID är permanent knutna till dessa variabelvärden.

Adobe kommer ihåg alla transaktions-ID-värden (länkade och olänkade) i upp till 25 månader.

## Transaktions-ID med Web SDK

Transaktions-ID mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.payments[0].transactionID`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.transactionID` eller `data.__adobe.analytics.xact`

## Transaktions-ID med Adobe Analytics-tillägg

Du kan ange transaktions-ID när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Transaction ID].

Du kan ange transaktions-ID till vilket strängvärde som helst, inklusive dataelement.

## s.transactionID i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

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
>Om du integrerar flera offlinekanaler med den här variabeln måste du se till att olika kanaler inte överlappar transaktions-ID:n. Om du till exempel har ett transaktions-ID för kundtjänst på `1234` och ett värde för lead-transaktion-ID på `1234` kan de orsaka en konflikt och oväntade resultat. Se till att transaktions-ID:n innehåller unika format per offlinekanal och differentiera dem om det behövs. Du kan till exempel ange ditt transaktions-ID för kundtjänst till `call_1234` och ditt transaktions-ID för försäljningslead `lead_1234` i både Datakällor och AppMeasurement.
