---
title: cookieDomainPeriods
description: Hjälp AppMeasurementet att förstå vilken domän cookies ska lagras i om domänen har en punkt i suffixet.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 0%

---


# cookieDomainPeriods

AppMeasurementet avgör dess cookie-plats genom att titta på domänen och domänsuffixet. För domäner som `example.com`, ställer AppMeasurementet in cookies på rätt plats. För andra domäner som `example.co.uk`, kan AppMeasurementet av misstag ange cookies på `co.uk`. De flesta webbläsare avvisar cookies som angetts i den här ogiltiga domänen, vilket orsakar problem med besökaridentifiering.

The `cookieDomainPeriods` variabeln hjälper AppMeasurementet att avgöra var Analytics-cookies anges genom att anropa att domänsuffixet har en extra period. Den här variabeln gör att AppMeasurementet kan ta emot den extra perioden i domänsuffixet och ange cookies på rätt plats.

* För domäner som `example.com` eller `www.example.com`behöver den här variabeln inte anges. Om det behövs kan du ange variabeln till `"2"`.
* För domäner som `example.co.uk` eller `www.example.co.jp`, ange variabeln till `"3"`.


>[!IMPORTANT]
>
>Ta inte underdomäner med i beräkningen för variabeln. Ange till exempel inte `cookieDomainPeriods` på exempelwebbadressen `store.toys.example.com`. AppMeasurementet känner som standard igen att cookies ska lagras på `example.com`, även på URL:er med många underdomäner.


## Cookie-domänperioder, cookies från tredje part och identifiering av äldre besökare

Endast när du använder den gamla Adobe Analytics-besökaridentifieraren (i stället för den rekommenderade Experience Cloud Identity-tjänsten) är den implicita eller explicita konfigurationen av `cookieDomainPeriods` kan påverka hur besökare identifieras, beroende på om cookies från tredje part blockeras eller inte.

I följande tabell visas fyra möjliga scenarier.

| Scenario | `cookieDomainPeriods` konfigurationen är ... | Är cookies från tredje part blockerade? | Resultat vid användning av tidigare Adobe Analytics besöksidentifieringstjänst |
|:---:|---|---|---|
| 1 | <span style="color:green">Korrigera</span> | Nej | Besökarna identifieras med en `s_vi` cookie, serversidan. |
| 2 | <span style="color:green">Korrigera</span> | Ja | Besökarna identifieras med en reservlinje `s_fid` cookie, ange klientsida (siddomän från första part). |
| 3 | <span style="color:red">Felaktig</span> | Nej | Besökare identifieras med en reservidentifierare som baseras på en kombination av användaragent och IP-adress. <br/>AppMeasurementet måste ange cookies som cookies från tredje part.<br/> The `s_vi` cookie kan anges när `cookieDomainPeriods` inte överförs korrekt. |
| 4 | <span style="color:red">Felaktig</span> | Ja | Besökare identifieras med en reservidentifierare som baseras på en kombination av användaragent och IP-adress.<br/>AppMeasurementet måste ange cookies som blockerade cookies från tredje part, så inga cookies anges. |

>[!CAUTION]
>
>Du kan ha konfigurerat av misstag `cookieDomainPeriods` <span style="color:red">felaktig</span> (lämna standardvärdet `"2"`) när du använder domäner som `example.co.uk`. Detta implicita felaktiga konfigurationsresultat som identifierar besökare efter scenario 3 eller 4.
>
>AppMeasurementen version 2.26.x eller senare konfigureras `cookieDomainPeriods` automatiskt med rätt värde så att endast scenarierna 1 eller 2 är möjliga. När du uppdaterar till AppMeasurement version 2.26.x eller senare, och för närvarande identifierar besökare felaktigt (scenario 3 eller 4), får uppdateringen större konsekvenser.
>
>* Besöksidentifierare återställs och besökarna visas som nya besökare. Det finns inget sätt att koppla ny aktivitet till den tidigare besökaridentifieraren.
>* Cookies anges (t.ex. för länkspårning eller aktivitetskarta).`s_sq` cookie), vilket leder till plötsliga skillnader i rapporteringen.
>
>Vid korrekt konfigurering `cookieDomainPeriods` kommer att förbättra funktionaliteten för AppMeasurement och analys, vi rekommenderar att du utvärderar om du påverkas av ändringarna som uppstår när du uppgraderar ditt AppMeasurement-bibliotek.
>
> Se [Analytics-cookies](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html) om du vill ha mer information om de cookies som AppMeasurementet använder.

## Cookie-domänperioder som använder Web SDK

Web SDK kan identifiera rätt cookie-lagringsdomän utan den här variabeln.

## Cookie-domänperioder med Adobe Analytics-tillägg

Domänperioder är ett fält under [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera [!UICONTROL Cookies] dragspelspanel, som visar [!UICONTROL Domain Periods] fält.

Ange att fältet ska `3` endast på domäner som innehåller en punkt i suffixet. Annars kan fältet lämnas tomt.

## Cookie-domänperioder i AppMeasurementet code och den anpassade kodredigeraren för Analytics-tillägget

Du kan ange `cookieDomainPeriods` i AppMeasurementets JavaScript-bibliotek eller i den anpassade kodredigeraren för Analytics-tillägget.

The `cookieDomainPeriods` variabeln är en sträng som vanligtvis är inställd på `"3"`, endast i domäner som innehåller en punkt i suffixet. Standardvärdet är `"2"`, som rymmer de flesta domäner.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
