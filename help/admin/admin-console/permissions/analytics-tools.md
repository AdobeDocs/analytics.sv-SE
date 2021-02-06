---
source-git-commit: 45edc5eacde90dc5b5da140ad50561f0f32bb41d
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '558'
ht-degree: 3%

---
# Produktprofilbehörigheter för analysverktyg

Behörighetsobjekt för Analytics-verktyg ger åtkomst till funktioner i Adobe Analytics. Behörighetsobjekten för analysverktygen gäller inte för en rapportserie, utan för Adobe Analytics som helhet.

| Behörighetsobjekt för analysverktyg | Beskrivning |
|----|----|
| Användning av serversamtal | Ger åtkomst till Admin > Serversamtalsanvändning. |
| Kodhanteraren | Vi har kvar dem i bakgrunden. Ger åtkomst till Admin > Code Manager. I de flesta fall bör du använda de bibliotek som finns i Adobe Experience Platform Launch i stället. |
| Kodhanteraren - webbtjänster | Ger åtkomst till Code Manager via 1.4-API:t. |
| Loggar | Ger åtkomst till Admin > Logs. |
| Loggar - webbtjänster | Ger åtkomst till pull-loggar via 1.4-API:t. |
| Trafikhantering | Ger åtkomst till Admin > Traffic Management. |
| Behörighetshantering | Används inte längre. Ger åtkomst till det äldre användarhanteringsgränssnittet under Admin > Användarhantering. |
| Behörigheter (läs) - webbtjänster | Används inte längre. Låter användaren visa äldre Analytics-behörigheter med Admin API. Använd Adobe Admin Console istället. |
| Behörigheter (skrivbehörighet) - webbtjänster | Används inte längre. Låter användaren redigera äldre analysbehörigheter med hjälp av Admin API. Använd Adobe Admin Console istället. |
| Säkerhet | Ger åtkomst till Admin > Företagsinställningar > Säkerhetshanteraren. |
| Support | Ger åtkomst till Admin > Företagsinställningar > Supportinformation. |
| Webbtjänster | Ger åtkomst till Admin > Företagsinställningar > Webbtjänster. |
| Enkel inloggning | Används inte längre. Ger åtkomst till den inaktuella Single Sign-On-tjänsten. |
| Väntande åtgärder | Ger åtkomst till Admin > Företagsinställningar > Väntande åtgärder. |
| Samprofilering | Används inte längre. Ger åtkomst till Admin > Företagsinställningar > Sammärkning. |
| Inställningar | Används inte. |
| Dölj rapportsviter | Ger åtkomst till Admin > Företagsinställningar > Dölj rapportsviter. Ger möjlighet att dölja alla rapporteringsprogram i organisationen, oavsett åtkomst till deras rapporteringsprogram. |
| Excel-licensanvändare | Används inte. |
| Activity Map | Ger åtkomst till Verktyg > Activity Map. Tillåter användaren att använda tillägget Activity Map. |
| Aktuella data | Aktiverar alternativet att visa aktuella data i rapporter och analysrapporter. |
| Ad Hoc Analysis License Users | Aktiverar hämtningsknappen under Verktyg > Ad Hoc Analysis och tillåter användaren att autentisera med verktyget. Se [adobe.ly/discoverworkspace](https://adobe.ly/discoverworkspace). |
| Administratör för mobilapp | Används inte. |
| Webbtjänståtkomst | Ger möjlighet att använda API:t, inklusive autentisering med tredjepartswebbplatser och sändande API-anrop. |
| Report Builder | Aktiverar hämtningsknappen under Verktyg > Report Builder och tillåter att användaren autentiserar i Microsoft Excel. |
| Analysis Workspace Access | Ger åtkomst till Analysis Workspace. Användarna måste tillhöra den här gruppen (helst) eller Rapporter och analyser för att kunna använda Adobe Analytics. |
| Rapporter och analysåtkomst | Ger åtkomst till rapporter och analyser. Användare måste tillhöra den här gruppen eller Analysis Workspace Access (standard) för att kunna använda Adobe Analytics. |
| Analysis Workspace: Spara som mall | Ger åtkomst till Projekt > Spara som mall i Analysis Workspace. |
| Åtkomst till labb | För närvarande under utveckling. När de släpps ger tillgång till Labs. |
| Skapande av beräknade mätvärden | Ger möjlighet att skapa beräknade värden för alla Analytics-funktioner. |
| Skapa segment | Ger möjlighet att skapa och dela segment över alla Analytics-funktioner. |
| Hantering av Advertising Analytics | Används inte. |
| Segmentpublicering | Ger möjlighet att göra ett segment till en Experience Cloud-målgrupp när du skapar eller redigerar ett segment. |
| Integreringar (skapa) | Ger åtkomst till Admin > Data Connectors och låter användaren skapa dataanslutningar. |
| Integreringar (uppdatering) | Ger åtkomst till Admin > Data Connectors och låter användaren ändra befintliga kopplingskonfigurationer. |
| Integreringar (ta bort) | Ger åtkomst till Admin > Data Connectors och tillåter användaren att ta bort dataanslutningar. |
