---
description: Aktivera användarbehörigheter för API-åtkomst, Report Suite-hantering, verktyg och rapporter samt instrumentpanelsobjekt.
keywords: grupper;behörigheter
subtopic: Users and groups
title: Anpassa behörigheter för verktyg i rapportsviten
feature: Administratörsverktyg
uuid: 3c95d296-ffd0-4971-9c5f-110ddbe042ce
exl-id: 8b776055-66a5-4ada-8d92-391c50a1d4f1
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 9%

---

# Anpassa behörigheter för verktyg i rapportsviten

>[!IMPORTANT]
>
>Användar- och produkthanteringen övergår till [Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html). Adobe meddelar dig när det är dags att migrera användare. När alla kunder har migrerat kommer hjälpinnehåll för **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** att tas bort.

Aktivera användarbehörigheter för API-åtkomst, Report Suite-hantering, verktyg och rapporter samt instrumentpanelsobjekt.

**[!UICONTROL User Management]** >  **[!UICONTROL Groups]** >  **[!UICONTROL Report Access]** >  **[!UICONTROL Report Suite Tools]** >  **[!UICONTROL Customize]**

Sidan [!UICONTROL Customize Report Suite Tools] ger medlemmar i en grupp åtkomst till följande objekt.

![](assets/report-suite-tools.png)

## Fältbeskrivningar

Inställningarna på den här sidan gäller för de rapportsviter som har valts på sidan [!UICONTROL Define User Groups].

