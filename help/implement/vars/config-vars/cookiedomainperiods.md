---
title: cookieDomainPeriods
description: (Föråldrat) Hjälp AppMeasurement att avgöra var cookies ska lagras när en webbplats toppnivådomän innehåller en punkt.
feature: Appmeasurement Implementation
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
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

Variabeln `cookieDomainPeriods` hjälpte AppMeasurement att avgöra var Analytics-cookies ska anges genom att ange att den översta domänen har en extra period. Denna variabel gjorde att AppMeasurement kunde ta emot den extra perioden i domänen på den översta nivån och ange cookies på rätt plats. Om webbplatsens toppnivådomän inte innehåller någon extra period är den här variabeln inte obligatorisk.

* För domäner som `example.co.uk` eller `www.example.co.jp` anger du den här variabeln till `"3"`.
* För domäner som `example.nsw.gov.au` anger du den här variabeln till `"4"`.
* För domäner som `example.com` eller `products.example.org` utelämnar du inställningen av den här variabeln eller anger den till `"2"`.

>[!TIP]
>
>Ta inte underdomäner med i beräkningen för variabeln. Ange till exempel inte `cookieDomainPeriods` för exempel-URL:en `store.toys.example.com`. AppMeasurement känner igen att cookies lagras på `example.com`, även på URL:er med många underdomäner.

För implementeringar på AppMeasurement v2.26.x eller senare används cookien [`s_ac`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) för att automatiskt avgöra rätt cookie-domän. Biblioteket försöker först skriva en cookie som innehåller två domänperioder. Om den här cookie-filen misslyckas försöker den igen, inklusive fler domänperioder tills den lyckas. Denna cookie tas omedelbart bort när den har angetts.

## Cookie-domänperioder som använder Web SDK

Web SDK avgör automatiskt vilken domän som ska användas för att ställa in cookies.

## Cookie-domänperioder med Adobe Analytics-tillägg

**[!UICONTROL Domain Periods]** är ett fält under dragspelet [!UICONTROL Cookies] när Adobe Analytics-tillägget konfigureras.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera dragspelsfliken [!UICONTROL Cookies] som visar fältet [!UICONTROL Domain Periods].

Ange det här fältet som `3` endast i toppnivådomäner som innehåller en punkt. Annars kan fältet lämnas tomt.

## Cookie-domänperioder i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `cookieDomainPeriods` är en sträng som vanligtvis är inställd på `"3"`, endast i toppnivådomäner som innehåller en punkt. Dess standardvärde är `"2"`, som rymmer de flesta toppnivådomäner som `.com` och `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
