---
description: Lär dig mer om riktlinjerna och rekommendationerna för användares samtycke till att lagra eller läsa cookies som inte är nödvändiga på enheter eller webbläsare.
title: Vilka är CNIL-riktlinjerna för användarens samtycke och cookies?
feature: Data Governance
role: Admin
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# Undantag för CNIL-medgivande

Den 1 oktober 2020 offentliggjorde den franska dataskyddsmyndigheten (nedan kallad CNIL) en reviderad version av sina riktlinjer för cookies (nedan kallade riktlinjerna) och sina slutliga rekommendationer om hur användare ska få tillstånd att lagra eller läsa icke-nödvändiga cookies och liknande tekniker på användarens enheter eller webbläsare (nedan kallad Recommendations).

Riktlinjerna ger ett begränsat undantag från kravet på samtycke (&quot;medgivande&quot;). Godkännandeundantaget gäller cookies som endast har till syfte att mäta målgruppen för webbplatsen eller appen för webbutgivarens räkning. Riktlinjerna föreskriver att följande villkor måste vara uppfyllda för att medgivandeundantaget ska gälla:

* 25 månaders datalagring max.  Du kan granska dina aktuella inställningar för datalagring under [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Data Governance].  [Datalagring](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* Inaktivera cookies från tredje part i ECID. [disableThirdPartyCall](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html#id-service-api), [disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html#id-service-api)och [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html#id-service-api)
* 13-månaders cookie-gräns.  Du kan åsidosätta förfallodatumet för din analyscookie med `cookieLifetime` variabel. Experience Cloud cookies, inklusive Analytics och ECID, förlänger utgångsdatumet för cookie vid varje besök.  Om du vill ange en statisk, icke-rullande cookie-förfallotid kan du antingen: (1) skriva anpassad kod för att ange ett datum då cookien ska tas bort, eller (2) använda din CMP för att styra datumet för cookie-återställningen.   [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html) och [Experience Cloud Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html#ec-cookies)
* Begränsad omfattning. Cookie-filen måste begränsas till en enda plats eller tillämpning. [Webbläsarcookies](https://experienceleague.adobe.com/docs/analytics/technotes/cookies/cookies.html#third-party-cookie-limitations)
* Anonymisering. Anonymisera IP-adressens sista oktett. [Allmänna kontoinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
* Dölj besökar-ID från rapportering.  Besökar-ID:n visas inte som standard i Adobe Workspace och Adobe Reports and Analytics.  Besökar-ID:n är tillgängliga i Datautflöden och Data Warehouse.  Åtkomsten till datafeeds och Data Warehouse kan begränsas av [Åtkomstbehörigheter i Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) och [Kolumnreferens för datafeed](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html#columns%2C-descriptions%2C-and-data-types)
* Parametrar för geopositionering. Geolokalisering kan inte vara mer exakt än postnummernivå. [Postalternativ](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en) och [Allmänna kontoinställningar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* Ange alternativ för deltagande.  Med anmälningstjänsten kan du ange besökarprotokoll för att avgöra om du kan ange en cookie på användarens enhet eller webbläsare när du besöker webbplatsen. [Anmälningstjänst](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* Förhindra datadelning.  Om du vill förhindra datadelning till Adobe Audience Manager använder du `opt.dmp` kontextvariabel för [Sekretessrapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) för att förhindra att träffar delas.
* Åtkomst och radering. Använd Privacy Servicen för att få åtkomst och ta bort begäranden. [Analyser och Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## Ytterligare överväganden för datainsamling

Följande ytterligare överväganden gäller:

* Adobe Analytics har datacentraler i USA, Storbritannien och Singapore för att ge alla kunder flexibilitet att samla in, bearbeta och lagra sina uppgifter regionalt. När man konfigurerar den första konfigurationen av Adobe Analytics kan man välja önskad plats för databehandlingscentret. Kundernas data lagras i den region där de har valts för huvudprodukten i Analytics.
* Överväg att samla in anmälningsstatusen i en Analytics-variabel för att separera indata från indata som avvalts för segmentering, virtuella rapportsviter eller för att dirigera till separata slutpunkter.
* Ingen mätning utanför webbplatsen eller appen utan förhandsgodkännande, till exempel inga kampanjer utanför webbplatsen, e-postkampanjer eller iFrames.
* Insamling av personuppgifter i variabler är inte tillåtet utan samtycke. [Åtgärder för kontroll av Experience Cloud baserat på användares samtycke](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html#implementing-opt-in-on-the-page)
* Uppgifterna får endast användas för att producera anonym statistik, utan kombination med andra uppgifter.
* Data används inte för korsreferensåtgärder.
* GPS-geopositioneringsdata samlas inte in.
* När slutanvändarens samtycke har lämnats kan ovanstående inställningar ändras och begränsningarna förenklas.

>[!IMPORTANT]
>
>Detta dokument är inte avsett som juridisk eller juridisk rådgivning och utgör inte någon garanti eller något avtalsåtagande från Adobe. Vi uppmuntrar kunderna att söka oberoende juridisk rådgivning om kundens rättsliga och lagstadgade skyldigheter i frågor som rör detta ämne.


Mer information finns i [CNIL Cookie-undantag](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications) webbplats.