| Element | Beskrivning |
|--- |--- |
| **Webbtjänster** |  |
| Med de här inställningarna kan användare anropa metoden Data warehouse och hämta inställningar för rapportsviten. |  |
| Data Warehouse | Används av en icke-admin-användare för att ringa anrop med Data warehouse-metoder via Web Services API. Se [Data warehouse - Utvecklardokumentation](/help/export/data-warehouse/data-warehouse.md) |
| Rapportsviter (läs) | Tillåter en icke-admin-användare att använda rapportsvitens metoder i API:t. |
| Rapportsviter (skriv) | Tillåter en icke-admin-användare att använda rapportsvitens metoder i API:t. |
| **Report Suite-hantering** |  |
| Dessa inställningar ger åtkomst till menyalternativen i Admin > Rapportsviter > Redigera inställningar ([Report Suite Manager](/help/admin/c-manage-report-suites/report-suites-admin.md)). |  |
| [Trafikhantering](/help/admin/c-traffic-management/traffic-management.md) | Ger tillstånd till trafikledning. |
| [Report Suite-hantering](/help/admin/c-manage-report-suites/report-suites-admin.md) | Ger behörighet att hantera rapportsviter. |
| [Kontosammanfattning](/help/admin/admin/general-acct-settings-admin.md) | Ger behörighet att redigera kontoinställningar för en rapportserie. |
| [URL-filter](/help/admin/admin/internal-url-filter-admin.md) | Ger behörighet till interna URL-filter i rapportsviter. Interna URL-filter används för att avgöra vilka referenser, eller refererande sidor, som är interna för din webbplats. |
| [Anpassad kalender](/help/admin/admin/custom-calendar.md) | Ger behörighet att redigera anpassad kalender. |
| [Betalsökning](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) | Betalsökningsidentifiering skiljer betald från naturlig sökning i rapporten Sökmotorer och Söknyckelord. |
| [Menyanpassning](/help/admin/admin/customize-menus.md) | Anpassa rapportmenyerna som en användare ser i Rapporter och analyser. |
| [Rapportkonfiguration i realtid](/help/admin/admin/realtime/t-realtime-admin.md) | Behörighet att konfigurera realtidsrapporter, Analytics. |
| [Videoinställningar](/help/admin/admin/video-management.md) | Behörighet att ange en uppsättning anpassade konverteringsvariabler (eVars) och anpassade händelser som ska användas för att spåra och rapportera video. |
| [Videoklassificeringar](https://docs.adobe.com/content/help/sv-SE/media-analytics/using/media-overview.html) | Behörighet att ange en uppsättning anpassade konverteringsvariabler (eVars) och anpassade händelser som ska användas för att spåra och rapportera video. |
| [Trafikvariabler](/help/admin/admin/c-traffic-variables/traffic-var.md) | Behörighet att korrelera anpassade data med specifika trafikrelaterade händelser. |
| [Trafikklassificeringar](/help/admin/admin/c-traffic-variables/traffic-classifications.md) | Konsoliderad i klassificeringar (under Verktyg och rapporter). |
| [Kanaler](/help/components/c-marketing-channels/analyze-mc.md) | Ger behörighet till inställningar för marknadsföringskanal i Report Suite Manager > Redigera inställningar > Marknadskanaler. |
| [Kostnader](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/analyze-mc.html) | Aktiverar tillstånd till marknadsföringskanaler > Marketing Channel-kostnader i Report Suite Manager. |
| [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) | Custom Insight Conversion Variable (eller eVar) placeras i Adobe-koden på vissa webbsidor på din webbplats. Dess främsta syfte är att segmentera framgångsstatistik för konverteringar i anpassade marknadsföringsrapporter. |
| [Sökmetoder](/help/admin/admin/finding-methods.md) | Här kan du identifiera hur olika sökmetoder rapporterar om konverteringsframgångar på din webbplats. |
| [Konverteringsklassificeringar](/help/admin/admin/conversion-var-admin/conversion-classifications.md) | Konsoliderad i klassificeringar (under Verktyg och rapporter). |
| [Unik besökare](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/unique-visitor-variable/t-unique-visitor-variable.html) | Ger behörighet att ange variabeln Unik besökare. |
| [Success Events](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) | Åtgärder som kan spåras, t.ex. produktvy, utcheckning och inköp. |
| [Klassificeringshierarkier](/help/admin/admin/conversion-var-admin/classification-hierarchies.md) | Konsoliderad i klassificeringar (under Verktyg och rapporter). |
| [Listvariabler](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/page-variables.html) | Kallas även List Var. På samma sätt som funktionen List Props tillåter List Vars flera värden inom samma bildbegäran. |
| [Standardmått](/help/admin/admin/default-metrics.md) | Rapporter och analyser visar en standarduppsättning med mätvärden i alla konverteringsrapporter, såvida inte en användare väljer en anpassad uppsättning mätvärden. De valda mätvärdena visas för alla användare i den associerade rapportsviten. |
| [Bearbetningsregler](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) | Ger åtkomst till bearbetningsregler som förenklar datainsamling och hantering av innehåll när det skickas till rapporter. |
| **Verktyg och rapporter** |  |
| [Avvikelseidentifiering](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) | Ger tillstånd till avvikelseidentifiering, som tillhandahåller en statistisk metod för att fastställa hur ett givet mätresultat har ändrats i förhållande till tidigare data. |
| [Kanalrapport](/help/components/c-marketing-channels/analyze-mc.md) | Ger tillstånd till Marketing Channel-rapporter, som finns i Rapporter > Marketing Channel Reports. |
| [Realtidsrapport](/help/admin/admin/realtime/t-realtime-admin.md) | Ger åtkomst till realtidsrapporten. |
| [Punktsidor](/help/admin/admin/bot-removal/bot-rules.md) | **Obs! Startsidor är för specifika rapporter- och analysrapporter, inte för hantering av robotregler. För närvarande finns det ingen behörighet att tillåta redigering av båda reglerna.** Med Bot Rules kan du ta bort trafik som genereras av kända spindlar och botar från rapportsviten. Genom att ta bort robottrafiken kan du få ett mer exakt mått på användaraktiviteten på din webbplats. |
| [Robotar](/help/admin/admin/bot-removal/bot-rules.md) | **Obs! Bots är till för specifika rapporter- och analysrapporter, inte för hantering av robotregler. För närvarande finns det ingen behörighet att tillåta redigering av båda reglerna.** Med Bots kan du ta bort trafik som genereras av kända spindlar och botar från rapportsviten. Genom att ta bort robottrafiken kan du få ett mer exakt mått på användaraktiviteten på din webbplats. |
| [Anpassad Data warehouse-rapport](/help/export/data-warehouse/data-warehouse.md) | Data warehouse avser kopian av obearbetade data för lagring och anpassade rapporter, som du kan köra genom att filtrera data. Du kan begära rapporter för att visa avancerade datarelationer från rådata baserat på dina unika frågor. |
| Dagliga återbesök | (Äldre) Rapport som visar antalet besökare på webbplatsen mer än en gång på en viss dag. En dag definieras som den sista 24-timmarsperioden. |
| [Data Sources Manager](/help/admin/admin/data-sources.md) | Med funktionen Datakällor kan du importera data till Analytics från offlinekällor. |
| [Exkludera efter IP-adress](/help/admin/admin/exclude-ip.md) | Du kan undanta data från specifika IP-adresser, som interna webbplatsaktiviteter, platstestning och personalanvändning, från dina rapporter. |
| Äldre ClickMap | Ger åtkomst till menyn för det gamla övertäckningsverktyget för ClickMap. |
| Installation av äldre klickkarta | Ger installationsbehörighet till det äldre verktyget för ClickMap. |
| Återbesök | En rapport som visar antalet besök där besöksnumret är större än 1. Rapporten om återkommande besök innehåller besökare som inte är cookies. |
| [Klassificeringsimporteraren](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-importer/c-working-with-saint.html) /exporteraren och  [regelbyggaren](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-rulebuilder/classification-rule-builder.html) | Konsoliderad i klassificeringar (se nedan). |
| Hanteraren för dataflöden | Ger rättigheter till Analytics Data Feed. |
| Klassificeringar | Kombinerar följande behörigheter: Trafikklassificeringar, Videoklassificeringar, Konverteringsklassificeringar, Klassificeringshierarkier, Klassificeringshanterare och Klassificeringsimporterare/Exporterare och Regelbyggare.  Obs!  Med den här behörigheten kan användarna redigera klassificeringar för alla rapportsviter, inte bara för de markerade. |
| [Bidragsanalys](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) | Ger rätt att använda bidragsanalys i Analysis Workspace. |
| **Kontrollpanelsobjekt** |  |
| Inställningarna i Kontrollpanelsobjekt ger åtkomst till [rapporter](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/server-call-usage-dashboard.html) i Rapporter och analys:, Mina rekommenderade rapporter, Sammanfattningsrapport för företag, Bild, KPI/mätarrapport, Rapportsvitsummor, Text, Rapport, Användningssammanfattningsrapport och Webbresurser |  |
| **Övriga** |  |
| Social | Styr åtkomsten till menyn Social Management i Report Suite Manager. |
