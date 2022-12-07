---
product: analytics
audience: admin
user-guide-title: Administratörshandbok för Analytics
breadcrumb-title: Administratörshandbok
user-guide-description: Lär dig mer om administrationsåtgärder i Analytics, som att hantera användare och produkter i Experience Cloud Admin Console, konfigurera rapportsviter med mera.
source-git-commit: b274cb4b51a1bdc54413a27f244a1522da903542
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 84%

---


# Adobe Analytics Admin Guide {#admin}

+ [Administratörshandbok för Analytics](home.md)
+ [Versionsinformation om Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
+ Kom igång med Analytics-administration {#admin-overview}
   + [Vilket Adobe Analytics-verktyg ska jag använda?](admin/get-started/which-analytics-tool.md)
   + [Produktjämförelse och krav för analyser](admin/get-started/analytics-product-comparison.md)
   + [Systemkrav](admin/get-started/sys-reqs.md)
   + Företagsinställningar {#company-settings}
      + [Översikt över företagsinställningar](admin/get-started/company/c-company-settings.md)
      + [Åtkomstnivåer](admin/get-started/company/feature-access-levels.md)
      + [Webbtjänster](admin/get-started/company/web-services-admin.md)
      + [Report Builder-rapporter](admin/get-started/company/report-builder-reports-admin.md)
      + [Enkel inloggning](admin/get-started/company/single-signon-admin.md)
      + [Väntande åtgärder](admin/get-started/company/pending-actions-admin.md)
      + [Samprofilering](admin/get-started/company/co-branding-admin.md)
      + [Dölj rapportsviter](admin/get-started/company/c-hide-report-suites.md)
      + [Säkerhetshanteraren](admin/get-started/company/security-manager.md)
+ Användarbehörigheter i Admin Console i Adobe {#admin-console}
   + [Analyser i Adobe Admin Console](admin-console/home.md)
   + Behörigheter {#permissions}
      + [Analysbehörigheter i Admin Console](admin-console/permissions/summary-tables.md)
      + [Produktprofiler för Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Produktprofilbehörigheter för Report Suite-verktyg](admin-console/permissions/report-suite-tools.md)
      + [Produktprofilbehörigheter för analysverktyg](admin-console/permissions/analytics-tools.md)
   + [Adobe Analytics första administrationshandbok](admin-console/first-admin-guide.md)
   + [Administratörsroller i Adobe Analytics](admin-console/admin-roles-in-analytics.md)
+ Administratörsverktyg {#admin-tools}
   + [Administratörsverktyg](admin/c-admin-tools.md)
   + [Fakturering](admin/billing-admin.md)
   + Borttagning av bot {#bot-removal}
      + [Borttagning av bot](admin/bot-removal/bot-removal.md)
      + [Översikt över botregler](admin/bot-removal/bot-rules.md)
      + [Vanliga robotsignaturer](admin/bot-removal/bot-signatures.md)
      + [Punktexkluderingsmetoder](admin/bot-removal/bot-exclusion-methods.md)
   + [Kodhanteraren](admin/code-manager-admin.md)
   + Konverteringsvariabler {#conversion-variables}
      + [Konverteringsvariabler (eVars)](admin/conversion-var-admin/conversion-var-admin.md)
      + [Redigera konverteringsvariabler](admin/conversion-var-admin/t-conversion-variables-admin.md)
      + [Konverteringsklassificeringar](admin/conversion-var-admin/conversion-classifications.md)
      + [Klassificeringshierarkier](admin/conversion-var-admin/classification-hierarchies.md)
      + [Listvariabler](admin/conversion-var-admin/list-var-admin.md)
      + [Marknadsförande eVars](admin/conversion-var-admin/merchandising-evars.md)
   + [Valutakoder](admin/currency.md)
   + [Anpassade rapportbeskrivningar](admin/custom-desc-admin.md)
   + [Anpassa kalender](admin/custom-calendar.md)
   + [Datakällor](admin/data-sources.md)
   + [Standardmått](admin/default-metrics.md)
   + [Exkludera efter IP-adress](admin/exclude-ip.md)
   + [Hitta metoder](admin/finding-methods.md)
   + [Allmänna kontoinställningar](admin/general-acct-settings-admin.md)
   + [Interna URL-filter](admin/internal-url-filter-admin.md)
   + [Loggar](admin/logs.md)
   + [Marknadsföringskanaler](admin/marketing-channels-admin.md)
   + [Anpassa menyer](admin/customize-menus.md)
   + [Måttsynlighet](admin/metric-visibility.md)
   + [Apphantering](admin/mobile-management.md)
   + Betald sökdetektering {#paid-search-detection}
      + [Översikt över betald sökdetektering](admin/paid-search-detection/paid-search-detection.md)
      + [Konfigurera betald sökdetektering](admin/paid-search-detection/t-paid-search-detection.md)
   + [Publiceringslistor](admin/publishing-list.md)
   + [Publiceringswidget](admin/publishing-widgets-admin.md)
   + [Inställningshanteraren](admin/preferences-manager.md)
   + [Sekretessinställningar](admin/privacy-settings.md)
   + [Sekretessrapportering](admin/privacy-reporting.md)
   + Behandlingsregler {#processing-rules}
      + [Översikt över behandlingsregler](admin/c-processing-rules/processing-rules.md)
      + Konfiguration av behandlingsregler {#processing-rules-configuration}
         + [Så fungerar behandlingsregler](admin/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
         + [Skapa behandlingsregler](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
         + [Visa aktiva behandlingsregler](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
         + [Visa historik för behandlingsregel](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
         + [Återställa behandlingsregler](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
         + [Kopiera behandlingsregler till en annan rapportsvit](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
      + [Tillgängliga dimensioner för behandlingsregler](admin/c-processing-rules/processing-rule-dimensions.md)
      + Exempel på behandlingsregler {#processing-rules-examples}
         + [Exempel på behandlingsregler](admin/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
         + [Fylla i ett kampanj-ID från en frågesträngsparameter](admin/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
         + [Ange produktvyhändelsen från sidan för produktöversikt](admin/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
         + [Lägg till en underkategori genom att sammanfoga kategorin och sidnamnet](admin/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
         + [Bestäm en sökväg genom att kopiera ett eVar-värde till ett projekt](admin/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
         + [Rensa värden i en rapport](admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
         + [Fylla i interna söktermer med en frågesträngsparameter](admin/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
         + [Kopiera en kontextdatavariabel till en eVar](admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
         + [Ange en händelse med hjälp av en kontextdatavariabel](admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
         + [Ta bort en händelse från en träff](admin/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
      + [Tips och tricks för regler](admin/c-processing-rules/processing-rules-tips.md)
   + Realtidsrapporter {#real-time-reports}
      + [Översikt över realtidsrapporter](admin/realtime/realtime.md)
      + [Konfiguration av rapporter i realtid](admin/realtime/t-realtime-admin.md)
      + [Mätvärden och dimensioner som stöds i realtid](admin/realtime/realtime-metrics.md)
   + [Rapporteringsaktivitetshanteraren](admin/reporting-activity.md)
   + [Schemalagd rapportkö](admin/scheduled-reports-admin.md)
   + Vidarebefordran på serversidan {#server-side-forwarding}
      + [Översikt över vidarebefordran på serversidan](admin/c-server-side-forwarding/ssf.md)
      + [GDPR/ePrivacy-efterlevnad och vidarebefordran på serversidan](admin/c-server-side-forwarding/ssf-gdpr.md)
      + [Krav för vidarebefordran på serversidan](admin/c-server-side-forwarding/ssf-requirements.md)
      + [Vidarebefordra data och kodreferenser på serversidan](admin/c-server-side-forwarding/ssf-reference.md)
      + [Så här verifierar du implementeringen av vidarebefordring på serversidan](admin/c-server-side-forwarding/ssf-verify.md)
      + [Vanliga frågor om vidarebefordran på serversidan](admin/c-server-side-forwarding/ssf-faq.md)
   + [Enklare rapportmeny](admin/t-simplified-menu.md)
   + [Social hantering](admin/social-management.md)
   + Slutförda händelser {#success-events}
      + [Översikt över slutförda händelser](admin/c-success-events/success-event.md)
      + [Konfigurera slutförda händelser](admin/c-success-events/t-success-events.md)
      + [Om att ändra händelsetypen](admin/c-success-events/event-type.md)
   + [Tidsstämplar (valfritt)](admin/timestamp-optional.md)
   + Trafikvariabler {#traffic-variables}
      + [Översikt över trafikvariabeln (prop)](admin/c-traffic-variables/traffic-var.md)
      + [Aktivera rapporter för trafikvariabel](admin/c-traffic-variables/t-traffic-variable.md)
      + [Trafikklassificeringar](admin/c-traffic-variables/traffic-classifications.md)
   + Unik besökarvariabel {#unique-visitor-variable}
      + [Ange variabeln Unik besökare](admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
      + [Användningsfall – extrahera besökar-ID:n](admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
   + [Videohantering](admin/video-management.md)
+ Hantera rapportsviter {#manage-report-suites}
   + [Hanterare för rapportsvit](c-manage-report-suites/report-suites-admin.md)
   + [Sammanslagning och globala rapportsviter](c-manage-report-suites/rollup-report-suite.md)
   + [Skapa en sammanslagen rapportsvit](c-manage-report-suites/t-rollups.md)
   + Rapportsvitmallar {#report-suite-templates}
      + [Översikt över rapportsvitmallar](c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
      + [Aggregatorportal](c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
      + [Handel](c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
      + [Innehåll och media](c-manage-report-suites/c-report-suite-templates/content-media.md)
      + [Standardmall](c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
      + [Finansiella tjänster](c-manage-report-suites/c-report-suite-templates/financial-services.md)
      + [Jobbportal](c-manage-report-suites/c-report-suite-templates/job-portal.md)
      + [Generering av leads](c-manage-report-suites/c-report-suite-templates/lead-generation.md)
      + [Supportmedia](c-manage-report-suites/c-report-suite-templates/support-media.md)
   + [Spara en sökning i en rapportsvit](c-manage-report-suites/t-report-suite-saved-search.md)
   + [Inställningar för enskild rapportsvit](c-manage-report-suites/individual-rs-settings.md)
   + [Hämta inställningar för rapportsviten](c-manage-report-suites/t-download-rs-settings.md)
   + Ny rapportsvit {#new-report-suite}
      + [Skapa en rapportsvit](c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
      + [Ny rapportsvit – inställningar](c-manage-report-suites/c-new-report-suite/new-report-suite.md)
      + [Inställningar som inte kopierats från en källrapportssvit](c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
   + [Skapa en rapportsvitgrupp](c-manage-report-suites/t-create-rs-group.md)
+ Användar- och produkthantering (äldre) {#user-product-management}
   + [Hantering av användare och produkter](user-management2/user-management.md)
   + Use: Migrera användare till Adobe Admin Console {#migrate-users}
      + [Migrering av Analytics-användare till Admin Console](user-management2/user-migration/c-migration-tool.md)
      + [Migrera Analytics-användarkonton för Adobe ID:n](user-management2/user-migration/t-migrate-users.md)
      + [Migrera Analytics-användarkonton för Enterprise och Federated ID](user-management2/user-migration/migrate-enterprise.md)
      + [Inaktivera äldre inloggningar](user-management2/user-migration/t-disable-legacy-login.md)
      + [API:er som påverkas av migreringen](user-management2/user-migration/developer.md)
+ Datastyrning {#data-governance}
   + [Adobe Analytics och GDPR](c-data-governance/an-gdpr-overview.md)
   + [Adobe Analytics och CCPA](c-data-governance/an-ccpa-overview.md)
   + [Undantag för CNIL-samtycke](c-data-governance/cnil-consent-exemption.md)
   + [Frågor och svar](c-data-governance/gdpr-faq.md)
   + [Arbetsflöde för datasekretess i Adobe Analytics](c-data-governance/an-gdpr-workflow.md)
   + [Visa/hantera rapportsvitens inställningar för datastyrning](c-data-governance/gdpr-view-settings.md)
   + [Data i etikettrapportsvit](c-data-governance/gdpr-setup-reportsuite.md)
   + [Skicka begäran om åtkomst och borttagning](c-data-governance/gdpr-submit-access-delete.md)
   + [Datasekretessetiketter för analysvariabler](c-data-governance/gdpr-labels.md)
   + [Namnutrymmen](c-data-governance/gdpr-namespaces.md)
   + [ID-expansion](c-data-governance/gdpr-id-expansion.md)
   + [Bästa praxis för etikettering](c-data-governance/gdpr-analytics-ids.md)
   + [Exempel på etiketter](c-data-governance/gdpr-labeling-example.md)
   + [Datasekretess och Data Connectors (Genesis)](c-data-governance/data-connectors-gdpr.md)
   + [Terminologi för datasekretess](c-data-governance/gdpr-terminology.md)
+ Användning av serversamtal {#server-call-usage}
   + [Översikt över användningen av serversamtal](c-server-call-usage/overage-overview.md)
   + [Visa aktuell användning av serversamtal](c-server-call-usage/server-call-usage-dashboard.md)
   + [Visa användning av rapportsvit](c-server-call-usage/report-suite-usage.md)
   + [Användningsvarningar för serversamtal](c-server-call-usage/scu-alerts.md)
   + [Vanliga frågor om användning av serversamtal](c-server-call-usage/overage-faq.md)
+ Trafikhantering {#traffic-management}
   + [Hantera trafik](c-traffic-management/traffic-management.md)
   + [Schemalägg en trafiktopp](c-traffic-management/t-traffic-schedule-spike.md)
   + [Uppskatta tidigare serveranrop och schemalägg en trafiktopp](c-traffic-management/traffic-spike-estimate-past-server-calls.md)
   + [Ange permanent trafikökning](c-traffic-management/t-traffic-permanent.md)
   + [Ledtid som krävs för trafikökningar](c-traffic-management/traffic-lead-time.md)
+ [Admin-API](c-admin-api/c-admin-api.md)
