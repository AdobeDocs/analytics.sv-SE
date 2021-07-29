---
title: transactionID
description: Använd den här variabeln för att länka samman online- och offlinedata.
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 0%

---

# transactionID

Variabeln `transactionID` identifierar en transaktion unikt så att träffen kan koppla till data som överförs via datakällor. Den här variabeln är värdefull när du vill använda data från andra kanaler och länka den till data som samlats in med AppMeasurement.

>[!NOTE]
>
>Kontrollera att [!UICONTROL Transaction ID Storage] är aktiverat i en rapportsserie innan du använder den här variabeln. Mer information finns i [Allmänna kontoinställningar](/help/admin/admin/general-acct-settings-admin.md) i användarhandboken för Admin.

När du anger `transactionID` för en träff tar Adobe en &quot;ögonblicksbild&quot; av alla analysvariabler som angetts eller sparats vid den tidpunkten. Data som överförs via datakällor med ett matchande transaktions-ID är permanent knutna till dessa variabelvärden.

Som standard kommer Adobe ihåg alla transaktions-ID-värden (länkade och olänkade) i upp till 90 dagar. Om din interaktionsprocess är längre än 90 dagar kontaktar du kundtjänst för att förlänga den här gränsen.

## Transaktions-ID med hjälp av taggar i Adobe Experience Platform

Du kan ange transaktions-ID när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Gå till avsnittet [!UICONTROL Transaction ID].

Du kan ange transaktions-ID till vilket strängvärde som helst, inklusive dataelement.

## s.transactionID i AppMeasurement och anpassad kodredigerare

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
>Om du integrerar flera offlinekanaler med den här variabeln måste du se till att olika kanaler inte överlappar transaktions-ID:n. Om du till exempel har ett transaktions-ID för kundtjänst på `1234` och ett värde för lead-transaktion-ID på `1234`, kan de orsaka en konflikt och oväntade resultat. Se till att transaktions-ID:n innehåller unika format per offlinekanal och differentiera dem om det behövs. Du kan till exempel ange ditt transaktions-ID för kundtjänst till `call_1234` och ditt transaktions-ID för säljlead `lead_1234` i både Datakällor och AppMeasurement.
