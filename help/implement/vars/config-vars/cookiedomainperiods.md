---
title: cookieDomainPeriods
description: (Föråldrat) AppMeasurementet Hjälp avgör var cookies ska lagras när en webbplats toppnivådomän innehåller en punkt.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: c7e525b68898a6663f3b40e2293f959d4bd129b2
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---


# cookieDomainPeriods

>[!IMPORTANT]
>Den här variabeln är inaktuell. Om du använder något av följande:
>
>* AppMeasurement v2.26.x eller senare
>* Adobe Analytics-tillägg v1.9.4 eller senare
>* Adobe Experience Cloud ID-tjänst
>
>Den här variabeln gör ingenting eftersom det tillämpliga biblioteket automatiskt identifierar den domän som cookies ska användas på.

The `cookieDomainPeriods` variabeln hjälpte AppMeasurementet att avgöra var Analytics-cookies ska ställas in genom att ange att domänen på den översta nivån hade en extra period. Den här variabeln tillät AppMeasurement för den extra perioden i den översta domänen och ställer in cookies på rätt plats. Om webbplatsens toppnivådomän inte innehåller någon extra period är den här variabeln inte obligatorisk.

* För domäner som `example.co.uk` eller `www.example.co.jp`, ange variabeln till `"3"`.
* För domäner som `example.nsw.gov.au`, ange variabeln till `"4"`.
* För domäner som `example.com` eller `products.example.org`, utelämna inställningen av den här variabeln eller ange den till `"2"`.

>[!TIP]
>
>Ta inte underdomäner med i beräkningen för variabeln. Ange till exempel inte `cookieDomainPeriods` på exempelwebbadressen `store.toys.example.com`. AppMeasurementet känner igen att cookies lagras på `example.com`, även på URL:er med många underdomäner.

För implementeringar på AppMeasurement v2.26.x eller senare finns [`s_ac`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie används för att automatiskt avgöra rätt cookie-domän. Biblioteket försöker först skriva en cookie som innehåller två domänperioder. Om den här cookie-filen misslyckas försöker den igen, inklusive fler domänperioder tills den lyckas. Denna cookie tas omedelbart bort när den har angetts.

## Cookie-domänperioder som använder Web SDK

Web SDK avgör automatiskt vilken domän som ska användas för att ställa in cookies.

## Cookie-domänperioder med Adobe Analytics-tillägg

**[!UICONTROL Domain Periods]** är ett fält under [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera [!UICONTROL Cookies] dragspelspanel, som visar [!UICONTROL Domain Periods] fält.

Ange att fältet ska `3` endast på toppnivådomäner som innehåller en punkt. Annars kan fältet lämnas tomt.

## Cookie-domänperioder i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `cookieDomainPeriods` variabeln är en sträng som vanligtvis är inställd på `"3"`, endast i toppnivådomäner som innehåller en punkt. Standardvärdet är `"2"`som rymmer de flesta toppnivådomäner som `.com` och `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
