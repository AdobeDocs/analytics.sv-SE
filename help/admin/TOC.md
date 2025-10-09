---
product: analytics
audience: admin
user-guide-title: Administratörshandbok för Analytics
breadcrumb-title: Användarhandbok om Admin
user-guide-description: Lär dig mer om administrationsåtgärder i Analytics, som att hantera användare och produkter i Experience Cloud Admin Console, konfigurera rapportsviter med mera.
source-git-commit: 77795002cc4a360ed8aad8e1fe4882f1fe16f6ae
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 11%

---


# Adobe Analytics Admin Guide {#admin}

+ [Administratörshandbok för analyser](home.md)
+ [Versionsinformation för analyser](https://experienceleague.adobe.com/en/docs/analytics/release-notes/latest)
+ Adobe Admin Console {#admin-console}
   + [Översikt](admin-console/home.md)
   + [Adobe Analytics första administrationshandbok](admin-console/first-admin-guide.md)
   + [Administratörsroller i Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Sammanfattning av behörigheter för analysverktyg {#permissions}
      + [Produktprofiler för Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Produktprofilbehörigheter för Report Suite-verktyg](admin-console/permissions/report-suite-tools.md)
      + [Produktprofilbehörigheter för analysverktyg](admin-console/permissions/analytics-tools.md)
+ Administratörsverktyg för analyser {#admin-tools}
   + [Översikt över administrationsverktyg](tools/c-admin-tools.md)
   + [Kodhanteraren](tools/code-manager-admin.md)
   + [Analysinventering](tools/analytics-inventory.md)
   + [Datakällor](tools/data-sources.md)
   + [Exkludera efter IP-adress](tools/exclude-ip.md)
   + [Loggar](tools/logs.md)
   + Rapporteringsaktivitetshanteraren {#reporting-activity-manager}
      + [Översikt](tools/reporting-activity-manager/reporting-activity-overview.md)
      + [Visa rapporteringsaktivitet](tools//reporting-activity-manager/reporting-activity.md)
      + [Avbryt rapporteringsbegäranden](tools/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + Komponentmigrering {#component-migration}
      + [Förbered för migrering](tools/component-migration/prepare-component-migration.md)
      + [Arbetsflöde för migrering](tools/component-migration/component-migration.md)
   + Report Suite-hanterare {#manage-report-suites}
      + Redigera inställningar för en rapportserie {#edit-report-suite}
         + Allmänt {#report-suite-general}
            + [Allmänna kontoinställningar](tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
            + [Interna URL-filter](tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)
            + [Anpassa kalender](tools/manage-rs/edit-settings/general/custom-calendar.md)
            + Betalsökningsidentifiering {#paid-search-detection}
               + [Översikt över betald sökningsidentifiering](tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)
               + [Konfigurera identifiering av betald sökning](tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)
            + Bearbetningsregler {#processing-rules}
               + [Översikt](tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
               + [Gränssnitt](tools/manage-rs/edit-settings/general/processing-rules/pr-interface.md)
               + [Visa historik](tools/manage-rs/edit-settings/general/processing-rules/pr-view-history.md)
               + [Kopiera regler](tools/manage-rs/edit-settings/general/processing-rules/pr-copy.md)
               + [Tillgängliga mått och mätvärden](tools/manage-rs/edit-settings/general/processing-rules/pr-variables.md)
               + [Användningsexempel](tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)
            + Punktregler {#bot-removal}
               + [Borttagning av punkt](tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md)
               + [Förstå och konfigurera robotregler](tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)
               + [Vanliga robotsignaturer](tools/manage-rs/edit-settings/general/bot-removal/bot-signatures.md)
               + [Punktexkluderingsmetoder](tools/manage-rs/edit-settings/general/bot-removal/bot-exclusion-methods.md)
            + [Sekretessinställningar](tools/manage-rs/edit-settings/general/privacy-settings.md)
            + [Konfiguration av tidsstämplar](tools/manage-rs/edit-settings/general/timestamp-configuration.md)
            + Vidarebefordran på serversidan {#server-side-forwarding}
               + [Översikt över vidarebefordran på serversidan](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
               + [GDPR/ePrivacy compliance och vidarebefordran på serversidan](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Krav för vidarebefordran på serversidan](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-requirements.md)
               + [Vidarebefordra data och kodreferenser på serversidan](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-reference.md)
               + [Så här verifierar du implementeringen av vidarebefordring på serversidan](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)
               + [Vanliga frågor om vidarebefordran på serversidan](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)
         + Trafik {#traffic-variables}
            + [Trafikvariabler](tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
            + [Trafikklassificeringar](tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md)
            + [Anpassade rapportbeskrivningar](tools/manage-rs/edit-settings/c-traffic-variables/custom-desc-admin.md)
         + Konvertering {#conversion-variables}
            + [Konverteringsvariabler](tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)
            + [Sökmetoder](tools/manage-rs/edit-settings/conversion-var-admin/finding-methods.md)
            + [Konverteringsklassificeringar](tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)
            + Unik besöksvariabel {#unique-visitor-variable}
               + [Ange variabeln Unik besökare](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Användningsfall - extrahera besökar-ID:n](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [Slutförda händelser](tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)
            + [Klassificeringshierarkier](tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)
            + [Listvariabler](tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)
            + [Marknadsförande eVars](tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md)
         + Marknadsföringskanaler {#marketing-channels}
            + [Marknadsföringskanalhanterare](tools/manage-rs/edit-settings/marketing-channels/c-channels.md)
            + [Bearbetningsregler för marknadsföringskanal](tools/manage-rs/edit-settings/marketing-channels/c-rules.md)
            + [Klassificeringar av marknadsföringskanaler](tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md)
            + [Utgångsdatum för marknadsföringskanal](tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md)
         + Trafikhantering {#traffic-management}
            + [Översikt](tools/manage-rs/edit-settings/c-traffic-management/traffic-management.md)
            + [Schemalägg spike](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md)
            + [Permanent trafik](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-permanent.md)
         + [Standardmått](tools/manage-rs/edit-settings/default-metrics.md)
         + Apphantering {#app-management}
            + [Apprapportering](tools/manage-rs/edit-settings/app-reporting.md)
            + [Appklassificeringar](tools/manage-rs/edit-settings/app-classifications.md)
         + [Mediehantering](tools/manage-rs/edit-settings/media-management.md)
         + [Activity Map](tools/manage-rs/edit-settings/activity-map.md)
         + [AEM](tools/manage-rs/edit-settings/adobe-experience-manager.md)
         + [Adobe Campaign](tools/manage-rs/edit-settings/adobe-campaign.md)
         + [Sekretessrapportering](tools/manage-rs/edit-settings/privacy-reporting.md)
         + Document Cloud Management {#doc-cloud-mgt}
            + [Konfigurera Document Cloud med Adobe Analytics](tools/manage-rs/edit-settings/document-cloud-mgt.md)
            + [Konfigurera Document Cloud-rapportering](tools/manage-rs/edit-settings/document-cloud-config.md)
         + [Konfiguration av Advertising Analytics](tools/manage-rs/edit-settings/advertising-analytics-config.md)
         + Realtid {#real-time-reports}
            + [Översikt över realtidsrapporter](tools/manage-rs/edit-settings/realtime/realtime.md)
            + [Konfiguration av rapporter i realtid](tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)
            + [Mätvärden och dimensioner som stöds i realtid](tools/manage-rs/edit-settings/realtime/realtime-metrics.md)
      + [Hantera rapportsviter](tools/manage-rs/report-suites-admin.md)
      + [Globala rapportsviter](tools/manage-rs/rollup-report-suite.md)
      + [Spara en sökning i en rapportserie](tools/manage-rs/t-report-suite-saved-search.md)
      + [Hämta inställningar för rapportsviten](tools/manage-rs/t-download-rs-settings.md)
      + Ny rapportsvit {#c-new-report-suite}
         + [Skapa en rapportsvit](tools/manage-rs/new-rs/t-create-a-report-suite.md)
         + [Skapa en rapportsvitgrupp](tools/manage-rs/new-rs/t-create-rs-group.md)
         + [Ny rapportsvit - inställningar](tools/manage-rs/new-rs/new-report-suite.md)
         + [Inställningar som inte kopierats från en källrapportsserie](tools/manage-rs/new-rs/settings-not-copied-from-rs.md)
      + Rapportsvitmallar {#report-suite-templates}
         + [Översikt över rapportsvitmallar](tools/manage-rs/rs-templates/report-suite-templates.md)
         + [Aggregator-portal](tools/manage-rs/rs-templates/aggregator-portal.md)
         + [Commerce](tools/manage-rs/rs-templates/commerce-admin.md)
         + [Innehåll och media](tools/manage-rs/rs-templates/content-media.md)
         + [Standardmall](tools/manage-rs/rs-templates/default-rs-template.md)
         + [Finansiella tjänster](tools/manage-rs/rs-templates/financial-services.md)
         + [Jobbportal](tools/manage-rs/rs-templates/job-portal.md)
         + [Generering av leads](tools/manage-rs/rs-templates/lead-generation.md)
         + [Supportmedia](tools/manage-rs/rs-templates/support-media.md)
   + Företagsinställningar {#company-settings}
      + [Översikt över företagsinställningar](tools/company/c-company-settings.md)
      + [Säkerhetshanteraren](tools/company/security-manager.md)
      + [Webbtjänster](tools/company/web-services-admin.md)
      + [Report Builder-rapporter](tools/company/report-builder-reports-admin.md)
      + [Enkel inloggning](tools/company/single-signon-admin.md)
      + [Dölj rapportsviter](tools/company/c-hide-report-suites.md)
      + [Inställningshanteraren](tools/company/preferences-manager.md)
      + [Väntande åtgärder](tools/company/pending-actions-admin.md)
      + [Åtkomstnivåer](tools/company/feature-access-levels.md)
   + Sekretessetiketter {#privacy-labeling}
      + [Översikt](tools/privacy-labeling/labeling-overview.md)
      + [Dataintegritetsetiketter för analyskomponenter](tools/privacy-labeling/labels.md)
      + [Visa/hantera integritetsetiketter för rapportsviten](tools/privacy-labeling/view-settings.md)
      + [Bästa praxis för etikettering](tools/privacy-labeling/best-practices.md)
      + [Exempel på etiketter](tools/privacy-labeling/examples.md)
      + [Namnutrymmen](tools/privacy-labeling/namespaces.md)
   + Användning av serversamtal {#server-call-usage}
      + [Översikt över användningen av serversamtal](tools/server-call-usage/overage-overview.md)
      + [Visa aktuell användning av serversamtal](tools/server-call-usage/server-call-usage-dashboard.md)
      + [Visa rapportsvitanvändning](tools/server-call-usage/report-suite-usage.md)
      + [Användningsvarningar för serversamtal](tools/server-call-usage/scu-alerts.md)
      + [Vanliga frågor om användning av serversamtal](tools/server-call-usage/overage-faq.md)
   + Användar- och produkthantering (äldre) {#user-product-management}
      + [Användar- och produkthantering (äldre)](tools/user-management/user-management.md)
      + [Hantera äldre användarkonton, resurser och förfallodatum](tools/user-management/users-assets.md)
      + Migrera användare till Adobe Admin Console {#migrate-users}
         + [Migrering av Analytics-användare till Admin Console](tools/user-management/user-migration/c-migration-tool.md)
         + [Migrera användarkonton för Analytics för Adobe ID:n](tools/user-management/user-migration/t-migrate-users.md)
         + [Migrera Analytics-användarkonton för Enterprise ID och Federated ID](tools/user-management/user-migration/migrate-enterprise.md)
         + [Inaktivera äldre inloggningar](tools/user-management/user-migration/t-disable-legacy-login.md)
         + [API:er som påverkas av migreringen](tools/user-management/user-migration/developer.md)
+ [Admin-API](https://developer.adobe.com/analytics-apis/docs/2.0/)
