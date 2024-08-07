---
title: Adobe Analytics Permissions - summary tables
description: Tabeller som sammanfattar tillgängliga Adobe Analytics-behörigheter i Adobe Admin Console.
exl-id: f1abbdb7-0f76-4d9b-a3ca-b12fa3cecb50
feature: Admin Tools
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 2%

---

# Analysbehörigheter i Admin Console

<!--This page is no longer in the TOC. It's a duplication of info and contradicts some of the info in the Report Suite Tools and Analytics Tools topics. -->
Använd följande sammanfattningstabeller för att identifiera Adobe Analytics-behörigheter i Adobe Admin Console, efter logiska grupperingar.

## Report Suite-verktyg

| Report Suite-verktyg | Administrering | Åtkomstkontroller | Funktioner endast för rapporter | Föråldrat | Beskrivning |
| --- | --- | --- | --- | --- | --- |
| Kontosammanfattning | x |  |  |  | Ger åtkomst till Allmänt > Allmänna kontoinställningar i Report Suite Manager. |
| Kanaler | x |  |  |  | Ger åtkomst till marknadsföringskanaler, inklusive Marketing Channel Manager, regler för bearbetning av marknadsföringskanaler och förfallodatum för marknadsföringskanaler i Report Suite Manager. |
| Klassificeringar | x |  |  |  | Ger åtkomst till alla klassificeringsinställningar i Report Suite Manager. Detta behörighetsobjekt innehåller: |
| Konverteringsvariabler | x |  |  |  | Ger åtkomst till Conversion > Conversion Variables i Report Suite Manager. |
| Kostnader | x |  |  |  | Ger åtkomst till marknadsföringskanaler > Marknadskanalkostnader i Report Suite Manager. |
| Anpassad kalender | x |  |  |  | Ger åtkomst till Allmänt > Anpassa kalender i Report Suite Manager. |
| Hanteraren för dataflöden | x |  |  |  | Ger åtkomst till Admin > Dataflöden i den övre navigeringen i Analytics. |
| API för datareparation | x |  |  |  | Ger åtkomst till API:t för datareparation |
| Datakällhanteraren | x |  |  |  | Ger åtkomst till Admin > Alla administratörer > Datakällor i den övre navigeringen i Analytics. Kräver behörighetsobjektet &#39;Report Suite Mgmt&#39;. |
| Standardmått | x |  |  |  | Ger åtkomst till Inställningar > Standardvärden i Report Suite Manager för enskilda rapportsviter. |
| Exkludera efter IP-adress | x |  |  |  | Ger åtkomst till Admin > Exkludera med IP i den övre navigeringen i Analytics. |
| Sökmetoder | x |  |  |  | Ger åtkomst till Conversion > Finding Methods i Report Suite Manager. |
| Listvariabler | x |  |  |  | Ger åtkomst till Conversion > List Variables i Report Suite Manager. |
| Menyanpassning | x |  |  |  | Ger åtkomst till Allmänt > Anpassa menyer i Report Suite Manager. |
| Betalsökning | x |  |  |  | Ger åtkomst till Allmänt > Identifiering av betald sökning i Report Suite Manager. |
| Bearbetningsregler | x |  |  |  | Ger åtkomst till Allmänt > Bearbetningsregler och Allmänt > Punktregler i Report Suite Manager. |
| Konfiguration av realtidsrapport | x |  |  |  | Ger åtkomst till realtid i Report Suite Manager. Använd behörighetsobjektet &#39;RealTime Report&#39; för att ge åtkomst till själva rapporten. |
| Rapportera Suite-hantering | x |  |  |  | Ger åtkomst till Report Suite Manager, men tillåter inga ändringar. |
| Success Events | x |  |  |  | Ger åtkomst till Conversion > Success Events i Report Suite Manager. |
| Trafikvariabler | x |  |  |  | Ger åtkomst till Traffic > Traffic Variables i Report Suite Manager. |
| Unik besökare | x |  |  |  | Ger åtkomst till Conversion > Unique Visitor Variable. Används vanligtvis inte i moderna implementeringar. |
| URL-filter | x |  |  |  | Ger åtkomst till Allmänt > Interna URL-filter i Report Suite Manager. |
| Avvikelseidentifiering |  | x |  |  | Ger åtkomst till avvikelseidentifiering i Analysis Workspace. |
| Bidragsanalys |  | x |  |  | Ger åtkomst till högerklicksmenyn Kör bidragsanalys i Analysis Workspace. |
| Anpassad Data Warehouse |  | x |  |  | Ger åtkomst till Verktyg > Data Warehouse i den övre navigeringen i Analytics. |
| Konfiguration av Advertising Analytics |  |  |  | x | Används inte. |
| Sammanfattningsrapport för företag |  |  |  | x | Används inte. |
| Data Warehouse |  |  |  | x | Används inte. Använd rapporten för anpassad Data Warehouse i stället. |
| Bild |  |  |  | x | Används inte. |
| KPI/mätarrapport |  |  |  | x | Används inte. |
| De senaste 100 besökarna |  |  |  | x | Används inte. |
| Äldre ClickMap |  |  |  | x | Används inte. Använd Activity Map under Analytics Tools i stället. |
| Installation av äldre klickkarta |  |  |  | x | Används inte. Använd Activity Map under Analytics Tools i stället. |
| Översiktsrapport för mobilappar |  |  |  | x | Används inte. |
| Rapportsvitsummor |  |  |  | x | Används inte. |
| Rapportsviter (läs) |  |  |  | x | Används inte. |
| Rapportsviter (skriv) |  |  |  | x | Används inte. |
| Site Catalyst |  |  |  | x | Används inte. Använd Analysis Workspace Access i stället. |
| Social |  |  |  | x | Används inte. |
| Textrapport |  |  |   | x | Används inte. |
| Trafikhantering |  |  |  | x | Används inte. |
| Användningssammanfattningsrapport |  |  |  | x | Används inte. |
| Videoinställningar |  |  |  | x | Används inte. |
| Webbresurser |  |  |  | x | Används inte. |

