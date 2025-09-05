---
description: Översikt över vilka data Adobe Analytics samlar in och andra sekretessvillkor.
keywords: sekretess
title: Sekretessöversikt
feature: Data Governance
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 1%

---

# Sekretessöversikt

Adobe vill att ni ska kunna aktivera er organisation så att ni kan följa gällande lagar och bestämmelser. Mer information finns i [Adobe Experience Cloud sekretess](https://www.adobe.com/privacy/experience-cloud.html){target=_blank}. Mellan Adobe Analytics och din organisation fungerar Adobe som&quot;personuppgiftsbiträde&quot; och du är&quot;personuppgiftsansvarig&quot; (eller motsvarande enligt gällande sekretess- och dataskyddslagstiftning). Det är upp till er organisation att redovisa hur ni använder Adobe produkter och tjänster, eftersom ni exklusivt styr hur ni ska implementera Adobe lösningar. När du använder Adobe Analytics ansvarar din organisation för att följa din egen integritetspolicy, ditt serviceavtal med Adobe och alla tillämpliga lagar.

Adobe rekommenderar starkt att du följer följande övergripande koncept:

* **Om du samlar in personuppgifter måste du kontrollera att du följer sekretesslagar och -regler.** Med anpassade variabler kan du samla in praktiskt taget allt som du har åtkomst till, men du måste också ta hänsyn till din organisations sekretesspolicy och tillämpliga lagar.
* **Ge dina kunder lättåtkomlig och lättförståelig sekretessinformation för organisationen.** Användbar information omfattar avanmälningslänkar, hur deras webbläsardata används och hur du använder eller planerar att använda Adobe tjänster.
* **Var medveten om både lokal och internationell lagstiftning som gäller dig.** Om din organisation arbetar globalt kan vissa internationella lagar gälla.

## Uppdelning av datainsamling

Adobe erbjuder flera datainsamlingsbibliotek som kan hjälpa till att skicka data till Adobe. Exempel:

* **AppMeasurement**: Ett bibliotek utformat för att skicka data direkt till Adobe Analytics.
* **Web SDK**: Ett bibliotek som är utformat för att skicka data till Adobe Experience Platform Edge-nätverket, som sedan vidarebefordrar dessa data till Adobe Analytics.
* **Taggar**: Ett webbaserat användargränssnitt som gör att du kan konfigurera implementeringen utan att det krävs åtkomst till en webbplats eller ett programs källkod utöver den inledande tagghanteringen. Det finns tillägg för både AppMeasurement och Web SDK.

Adobe Analytics kan samla in följande typer av data:

| Typ av data | Information | Exempelvariabler som innehåller dessa data |
| --- | --- | --- |
| Sidnamn eller URL-adresser för webbsidor på din webbplats | Dessa data krävs för att Adobe Analytics ska fungera. En URL eller ett sidnamn krävs för varje träff. | [Sida](/help/components/dimensions/page.md), [Sidadress](/help/components/dimensions/page-url.md) |
| Tidsbaserade data | Dessa data krävs för att Adobe Analytics ska fungera. En tidsstämpel krävs för datainsamling, och tidsbaserade data hämtas från tidsstämpeln. | [Tid som har använts på sidan](/help/components/dimensions/time-spent-on-page.md), [Timme på dagen](/help/components/dimensions/hour-of-day.md), [AM/PM](/help/components/dimensions/am-pm.md), [Veckodag/Veckoslut](/help/components/dimensions/weekday-weekend.md), [Veckodag](/help/components/dimensions/day-of-week.md), [Månad på året](/help/components/dimensions/month-of-year.md) |
| Referensdata | Datainsamlingsbiblioteken samlar som standard in den refererande URL:en när en besökare kommer till din webbplats. Du kan anpassa implementeringen för att samla in data inom en hänvisares frågesträng. Det här är vanligt för kampanjer och för att spåra annonsresultat. | [Referent](/help/components/dimensions/referrer.md), [Refererande domän](/help/components/dimensions/referring-domain.md) |
| Anonymiserade besökar-ID:n | Datainsamlingsbiblioteken genererar och refererar till ett besökar-ID för varje webbläsare som besöker webbplatsen. Detta ID lagras i en cookie. Om ett datainsamlingsbibliotek inte kan ange en cookie-identifierare använder biblioteket en reservmetod för anonym besökaridentifiering. Den här metoden innebär att koppla relaterade träffar till samma besök med besökarens IP-adress och användaragentsträng. Om din organisation har aktiverat IP-förfalskning respekteras den här inställningen. Mer information finns i [Adobe Analytics- och webbläsarcookies](../cookies/cookies.md). | [Unika besökare](/help/components/metrics/unique-visitors.md) |
| Identifierbara besökar-ID | Adobe samlar inte automatiskt in anpassade besökar-ID. Du kan dock anpassa implementeringen för att samla in dessa data. | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) |
| Extern sökterm | Externa sökdata innehåller nyckelord som kommer från sökmotorer. Datainsamlingsbibliotek söker efter dessa data baserat på den refererande URL:en. Många moderna sökmotorer innehåller dock inte längre den här informationen. | [Söknyckelord](/help/components/dimensions/search-keyword.md) |
| Interna söktermer | Interna sökdata innehåller nyckelord som kommer från webbplatsen eller appens sökfunktioner. Adobe samlar inte automatiskt in interna sökdata. Du kan dock anpassa implementeringen för att samla in dessa data. Detta är vanligt för organisationer som använder Adobe Analytics. | [eVar](/help/components/dimensions/evar.md) |
| Specifikationer för dator och webbläsare | Datainsamlingsbiblioteken samlar automatiskt in webbläsartips med låg entropi, som webbläsartyp, operativsystemtyp och om enheten är stationär eller mobil. Anpassad konfiguration krävs för att samla in tips för hög entropi, till exempel webbläsarens specifika version/build, enhetsmodellen eller operativsystemets version. Mer information finns i [Översikt över klienttips](../client-hints.md). | [Webbläsare](/help/components/dimensions/browser.md), [Operativsystem](/help/components/dimensions/operating-systems.md), [Mobila dimensioner](/help/components/dimensions/mobile-dimensions.md), [Skärmupplösning](/help/components/dimensions/monitor-resolution.md) |
| Geoplatsinformation | Adobe erbjuder möjlighet att förhindra detaljerad geolokalisering genom att ange den sista oktetten i en IP-adress till 0. Detta gör geoinformationen mindre exakt och kan anges i [rapportsvitsinställningarna](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md). | [Städer](/help/components/dimensions/cities.md), [Regioner](/help/components/dimensions/regions.md), [Länder](/help/components/dimensions/countries.md) |
| IP-adress | Adobe erbjuder möjlighet att dölja (hash) eller helt ta bort besökarens IP-adress när dessa data lagras. EMEA-kunder har vanligtvis som standard dolda IP-adressinställningar. Oavsett vilken inställning du anger för obehörig åtkomst är IP-adressen inte tillgänglig som en dimension i Analysis Workspace. Den ingår bara i [Dataflöden](/help/export/analytics-data-feed/data-feed-overview.md). Se [Allmänna kontoinställningar](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) i administrationshandboken för mer information om tillgängliga felsökningsinställningar. | Ingen |
| Formulärinformation finns på din webbplats | Alla implementeringstyper kräver konfiguration för att samla in dessa data. Du kan inkludera dessa data i anpassade variabler. | [eVar](/help/components/dimensions/evar.md) |
| Markerade annonser eller länkar på din webbplats | Samlades in om [`trackExternalLinks`](/help/implement/vars/config-vars/trackexternallinks.md) eller [`trackDownloadLinks`](/help/implement/vars/config-vars/trackdownloadlinks.md) är aktiverat. Ytterligare information, till exempel platsen där du klickar, är tillgänglig när du aktiverar Activity Map. | [Activity Map](/help/analyze/activity-map/overview.md), [Avsluta länk](/help/components/dimensions/exit-link.md), [Hämta länk](/help/components/dimensions/download-link.md) |
| Produkter som köpts på er webbplats | Alla implementeringstyper kräver konfiguration för att samla in dessa data. Adobe erbjuder flera standardvariabler för att samla in den här informationen. | [Produkt](/help/components/dimensions/product.md), [Beställningar](/help/components/metrics/orders.md), [Intäkter](/help/components/metrics/revenue.md) |

{style="table-layout:auto"}

Se navigeringsmenyn under [Dimensionsöversikt](/help/components/dimensions/overview.md) och [Metrisk översikt](/help/components/metrics/overview.md) för fler variabler som Adobe kan samla in data under.

## Platser för databehandling

Adobe har tre databehandlingsplatser för Adobe Analytics. Dessa webbplatser tar emot rådata och bearbetar dem i en rapportsserie som är optimerad för datalagring och rapporthämtning. Dessa databehandlingsplatser finns för närvarande i USA (Oregon), Storbritannien (London) och Singapore. Mer information finns i [Adobe Analytics säkerhetsöversikt](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank}.
