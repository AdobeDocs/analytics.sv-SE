---
title: Produktprofilbehörigheter för analysverktyg
description: Använd behörighetsobjekt i Analytics Tools för att ge åtkomst till funktioner i Adobe Analytics.
exl-id: 8c2ce50b-f75f-41c3-91ac-a0426ce27438
source-git-commit: 8d409f27024a8c58bc875555ad5aa980815d1fc9
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 4%

---

# Produktprofilbehörigheter för analysverktyg

Behörighetsobjekt för Analytics-verktyg ger åtkomst till funktioner i Adobe Analytics. Behörighetsobjekten för analysverktygen gäller inte för en rapportserie, utan för Adobe Analytics som helhet.

| Behörighetsobjekt för analysverktyg | Beskrivning |
|----|----|
| Användning av serversamtal | Ger åtkomst till Admin > Serversamtalsanvändning. |
| Kodhanteraren | Vi har kvar dem i bakgrunden. Ger åtkomst till Admin > Alla administratörer > Kodhanteraren. I de flesta fall bör du använda de bibliotek som finns i Adobe Experience Platform Launch i stället. |
| Kodhanteraren - webbtjänster | Ger åtkomst till Code Manager via 1.4-API:t. |
| Loggar | Ger åtkomst till Admin > Alla administratörer > Loggar. |
| Loggar - webbtjänster | Ger åtkomst till pull-loggar via 1.4-API:t. |
| Trafikhantering | Ger åtkomst till Admin > All admin > Traffic Management. |
| Säkerhet | Ger åtkomst till Admin > All admin > Company settings > Security Manager. |
| Support | Ger åtkomst till Admin > All admin > Company settings > Support Information. |
| Webbtjänster | Ger åtkomst till Admin > All admin > Company settings > Web Services. |
| Väntande åtgärder | Ger åtkomst till Admin > Alla administratörer > Företagsinställningar > Väntande åtgärder. |
| Dölj rapportsviter | Ger åtkomst till Admin > All admin > Company settings > Hide Report Suites. Ger möjlighet att dölja alla rapporteringsprogram i organisationen, oavsett åtkomst till deras rapporteringsprogram. |
| Excel-licensanvändare | Används inte. |
| Activity Map | Ger åtkomst till Verktyg > Activity Map. Tillåter användaren att använda tillägget Activity Map. |
| Aktuella data | Aktiverar alternativet att visa aktuella data i rapporter och analysrapporter. |
| Ad Hoc Analysis License Users | Ad Hoc Analysis har blivit uppsagd. Se [adobe.ly/discoverworkspace](https://adobe.ly/discoverworkspace). |
| Administratör för mobilapp | Används inte. |
| Webbtjänståtkomst | Ger möjlighet att använda API:t, inklusive autentisering med tredjepartswebbplatser och sändande API-anrop. |
| Report Builder | Aktiverar hämtningsknappen under Verktyg > Report Builder och tillåter att användaren autentiserar i Microsoft Excel. |
| Analysis Workspace Access | Ger åtkomst till Analysis Workspace. Användarna måste tillhöra den här gruppen (helst) eller Rapporter och analyser för att kunna använda Adobe Analytics. |
| Rapporter och analysåtkomst | Ger åtkomst till rapporter och analyser. Användare måste tillhöra den här gruppen eller Analysis Workspace Access (standard) för att kunna använda Adobe Analytics. |
| Analysis Workspace: Spara som mall | Ger åtkomst till Projekt > Spara som mall i Analysis Workspace. |
| Åtkomst till labb | Ge användarna tillgång till Labs och prototyperna i Labs. |
| Skapande av beräknade mätvärden | Ger möjlighet att skapa beräknade värden för alla Analytics-funktioner. |
| Skapa segment | Ger möjlighet att skapa och dela segment över alla Analytics-funktioner. |
| Hantering av Advertising Analytics | Används inte. |
| Segmentpublicering | Ger möjlighet att göra ett segment till en Experience Cloud-målgrupp när du skapar eller redigerar ett segment. |
| Integreringar (skapa) | Ger åtkomst till Admin > Alla administratörer > Datakopplingar och låter användaren skapa dataanslutningar. |
| Integreringar (uppdatering) | Ger åtkomst till Admin > Alla administratörer > Datakopplingar och låter användaren ändra befintliga kopplingskonfigurationer. |
| Integreringar (ta bort) | Ger åtkomst till Admin > Alla administratörer > Datakopplingar och låter användaren ta bort dataanslutningar. |
