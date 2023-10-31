---
title: transactionID
description: Använd den här variabeln för att länka samman online- och offlinedata.
feature: Variables
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
source-git-commit: ccdeaf341cf9a603da857d9425d3a2196d0f67f4
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# transactionID

The `transactionID` identifierar en transaktion unikt så att träffen kan koppla till data som överförts via datakällor. Den här variabeln är värdefull när du vill använda data från andra kanaler och länka den till data som samlats in med AppMeasurement.

>[!NOTE]
>
>Se till att [!UICONTROL Transaction ID Storage] aktiveras i en rapportsvit innan variabeln används. Se [Allmänna kontoinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) i användarhandboken för Admin om du vill ha mer information.

När du anger `transactionID` Vid en träff tar Adobe en ögonblicksbild av alla analysvariabler som angetts eller sparats vid den tidpunkten. Data som överförs via datakällor med ett matchande transaktions-ID är permanent knutna till dessa variabelvärden.

Som standard kommer Adobe ihåg alla transaktions-ID-värden (länkade och olänkade) i upp till 90 dagar. Om din interaktionsprocess är längre än 90 dagar kontaktar du kundtjänst för att förlänga den här gränsen.

## Transaktions-ID med Web SDK

Transaktions-ID är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fältet `commerce.order.payments[0].transactionID`.

## Transaktions-ID med Adobe Analytics-tillägg

Du kan ange transaktions-ID när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Transaction ID] -avsnitt.

Du kan ange transaktions-ID till vilket strängvärde som helst, inklusive dataelement.

## s.transactionID i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.transactionID` variabeln är en sträng som innehåller en unik identifierare för en transaktion. Giltiga värden är alfanumeriska tecken som är upp till 100 byte långa. Dess standardvärde är en tom sträng.

```js
s.transactionID = "ABC123";
```

Om du har fler än ett transaktions-ID för en träff kan du avgränsa varje träff med kommatecken. Flera transaktions-ID:n omfattas fortfarande av 100 byte-gränsen.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!TIP]
>
>Om du integrerar flera offlinekanaler med den här variabeln måste du se till att olika kanaler inte överlappar transaktions-ID:n. Om du till exempel har ett transaktions-ID för kundtjänst på `1234` och ett transaktions-ID för försäljningslead för `1234`kan de orsaka konflikter och oväntade resultat. Se till att transaktions-ID:n innehåller unika format per offlinekanal och differentiera dem om det behövs. Ange till exempel ditt transaktions-ID för kundtjänst till `call_1234` och ditt transaktions-ID för försäljningslead `lead_1234` i både Datakällor och AppMeasurement.
