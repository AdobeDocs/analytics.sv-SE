---
description: Lär dig mer om riktlinjerna och rekommendationerna för användares samtycke till att lagra eller läsa cookies som inte är nödvändiga på enheter eller webbläsare.
title: Vilka är CNIL-riktlinjerna för användarens samtycke och cookies?
feature: Data Governance
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 0%

---

# Undantag för CNIL-samtycke

Den 1 oktober 2020 offentliggjorde den franska dataskyddsmyndigheten (nedan kallad CNIL) en reviderad version av sina riktlinjer för cookies (nedan kallade riktlinjerna) och sina slutliga rekommendationer om hur användare ska få tillstånd att lagra eller läsa icke-nödvändiga cookies och liknande tekniker på användarens enheter eller webbläsare (nedan kallad Recommendations).

Riktlinjerna ger ett begränsat undantag från kravet på samtycke (&quot;medgivande&quot;). Godkännandeundantaget gäller cookies som endast har till syfte att mäta målgruppen för webbplatsen eller appen för webbutgivarens räkning. Riktlinjerna föreskriver att följande villkor måste vara uppfyllda för att medgivandeundantaget ska gälla:

* 25 månaders datalagring max.  Du kan granska dina aktuella inställningar för datalagring under Analytics > Admin > Data Governance.  [Datalagring](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* Inaktivera cookies från tredje part i ECID. [disableThirdPartyCall](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=en#id-service-api), [disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=en#id-service-api)och [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=en#id-service-api)
* 13-månaders cookie-gräns.  Du kan åsidosätta förfallodatumet för din analyscookie med `cookieLifetime` variabel. Experience Cloud cookies, inklusive Analytics och ECID, förlänger utgångsdatumet för cookie vid varje besök.  Om du vill ange en statisk, icke-rullande cookie-förfallotid kan du antingen: (1) skriv egen kod för att ange ett datum då cookien ska tas bort, eller (2) använd din CMP för att styra datumet för cookie-återställningen.   [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html) och [Experience Cloud Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=en#ec-cookies)
* Begränsat omfång. Cookie-filen måste begränsas till en enda plats eller tillämpning. [Webbläsarcookies](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=en&quot;\l&quot;cookie-implementations från tredje part)
* Anonymisering. Anonymisera IP-adressens sista oktett. [Allmänna kontoinställningar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* Dölj besökar-ID från rapportering.  Besökar-ID:n visas inte som standard i Adobe Workspace och Adobe Reports and Analytics.  Besökar-ID:n är tillgängliga i Dataflöden och Data warehouse.  Åtkomsten till datafeeds och Data warehouse kan begränsas av [Åtkomstbehörigheter i Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en&quot;\l&quot;task_040673FE3E429B9531FBCB8B6A4391) och [Kolumnreferens för datafeed](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en#columns%2C-descriptions%2C-and-data-types)
* Parametrar för geopositionering. Geolokalisering kan inte vara mer exakt än postnummernivå. [Postalternativ](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en&quot;\l&quot;zip-in-adobe-experience-platform-launch) och [Allmänna kontoinställningar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=en&quot;\l&quot;admin-tools)
* Ange alternativ för deltagande.  Med anmälningstjänsten kan du ange besökarprotokoll för att avgöra om du kan ange en cookie på användarens enhet eller webbläsare när du besöker webbplatsen. [Anmälningstjänst](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* Förhindra datadelning.  För att förhindra datadelning till Adobe Audience Manager använder du `opt.dmp` kontextvariabel för [Sekretessrapportering](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=en&quot;\l&quot;variabler) för att förhindra att träffar delas.
* Åtkomst och radering. Utnyttja Privacy Servicen för begäran om åtkomst och borttagning. [Analyser och Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## Ytterligare överväganden för datainsamling

Följande ytterligare överväganden gäller:

* Överväg att samla in anmälningsstatusen i en Analytics-variabel för att separera indata från indata som avvalts för segmentering, virtuella rapportsviter eller för att dirigera till separata slutpunkter.
* Ingen mätning utanför webbplatsen eller appen utan förhandsgodkännande, till exempel inga kampanjer utanför webbplatsen, e-postkampanjer eller iFrames.
* Insamling av personuppgifter i variabler är inte tillåtet utan samtycke. [Åtgärder för kontroll av Experience Cloud baserat på användares samtycke](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html?lang=en%22%20\l%20%22implementation#implementation)
* Uppgifterna får endast användas för att producera anonym statistik, utan kombination med andra uppgifter.
* Data används inte för korsreferensåtgärder.
* GPS-geopositioneringsdata samlas inte in.
* När slutanvändarens samtycke har lämnats kan ovanstående inställningar ändras och begränsningarna förenklas.

Mer information finns i [CNIL Cookie-undantag](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications) webbplats.
