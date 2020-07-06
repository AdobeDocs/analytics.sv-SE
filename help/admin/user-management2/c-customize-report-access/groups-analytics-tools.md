---
description: Aktivera användarbehörigheter för allmänna objekt (fakturering, loggar osv.), företagshantering, verktyg, Web Service Access, Report Builder och integrering med Data Connectors.
keywords: groups;permissions
subtopic: Users and groups
title: Anpassa behörigheter för Analytics-verktyg
topic: Admin tools
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 10%

---


# Anpassa behörigheter för Analytics-verktyg

>[!IMPORTANT]
>
>Hanteringen av användare och produkter har flyttats till [Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html). Adobe meddelar dig när det är dags att migrera användare. När alla kunder har migrerat tas hjälpinnehåll för **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** bort.

Aktivera användarbehörigheter för allmänna objekt (fakturering, loggar osv.), företagshantering, verktyg, Web Service Access, Report Builder och integrering med Data Connectors.

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL All Report Access]** > **[!UICONTROL Analytics Tools]** > **[!UICONTROL Customize]**

>[!NOTE]
>
>Versionen från hösten 2016 (20 oktober) förändrade grupphanteringen. Se [Administrativa ändringar - hösten 2016](/help/admin/user-management2/c-user-management/permissions-changes.md) för en sammanfattning av ändringarna.

## Rapportåtkomst - Analytics-verktyg

![](assets/report-access-analytics-tools.png)

Klicka **[!UICONTROL Customize]** för att markera objekt som den här gruppen ska ha åtkomst till.

## Fältbeskrivningar

Inställningarna på den här sidan gäller för de rapportsviter som är markerade på [!UICONTROL Define User Groups] sidan.

| Element | Beskrivning |
|--- |--- |
| **Allmänt** |  |
| [Kodhanteraren](/help/admin/admin/code-manager-admin.md) | Ger behörighet att hämta datainsamlingskod för webb- och mobilplattformar. |
| Kodhanteraren - webbtjänster | Tillåter en icke-administrativ användare att komma åt kodhanteraren via webbtjänster. |
| [Loggar](/help/admin/admin/logs.md) | Aktiverar behörighet att logga filer, som hjälper dig att se när användare loggar in, hur de använder dem, hur de får åtkomst, hur rapporteringsprogram och vilka administratörsändringar de har. |
| Loggar - webbtjänster | Tillåter en icke-administrativ användare att komma åt administratörsverktygsloggar via webbtjänster. |
| [Trafikhantering](/help/admin/c-traffic-management/traffic-management.md) | På sidan Traffic Management kan du ange förväntade ändringar av trafikvolymen. |
| Behörighetshantering | Ger icke-administratörsanvändare åtkomst till sidorna för användarhantering i Admin Tools. Dessa användare har läsbehörighet men inte skrivbehörighet. |
| Behörigheter (skrivbehörighet) - webbtjänster | Ger icke-administrativa användare läs- och skrivbehörighetsinställningar under Användarhantering i webbtjänster.<br>Den här inställningen hänvisar specifikt till de angivna behörighetsåtgärderna i Admin API. |
| Behörigheter (läs) - webbtjänster | Tillåter en icke-administrativ användare att visa behörighetsinställningar under Användarhantering i webbtjänster.<br>Den här inställningen hänvisar specifikt till de angivna behörighetsåtgärderna i Admin API. |
| **Företagshantering** |  |
| [Säkerhet](/help/admin/company/security-manager.md) | Ger behörighet till Security Manager-sidan för att styra åtkomst till rapportdata. Du kan välja starka lösenord, lösenord, IP-inloggningsbegränsningar och e-postdomänbegränsningar. |
| Supportinformation | Ger behörighet till supportinformationen i företagsinställningarna. |
| [Webbtjänster](/help/admin/company/web-services-admin.md) | Tillåter åtkomst till webbtjänstsidan i Admin Tools-gränssnittet ([!UICONTROL Company Settings] > [!UICONTROL Web Services]).<br>API:t för webbtjänster ger programmatisk åtkomst till Adobe Analytics-tjänster som gör att du kan duplicera och förstärka funktioner som är tillgängliga via användargränssnittet. |
| Enkel inloggning (äldre) | Ger åtkomst till sidan för enkel inloggning i Admin Tools.<br>**Obs!**Enkel inloggning i Adobe Experience Cloud implementeras med[kontolänkning](https://docs.adobe.com/content/help/sv-SE/core-services/interface/manage-users-and-products/organizations.html)mellan Experience Cloud och lösningar. |
| [Väntande åtgärder](/help/admin/company/pending-actions-admin.md) | Ger behörighet att hantera väntande åtgärder i [!UICONTROL Company Settings]. |
| [Samprofilering](/help/admin/company/co-branding-admin.md) | Ger tillstånd att sammärka Analytics. |
| [Inställningar](/help/admin/admin/preferences-manager.md) | Ger tillstånd till [!UICONTROL Preference Manager]användaren. |
| [Dölj rapportsviter](/help/admin/company/c-hide-report-suites.md) | Ger behörighet att dölja rapportsviter i användargränssnittet för Adobe Analytics. |
| **verktyg** | Dessa inställningar ger åtkomst till Analytics-verktyg (gränssnitt och program) och avancerade funktioner som segmentering och beräknade värden. |
| [Aktuella data](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html) | Ger behörighet att använda funktionen Aktuella data vid rapportering. |
| [Ad Hoc Analysis](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) licensanvändare | Ger behörighet att komma åt [!UICONTROL Ad Hoc Analysis]. |
| Webbtjänståtkomst | Ger åtkomst till webbtjänster för icke-administratörer. Skapar autentiseringsuppgifter för webbtjänsten. |
| [Report Builder](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html) | Ger medlemmar i den här gruppen tillgång till [!UICONTROL Report Builder] licenser. |
| [Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html) Access | Ger användare åtkomst till Analysis Workspace, det rekommenderade rapporteringsgränssnittet för [!DNL Adobe Analytics]. |
| [Rapporter och Analytics](https://docs.adobe.com/content/help/en/analytics/landing/an-key-concepts.html) | Ger användare åtkomst till Rapporter och Analytics. |
| [Skapande av beräknade mätvärden](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) | Ger användare behörighet att skapa beräknade värden. |
| [Skapa segment](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) | Ger användare behörighet att skapa segment. |
| **Data Connectors** |  |
| Integreringar (Skapa, Uppdatera eller Ta bort) | Ger behörighet att skapa, uppdatera och ta bort Data Connector-integreringar. |
