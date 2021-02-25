---
description: Lär dig mer om riktlinjerna och rekommendationerna för användares samtycke till att lagra eller läsa cookies som inte är nödvändiga på enheter eller webbläsare.
title: Vilka är CNIL-riktlinjerna för användarens samtycke och cookies?
translation-type: tm+mt
source-git-commit: c5ebc92622e012699d64c27701b24a88429e9f4f
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 0%

---


# Undantag för CNIL-samtycke

Den 1 oktober 2020 offentliggjorde den franska dataskyddsmyndigheten (nedan kallad CNIL) en reviderad version av sina riktlinjer för cookies (nedan kallade riktlinjerna) och sina slutliga rekommendationer om hur användare ska få tillstånd att lagra eller läsa icke-nödvändiga cookies och liknande tekniker på användarens enheter eller webbläsare (nedan kallad Recommendations).

Riktlinjerna ger ett begränsat undantag från kravet på samtycke (&quot;medgivande&quot;). Godkännandeundantaget gäller cookies som endast har till syfte att mäta målgruppen för webbplatsen eller appen för webbutgivarens räkning. Riktlinjerna föreskriver att följande villkor måste vara uppfyllda för att medgivandeundantaget ska gälla:

* 25 månaders datalagring max.  Du kan granska dina aktuella inställningar för datalagring under Analytics > Admin > Data Governance.  [Datalagring](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* 13-månaders cookie-gräns.  Du kan åsidosätta förfallodatumet för din analyscookie med variabeln `cookieLifetime`.  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html)
* Begränsat omfång. Cookie-filen måste begränsas till en enda plats eller tillämpning. [Webbläsarcookies](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=en&quot;\l&quot;cookie-implementations från tredje part)
* Anonymisering. Anonymisera IP-adressens sista oktett. [Allmänna kontoinställningar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* Dölj besökar-ID från rapportering.  Besökar-ID:n visas inte som standard i Adobe Workspace och Adobe Reports and Analytics.  Besökar-ID:n är tillgängliga i Dataflöden och Data warehouse.  Åtkomsten till datafeeds och Data warehouse kan begränsas av [Åtkomstbehörigheter i Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en&quot;\l&quot;task_040673FE3E429B9531FBCB8B6A4391)
* Parametrar för geopositionering. Geolokalisering kan inte vara mer exakt än postnummernivå. [Postalternativ ](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en&quot;\l&quot;zip-in-adobe-experience-platform-launch) och  [allmänna kontoinställningar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=en&quot;\l&quot;admin-tools)
* Ange alternativ för deltagande.  Med anmälningstjänsten kan du ange besökarprotokoll för att avgöra om du kan ange en cookie på användarens enhet eller webbläsare när du besöker webbplatsen. [Anmälningstjänst](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* Förhindra datadelning.  Om du vill utesluta datadelning till Adobe Audience Manager använder du kontextvariabeln `opt.dmp` för [Sekretessrapportering](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=en&quot;\l&quot;variabler) för att förhindra att träffar delas.
* Åtkomst och radering. Använd Privacy Servicen för att få åtkomst och ta bort begäranden. [Analyser och Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## Ytterligare överväganden för datainsamling

Följande ytterligare överväganden gäller:

* Ingen mätning utanför webbplatsen eller appen utan förhandsgodkännande, till exempel inga kampanjer utanför webbplatsen, e-postkampanjer eller iFrames.
* Insamling av personuppgifter i variabler är inte tillåtet utan samtycke.
* Uppgifterna får endast användas för att producera anonym statistik, utan kombination med andra uppgifter.
* Data används inte för korsreferensåtgärder.
* GPS-geopositioneringsdata samlas inte in.

Mer information finns på webbplatsen [CNIL Cookie Exction](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).
