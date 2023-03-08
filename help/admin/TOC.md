---
product: analytics
audience: admin
user-guide-title: Administratörshandbok för Analytics
breadcrumb-title: Användarhandbok om Admin
user-guide-description: Lär dig mer om administrationsåtgärder i Analytics, som att hantera användare och produkter i Experience Cloud Admin Console, konfigurera rapportsviter med mera.
source-git-commit: 87d4e492afe8d614dfdba24389660829df871dd7
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 73%

---


# Adobe Analytics Admin Guide {#admin}

+ [Administratörshandbok för Analytics](home.md)
+ [Versionsinformation om Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
+ Admin Console för Adobe {#admin-console}
   + [Översikt](admin-console/home.md)
   + [Adobe Analytics första administrationshandbok](admin-console/first-admin-guide.md)
   + [Administratörsroller i Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Sammanfattning av behörigheter för analysverktyg {#permissions}
      + [Analysbehörigheter i Admin Console](admin-console/permissions/summary-tables.md)
      + [Produktprofiler för Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Produktprofilbehörigheter för Report Suite-verktyg](admin-console/permissions/report-suite-tools.md)
      + [Produktprofilbehörigheter för analysverktyg](admin-console/permissions/analytics-tools.md)
+ Administratörsverktyg för analyser {#admin-tools}
   + [Översikt över administrationsverktyg](admin/c-admin-tools.md)
   + [Kodhanteraren](admin/code-manager-admin.md)
   + [Datakällor](admin/data-sources.md)
   + [Exkludera efter IP-adress](admin/exclude-ip.md)
   + [Loggar](admin/logs.md)
   + [Rapporteringsaktivitetshanteraren](admin/reporting-activity.md)
   + Report Suite-hanterare {#manage-report-suites}
      + Redigera inställningar för en rapportserie {#edit-report-suite}
         + Allmänt {#report-suite-general}
            + [Allmänna kontoinställningar](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [Interna URL-filter](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + [Anpassa kalender](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + Betalsökningsidentifiering {#paid-search-detection}
               + [Översikt över betald sökdetektering](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [Konfigurera betald sökdetektering](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + [Anpassa menyer](admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md)
            + Bearbetningsregler {#c-processing-rules}
               + [Översikt över behandlingsregler](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)
               + Bearbetningsregler {#c-processing-rules-configuration}
                  + [Så fungerar behandlingsregler](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
                  + [Skapa behandlingsregler](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
                  + [Visa aktiva behandlingsregler](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
                  + [Visa historik för behandlingsregel](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
                  + [Återställa behandlingsregler](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
                  + [Kopiera behandlingsregler till en annan rapportsvit](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
                  + [Tillgängliga dimensioner för behandlingsregler](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rule-dimensions.md)
               + Exempel på behandlingsregler {#processing-rules-examples}
                  + [Exempel på behandlingsregler](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
                  + [Fylla i ett kampanj-ID från en frågesträngsparameter](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
                  + [Ange produktvyhändelsen från sidan för produktöversikt](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
                  + [Lägg till en underkategori genom att sammanfoga kategorin och sidnamnet](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
                  + [Bestäm en sökväg genom att kopiera ett eVar-värde till ett projekt](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
                  + [Rensa värden i en rapport](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
                  + [Fylla i interna söktermer med en frågesträngsparameter](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
                  + [Kopiera en kontextdatavariabel till en eVar](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
                  + [Ange en händelse med hjälp av en kontextdatavariabel](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
                  + [Ta bort en händelse från en träff](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
               + [Tips och tricks för regler](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-tips.md)
            + Punktregler {#bot-removal}
               + [Borttagning av bot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [Översikt över botregler](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [Vanliga robotsignaturer](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [Punktexkluderingsmetoder](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [Sekretessinställningar](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [Konfiguration av tidsstämplar](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + Vidarebefordran på serversidan {#server-side-forwarding}
               + [Översikt över vidarebefordran på serversidan](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [GDPR/ePrivacy-efterlevnad och vidarebefordran på serversidan](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Krav för vidarebefordran på serversidan](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [Vidarebefordra data och kodreferenser på serversidan](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [Så här verifierar du implementeringen av vidarebefordring på serversidan](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [Vanliga frågor om vidarebefordran på serversidan](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + Trafik {#traffic-variables}
            + [Trafikvariabler](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [Aktivera rapporter för trafikvariabel](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/t-traffic-variable.md)
            + [Trafikklassificeringar](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [Anpassade rapportbeskrivningar](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + Konvertering {#conversion-variables}
            + [Konverteringsvariabler](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [Sökmetoder](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + [Konverteringsklassificeringar](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + Unik besöksvariabel {#unique-visitor-variable}
               + [Ange variabeln Unik besökare](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Användningsfall – extrahera besökar-ID:n](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + Success Events {#success-events}
               + [Översikt över slutförda händelser](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
               + [Konfigurera slutförda händelser](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/t-success-events.md)
               + [Om att ändra händelsetypen](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md)
            + [Klassificeringshierarkier](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [Listvariabler](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [Marknadsförande eVars](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
         + Marknadsföringskanaler {#marketing-channels}
            + [Marknadsföringskanalhanterare](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
            + [Bearbetningsregler för marknadsföringskanal](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
            + [Klassificeringar av marknadsföringskanaler](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
            + [Utgångsdatum för marknadsföringskanal](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
         + Trafikhantering {#traffic-management}
            + [Översikt](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [Schemalägg spike](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [Permanent trafik](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [Standardmått](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
         + [Apphantering](admin/c-manage-report-suites/c-edit-report-suites/mobile-management.md)
         + [Mediehantering](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
         + [Activity Map](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
         + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
         + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
         + [Sekretessrapportering](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
         + hantering av Document Cloud {#doc-cloud-mgt}
            + [Konfigurera Document Cloud med Adobe Analytics](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-mgt.md)
            + [Konfigurera rapportering för Document Cloud](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-config.md)
         + [Konfiguration av Advertising Analytics](admin/c-manage-report-suites/c-edit-report-suites/advertising-analytics-config.md)
         + Realtid {#real-time-reports}
            + [Översikt över realtidsrapporter](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [Konfiguration av rapporter i realtid](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [Mätvärden och dimensioner som stöds i realtid](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
      + [Hantera rapportsviter](admin/c-manage-report-suites/report-suites-admin.md)
      + [Sammanslagning och globala rapportsviter](admin/c-manage-report-suites/rollup-report-suite.md)
      + [Spara en sökning i en rapportsvit](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [Hämta inställningar för rapportsviten](admin/c-manage-report-suites/t-download-rs-settings.md)
      + Ny rapportsvit {#c-new-report-suite}
         + [Skapa en rapportsvit](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [Skapa en sammanslagen rapportsvit](admin/c-manage-report-suites/c-new-report-suite/t-rollups.md)
         + [Skapa en rapportsvitgrupp](admin/c-manage-report-suites/c-new-report-suite/t-create-rs-group.md)
         + [Ny rapportsvit – inställningar](admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
         + [Inställningar som inte kopierats från en källrapportssvit](admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
      + Rapportsvitmallar {#report-suite-templates}
         + [Översikt över rapportsvitmallar](admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
         + [Aggregatorportal](admin/c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
         + [Handel](admin/c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
         + [Innehåll och media](admin/c-manage-report-suites/c-report-suite-templates/content-media.md)
         + [Standardmall](admin/c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
         + [Finansiella tjänster](admin/c-manage-report-suites/c-report-suite-templates/financial-services.md)
         + [Jobbportal](admin/c-manage-report-suites/c-report-suite-templates/job-portal.md)
         + [Generering av leads](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
         + [Supportmedia](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
   + Företagsinställningar {#company-settings}
      + [Översikt över företagsinställningar](admin/company/c-company-settings.md)
      + [Säkerhetshanteraren](admin/company/security-manager.md)
      + [Webbtjänster](admin/company/web-services-admin.md)
      + [Report Builder-rapporter](admin/company/report-builder-reports-admin.md)
      + [Enkel inloggning](admin/company/single-signon-admin.md)
      + [Samprofilering](admin/company/co-branding-admin.md)
      + [Dölj rapportsviter](admin/company/c-hide-report-suites.md)
      + [Inställningshanteraren](admin/company/preferences-manager.md)
      + [Väntande åtgärder](admin/company/pending-actions-admin.md)
      + [Åtkomstnivåer](admin/company/feature-access-levels.md)
   + Etikettering av integritetsskydd för datahantering {#data-governance}
      + [Arbetsflöde för datasekretess i Adobe Analytics](admin/c-data-governance/an-gdpr-workflow.md)
      + [Frågor och svar](admin/c-data-governance/gdpr-faq.md)
      + Dataetiketter {#data-labels}
         + [Dataintegritetsetiketter för analyskomponenter](admin/c-data-governance/data-labeling/gdpr-labels.md)
         + [Data i etikettrapportsvit](admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
         + [Visa/hantera integritetsetiketter för rapportsviten](admin/c-data-governance/data-labeling/gdpr-view-settings.md)
         + [Bästa praxis för etikettering](admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)
         + [Exempel på etiketter](admin/c-data-governance/data-labeling/gdpr-labeling-example.md)
         + [Namnutrymmen](admin/c-data-governance/data-labeling/gdpr-namespaces.md)
      + [ID-expansion](admin/c-data-governance/gdpr-id-expansion.md)
      + [Undantag för CNIL-samtycke](admin/c-data-governance/cnil-consent-exemption.md)
   + Användning av serversamtal {#server-call-usage}
      + [Översikt över användningen av serversamtal](admin/c-server-call-usage/overage-overview.md)
      + [Visa aktuell användning av serversamtal](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [Visa användning av rapportsvit](admin/c-server-call-usage/report-suite-usage.md)
      + [Användningsvarningar för serversamtal](admin/c-server-call-usage/scu-alerts.md)
      + [Vanliga frågor om användning av serversamtal](admin/c-server-call-usage/overage-faq.md)
   + Användar- och produkthantering (äldre) {#user-product-management}
      + [Användar- och produkthantering (äldre)](admin/user-management2/user-management.md)
      + Use: Migrera användare till Adobe Admin Console {#migrate-users}
         + [Migrering av Analytics-användare till Admin Console](admin/user-management2/user-migration/c-migration-tool.md)
         + [Migrera Analytics-användarkonton för Adobe ID:n](admin/user-management2/user-migration/t-migrate-users.md)
         + [Migrera Analytics-användarkonton för Enterprise och Federated ID](admin/user-management2/user-migration/migrate-enterprise.md)
         + [Inaktivera äldre inloggningar](admin/user-management2/user-migration/t-disable-legacy-login.md)
         + [API:er som påverkas av migreringen](admin/user-management2/user-migration/developer.md)
+ [Admin-API](c-admin-api/c-admin-api.md)

