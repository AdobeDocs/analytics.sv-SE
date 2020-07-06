---
title: transactionID
description: Använd den här variabeln för att länka samman online- och offlinedata.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 1%

---


# transactionID

Variabeln identifierar en transaktion unikt så att träffen kan koppla till data som överförs via datakällor. `transactionID` Den här variabeln är värdefull när du vill använda data från andra kanaler och länka den till data som samlats in med AppMeasurement.

>[!NOTE]
>
>Kontrollera att [!UICONTROL Transaction ID Storage] är aktiverat i en rapportserie innan du använder den här variabeln. Mer information finns i [Allmänna kontoinställningar](/help/admin/admin/general-acct-settings-admin.md) i användarhandboken för Admin.

När du väljer `transactionID` en träff tar Adobe en ögonblicksbild av alla Analytics-variabler som då är inställda eller beständiga. Data som överförs via datakällor med ett matchande transaktions-ID är permanent knutna till dessa variabelvärden.

Som standard kommer Adobe ihåg alla transaktions-ID-värden (länkade och olänkade) i upp till 90 dagar. Om din interaktionsprocess är längre än 90 dagar kontaktar du kundtjänst för att förlänga den här gränsen.

## Transaktions-ID i Adobe Experience Platform Launch

Du kan ange transaktions-ID när du konfigurerar Analytics-tillägget (globala variabler) eller enligt regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan [!UICONTROL Extension] på Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Transaction ID] avsnittet.

Du kan ange transaktions-ID till vilket strängvärde som helst, inklusive dataelement.

## s.transactionID i AppMeasurement och Launch, anpassad kodredigerare

Variabeln `s.transactionID` är en sträng som innehåller en unik identifierare för en transaktion. Giltiga värden är alfanumeriska tecken som är upp till 100 byte långa. Dess standardvärde är en tom sträng.

```js
s.transactionID = "ABC123";
```

Om du har fler än ett transaktions-ID för en träff kan du avgränsa varje träff med kommatecken. Flera transaktions-ID:n omfattas fortfarande av 100 byte-gränsen.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!NOTE]
>
>Om du integrerar flera offlinekanaler med den här variabeln måste du se till att olika kanaler inte överlappar transaktions-ID:n. Om du till exempel har ett transaktions-ID för kundtjänst på `1234` och ett ID-värde för lead-transaktion på `1234`kan de orsaka en konflikt och oväntade resultat. Se till att transaktions-ID:n innehåller unika format per offlinekanal och differentiera dem om det behövs. Du kan till exempel ställa in ditt transaktions-ID för kundtjänst på `call_1234` och ditt transaktions-ID för säljlead `lead_1234` i både Datakällor och AppMeasurement.