{style="table-layout:auto"}

## Analysverktyg

| Analysverktyg | Administrering | Åtkomstkontroller | Funktioner endast för rapporter | Föråldrat | Beskrivning |
| --- | --- | --- | --- | --- | --- |
| Kodhanteraren | x |  |  |  | Vi har kvar dem i bakgrunden. Ger åtkomst till Admin > Alla administratörer > Kodhanteraren. I de flesta fall bör du i stället använda de bibliotek som ingår i Adobe Analytics-tillägget i Adobe Experience Platform Data Collection. |
| Kodhanteraren - webbtjänster | x |  |  |  | Ger åtkomst till Code Manager via 1.4 API. |
| Dölj rapportsviter | x |  |  |  | Ger åtkomst till Admin > All admin > Company settings > Hide Report Suites. Ger möjlighet att dölja alla rapporteringsprogram i organisationen, oavsett åtkomst till deras rapporteringsprogram. |
| Integreringar (skapa) | x |  |  |  | Ger åtkomst till Admin > Alla administratörer > Datakopplingar och låter användaren skapa dataanslutningar. |
| Integreringar (ta bort) | x |  |  |  | Ger åtkomst till Admin > Alla administratörer > Datakopplingar och låter användaren ta bort dataanslutningar. |
| Integreringar (uppdatering) | x |  |  |  | Ger åtkomst till Admin > Alla administratörer > Datakopplingar och låter användaren ändra befintliga kopplingskonfigurationer. |
| Loggar | x |  |  |  | Ger åtkomst till Admin > Alla administratörer > Loggar. |
| Loggar - webbtjänster | x |  |  |  | Ger åtkomst till pull-loggar via 1.4-API:t. |
| Väntande åtgärder | x |  |  |  | Ger åtkomst till Admin > Alla administratörer > Företagsinställningar > Väntande åtgärder. |
| Säkerhet | x |  |  |  | Ger åtkomst till Admin > All admin > Company settings > Security Manager. |
| Användning av serversamtal | x |  |  |  | Ger åtkomst till Admin > Serversamtalsanvändning. |
| Support | x |  |  |  | Ger åtkomst till Admin > All admin > Company settings > Support Information. |
| Trafikhantering | x |  |  |  | Ger åtkomst till Admin > All admin > Traffic Management. |
| Webbtjänster | x |  |  |  | Ger åtkomst till Admin > All admin > Company settings > Web Services. |
| Dela projektlänkar med vem som helst | x |  |  |  | Ger användare åtkomst att Dela med vem som helst i ett Workspace-projekt -> Dela -> Dela med vem som helst. |
| Activity Map |  | x |  |  | Ger åtkomst till Verktyg > Activity Map. Tillåter användaren att använda tillägget Activity Map. |
| Ad Hoc Analysis License Users |  | x |  |  | Ad Hoc Analysis har blivit uppsagd. [Mer information](https://spark.adobe.com/page/S9Bhp66VJ2fEn/). |
| Analysis Workspace Access |  | x |  |  | Ger åtkomst till Analysis Workspace. |
| Analysis Workspace: Spara som mall |  | x |  |  | Ger åtkomst till Projekt > Spara som mall i Analysis Workspace. |
| Skapande av beräknade mätvärden |  | x |  |  | Ger möjlighet att skapa beräknade värden för alla Analytics-funktioner. |
| Labs Access |  | x |  |  | Ger tillgång till Labs. |
| Report Builder |  | x |  |  | Aktiverar hämtningsknappen under Verktyg > Report Builder och tillåter att användaren autentiserar i Microsoft Excel. |
| Skapa segment |  | x |  |  | Ger möjlighet att skapa och dela segment över alla Analytics-funktioner. |
| Segmentpublicering |  | x |  |  | Ger möjlighet att göra ett segment till en Experience Cloud-målgrupp när du skapar eller redigerar ett segment. |
| Webbtjänståtkomst |  | x |  |  | Ger möjlighet att använda API:t, inklusive autentisering med tredjepartswebbplatser och sändande API-anrop. |
| Hantering av Advertising Analytics |  |  |  | x | Används inte. |
| Sammärkning |  |  |  | x | Används inte längre. Ger åtkomst till Admin > All admin > Company settings > Co-Branding. |
| Excel-licensanvändare |  |  |  | x | Används inte. |
| Administratör för mobilapp |  |  |  | x | Används inte. |
| Behörighetshantering |  |  |  | x | Används inte längre. Ger åtkomst till det äldre användarhanteringsgränssnittet under Admin > Alla administratörer > Användarhantering. |
| Behörigheter (läs) - webbtjänster |  |  |  | x | Används inte längre. Låter användaren visa äldre Analytics-behörigheter med Admin API. Använd Adobe Admin Console istället. |
| Behörigheter (skrivbehörighet) - webbtjänster |  |  |  | x | Används inte längre. Låter användaren redigera äldre analysbehörigheter med hjälp av Admin API. Använd Adobe Admin Console istället. |
| Inställningar |  |  |  | x | Används inte. |
| Enkel inloggning |  |  |  | x | Används inte längre. Ger åtkomst till den inaktuella Single Sign-On-tjänsten. |

{style="table-layout:auto"}