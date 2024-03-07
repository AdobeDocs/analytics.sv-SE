---
description: Översikt över vilka data Adobe Analytics samlar in och andra sekretessvillkor.
keywords: sekretess
title: Sekretessöversikt
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 1%

---

# Sekretessöversikt

Adobe vill aktivera er organisation så att ni kan följa gällande lagar och bestämmelser. Se [Adobe Experience Cloud sekretess](https://www.adobe.com/privacy/experience-cloud.html){target=_blank} för mer information. Mellan Adobe Analytics och din organisation fungerar Adobe som&quot;personuppgiftsbiträde&quot; och du är&quot;personuppgiftsansvarig&quot; (eller motsvarande enligt gällande sekretess- och dataskyddslagstiftning). Det är upp till er organisation att redovisa hur ni använder Adobe och tjänster eftersom er organisation exklusivt styr hur ni implementerar Adobe lösningar. När du använder Adobe Analytics ansvarar din organisation för att följa din egen integritetspolicy, ditt serviceavtal med Adobe och alla tillämpliga lagar.

Adobe rekommenderar starkt att du följer följande övergripande koncept:

* **Om du samlar in personuppgifter, se till att du följer sekretesslagar och -bestämmelser.** Med anpassade variabler kan du samla in praktiskt taget allt som du har åtkomst till, men du måste också ta hänsyn till din organisations sekretesspolicy och tillämpliga lagar.
* **Ge era kunder lättsökbar och lättförståelig sekretessinformation för organisationen.** Användbar information omfattar avanmälningslänkar, hur deras surfdata används och hur du använder eller planerar att använda Adobe-tjänster.
* **Var medveten om både lokal lagstiftning och internationell lagstiftning som gäller dig.** Om er organisation verkar globalt kan vissa internationella lagar gälla.

## Uppdelning av datainsamling

Adobe erbjuder flera datainsamlingsbibliotek som kan hjälpa till att skicka data till Adobe. Exempel:

* **AppMeasurement**: Ett bibliotek som utformats för att skicka data direkt till Adobe Analytics.
* **Web SDK**: Ett bibliotek som utformats för att skicka data till Adobe Experience Platform Edge-nätverket, som sedan vidarebefordrar dessa data till Adobe Analytics.
* **Taggar**: Ett webbaserat användargränssnitt som gör att du kan konfigurera implementeringen utan att behöva ha tillgång till källkoden för en webbplats eller app utöver den inledande tagghanteringen. Det finns tillägg för både AppMeasurement och Web SDK.

Adobe Analytics kan samla in följande typer av data:

| Typ av data | Information | Exempelvariabler som innehåller dessa data |
| --- | --- | --- |
| Sidnamn eller URL-adresser för webbsidor på din webbplats | Dessa data krävs för att Adobe Analytics ska fungera. En URL eller ett sidnamn krävs för varje träff. | [Sida](../components/dimensions/page.md), [Sidans URL](../components/dimensions/page-url.md) |
| Tidsbaserade data | Dessa data krävs för att Adobe Analytics ska fungera. En tidsstämpel krävs för datainsamling, och tidsbaserade data hämtas från tidsstämpeln. | [Tid som använts på sidan](../components/dimensions/time-spent-on-page.md), [Timme på dagen](../components/dimensions/hour-of-day.md), [AM/PM](../components/dimensions/am-pm.md), [Veckodag/vecka](../components/dimensions/weekday-weekend.md), [Veckodag](../components/dimensions/day-of-week.md), [Månad på året](../components/dimensions/month-of-year.md) |
| Referensdata | Datainsamlingsbiblioteken samlar som standard in den refererande URL:en när en besökare kommer till din webbplats. Du kan anpassa implementeringen för att samla in data inom en hänvisares frågesträng. Det här är vanligt för kampanjer och för att spåra annonsresultat. | [Referent](../components/dimensions/referrer.md), [Refererande domän](../components/dimensions/referring-domain.md) |
| Anonymiserade besökar-ID:n | Datainsamlingsbiblioteken genererar och refererar till ett besökar-ID för varje webbläsare som besöker webbplatsen. Detta ID lagras i en cookie. Om ett datainsamlingsbibliotek inte kan ange en cookie-identifierare använder biblioteket en reservmetod för anonym besökaridentifiering. Den här metoden innebär att koppla relaterade träffar till samma besök med besökarens IP-adress och användaragentsträng. Om din organisation har aktiverat IP-förfalskning respekteras den här inställningen. Se [Adobe Analytics och webbläsarcookies](cookies/cookies.md) för mer information. | [Unika besökare](../components/metrics/unique-visitors.md) |
| Identifierbara besökar-ID | Adobe samlar inte automatiskt in anpassade besökar-ID:n. Du kan dock anpassa implementeringen för att samla in dessa data. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| Extern sökterm | Externa sökdata innehåller nyckelord som kommer från sökmotorer. Datainsamlingsbibliotek söker efter dessa data baserat på den refererande URL:en. Många moderna sökmotorer innehåller dock inte längre den här informationen. | [Söknyckelord](../components/dimensions/search-keyword.md) |
| Interna söktermer | Interna sökdata innehåller nyckelord som kommer från webbplatsen eller appens sökfunktioner. Adobe samlar inte automatiskt in interna sökdata. Du kan dock anpassa implementeringen för att samla in dessa data. Detta är vanligt för organisationer som använder Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Specifikationer för dator och webbläsare | Datainsamlingsbiblioteken samlar automatiskt in webbläsartips med låg entropi, som webbläsartyp, operativsystemtyp och om enheten är stationär eller mobil. Anpassad konfiguration krävs för att samla in tips för hög entropi, till exempel webbläsarens specifika version/build, enhetsmodellen eller operativsystemets version. Se [Översikt över klienttips](client-hints.md) för mer information. | [Webbläsare](../components/dimensions/browser.md), [Operativsystem](../components/dimensions/operating-systems.md), [Mobila dimensioner](../components/dimensions/mobile-dimensions.md), [Bildskärmsupplösning](../components/dimensions/monitor-resolution.md) |
| Geoplatsinformation | Adobe kan förhindra detaljerad geopositionering genom att ange den sista oktetten i en IP-adress till 0. Detta gör geoinformationen mindre exakt och kan anges i [rapportsvitsinställningar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/general-acct-settings-admin.html). | [Städer](../components/dimensions/cities.md), [Regioner](../components/dimensions/regions.md), [Länder](../components/dimensions/countries.md) |
| IP-adress | Adobe kan dölja (hash) eller helt ta bort besökarens IP-adress när dessa data lagras. EMEA-kunder har vanligtvis som standard dolda IP-adressinställningar. Oberoende av hur obehindrad inställningen är IP-adressen inte tillgänglig som en dimension i Analysis Workspace, utan inkluderas bara i [Dataflöden](../export/analytics-data-feed/data-feed-overview.md). Se [Allmänna kontoinställningar](../admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) i administrationshandboken för mer information om tillgängliga försvårande inställningar. | Ingen |
| Formulärinformation finns på din webbplats | Alla implementeringstyper kräver konfiguration för att samla in dessa data. Du kan inkludera dessa data i anpassade variabler. | [eVar](../components/dimensions/evar.md) |
| Markerade annonser eller länkar på din webbplats | Insamlat om [`trackExternalLinks`](../implement/vars/config-vars/trackexternallinks.md) eller [`trackDownloadLinks`](../implement/vars/config-vars/trackdownloadlinks.md) är aktiverat. Ytterligare information, till exempel platsen där du klickar, är tillgänglig när du aktiverar Activity Map. | [Activity Map](../analyze/activity-map/activity-map.md), [Avsluta länk](../components/dimensions/exit-link.md), [Hämta länk](../components/dimensions/download-link.md) |
| Produkter som köpts på er webbplats | Alla implementeringstyper kräver konfiguration för att samla in dessa data. Adobe har flera standardvariabler för att samla in den här informationen. | [Produkt](../components/dimensions/product.md), [Beställningar](../components/metrics/orders.md), [Intäkter](../components/metrics/revenue.md) |

{style="table-layout:auto"}

Se navigeringsmenyn under [Översikt över Dimensioner](../components/dimensions/overview.md) och [Översikt över mått](../components/metrics/overview.md) för fler variabler som Adobe kan samla in data under.

## Platser för databehandling

Adobe har tre databehandlingsplatser för Adobe Analytics. Dessa webbplatser tar emot rådata och bearbetar dem i en rapportsserie som är optimerad för datalagring och rapporthämtning. Dessa databehandlingsplatser finns för närvarande i USA (Oregon), Storbritannien (London) och Singapore. Se [Adobe Analytics - säkerhetsöversikt](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank} för mer information.
