---
description: Översikt över vilka data Adobe Analytics samlar in och andra sekretessvillkor.
keywords: sekretess
title: Sekretessöversikt
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: ee0bf5beeac3c9780eb0c8420845114f7e840aec
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 11%

---

# Sekretessöversikt

Besökarna kan lära sig mer om hur Adobe i allmänhet använder information som samlas in i [Adobes sekretesscenter](https://www.adobe.com/se/privacy.html). Det är upp till er organisation att redovisa hur ni använder Adobes produkter och tjänster, eftersom ni exklusivt styr hur ni ska implementera Adobes tjänster. Din organisation ansvarar för att följa din egen integritetspolicy, ditt serviceavtal med Adobe och alla tillämpliga lagar.

Adobe rekommenderar starkt att du följer följande övergripande koncept:

* **Samla inte in personligt identifierbar information i Adobe Analytics.** Med anpassade variabler kan du samla in praktiskt taget allt som du har åtkomst till, men du måste också ta hänsyn till din organisations sekretesspolicy och tillämpliga lagar.
* **Förse besökarna med lättillgänglig och lättbegriplig information om avanmälningsinformation.** Tillåt dem att avanmäla allt som inte är absolut nödvändigt. De flesta länder i EU anser inte att cookies i analyser är absolut nödvändiga.

## Uppdelning av datainsamling

Adobe Analytics samlar automatiskt in eller kan samla in följande typer av data:

| Typ av data | Information | Exempelvariabler som innehåller dessa data |
| --- | --- | --- |
| Sidnamn eller URL-adresser för webbsidor på din webbplats | Alltid samlade. URL eller sidnamn krävs för varje träff. | [Sida](../components/dimensions/page.md), [Sidans URL](../components/dimensions/page-url.md) |
| Tidsbaserade data | Alltid samlade. Tidsstämpel krävs för datainsamling och tidsbaserade data hämtas från tidsstämpeln. | [Tid som använts på sidan](../components/dimensions/time-spent-on-page.md), [Timme på dagen](../components/dimensions/hour-of-day.md), [AM/PM](../components/dimensions/am-pm.md), [Veckodag/vecka](../components/dimensions/weekday-weekend.md), [Veckodag](../components/dimensions/day-of-week.md), [Månad på året](../components/dimensions/month-of-year.md) |
| Data från webbsidor på andra webbplatser | Adobe kan inte samla in data på icke-närstående webbplatser där du inte kan ändra webbplatsens källkod. AppMeasurementet samlar automatiskt in den refererande URL:en när en besökare kommer till webbplatsen. Du kan anpassa implementeringen för att samla in data inom frågesträngar efter att de har anlänt till din webbplats. | [Referent](../components/dimensions/referrer.md), [Refererande domän](../components/dimensions/referring-domain.md) |
| Anonymiserade besökar-ID:n | AppMeasurementet genererar automatiskt och refererar till ett besökar-ID för varje webbläsare som besöker webbplatsen. Detta ID lagras i en cookie. Om cookies inte är tillgängliga för en viss implementering använder Adobe Analytics en reservmetod för identifiering av besökare med hjälp av IP-adress och användaragentsträng. Se [Adobe Analytics och webbläsarcookies](cookies/cookies.md) för mer information. | [Unika besökare](../components/metrics/unique-visitors.md) |
| Identifierbara besökar-ID | Adobe samlar inte automatiskt in anpassade besökar-ID:n. Du kan dock anpassa implementeringen för att samla in dessa data. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| Extern sökterm | AppMeasurementet försöker att automatiskt samla in dessa data baserat på den refererande URL:en. Många moderna sökmotorer innehåller dock inte längre den här informationen. | [Söknyckelord](../components/dimensions/search-keyword.md) |
| Interna söktermer | Adobe samlar inte automatiskt in interna sökdata. Men ni kan anpassa implementeringen för att samla in data, och det är en vanlig metod för organisationer som använder Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Specifikationer för dator och webbläsare | AppMeasurementet samlar automatiskt in webbläsartips med låg entropi, t.ex. webbläsartyp, operativsystemtyp och om enheten är stationär eller mobil. Det krävs en konfiguration för att samla in tips för hög entropi, till exempel webbläsarens specifika version/build, enhetsmodellen eller operativsystemets version. Se [Översikt över klienttips](client-hints.md) för mer information. | [Webbläsare](../components/dimensions/browser.md), [Operativsystem](../components/dimensions/operating-systems.md), [Mobila dimensioner](../components/dimensions/mobile-dimensions.md), [Bildskärmsupplösning](../components/dimensions/monitor-resolution.md) |
| Geoplatsinformation | Adobe kan aktivera eller inaktivera insamling av geolokaliseringsdata för varje webbplats eller app (på rapportsvitnivå). Många implementeringstyper, inklusive AppMeasurement, samlar automatiskt in dessa data. | [Städer](../components/dimensions/cities.md), [Regioner](../components/dimensions/regions.md), [Länder](../components/dimensions/countries.md) |
| IP-adress | Adobe erbjuder möjlighet att skymma den sista oktetten eller helt skymma besökarens IP-adress när dessa data lagras. EMEA-kunder har vanligtvis en IP-adress som är helt dold som standard. IP-adressen är inte tillgänglig som en dimension i Adobe Analytics; den ingår endast i rådata ([Dataflöden](../export/analytics-data-feed/data-feed-overview.md)). | Ingen |
| Formulärinformation finns på din webbplats | Alla implementeringstyper kräver konfiguration för att samla in dessa data. Du kan inkludera dessa data i anpassade variabler. | [eVar](../components/dimensions/evar.md) |
| Lägger till eller länkar som klickas på på webbplatsen | Samlas in automatiskt om AppMeasurement används. Ytterligare information, till exempel platsen för klickningarna, är tillgänglig när Activity Map är aktiverat. | [Activity Map](../analyze/activity-map/activity-map.md), [Avsluta länk](../components/dimensions/exit-link.md), [Hämta länk](../components/dimensions/download-link.md) |
| Produkter som köpts på er webbplats | Alla implementeringstyper kräver konfiguration för att samla in dessa data. I Adobe finns flera standardvariabler för att lagra den här informationen. | [Produkt](../components/dimensions/product.md), [Beställningar](../components/metrics/orders.md), [Intäkter](../components/metrics/revenue.md) |

{style="table-layout:auto"}

Se navigeringsmenyn under [Översikt över Dimensioner](../components/dimensions/overview.md) och [Översikt över mått](../components/metrics/overview.md) för fler variabler som Adobe kan samla in data under.
