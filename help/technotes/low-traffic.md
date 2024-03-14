---
description: När en rapport har många unika värden använder Adobe måttobjektet Lågtrafik för att förbättra rapportens prestanda.
title: Lågtrafikvärde i Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: fe6b1a2d503bbc423d3ebcacad2ce3c29e1ebbed
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 0%

---

# Lågtrafikvärde i Adobe Analytics

När en rapport har många unika värden tillhandahåller Adobe funktioner som säkerställer att de viktigaste värdena visas i rapporten. Unika variabelvärden som samlats in utöver ett visst tröskelvärde (se nedan) listas under en dimensionspost som är märkt **[!UICONTROL Low-Traffic]**.

## Hur [!UICONTROL Low-Traffic] verk

* Adobe Analytics använder två tröskelvärden för att avgöra vilka unika värden som visas i rapporter varje månad: A **[!UICONTROL low threshold]** och **[!UICONTROL high threshold]**. Dessa tröskelvärden kan justeras av Adobe då och då. De nuvarande tröskelvärdena är:
   * **[!UICONTROL Low threshold]**: >500 000 unika värden under månaden.
   * **[!UICONTROL High threshold]**: >1 000 000 unika värden under månaden.
* I **mitten av april 2024** kommer Adobe att börja öka standardrapporteringsprogrammets lågtrafiktrösklar enligt följande: ![lågtrafiktrösklar](assets/thresholds.png)
Detta påverkar endast variabler som för närvarande ligger under de nya tröskelvärdena. Dessa ändringar kommer att göras stegvis, och vi förväntar oss att arbetet ska vara slutfört av **slutet av maj**. När dessa ökningar introduceras kan du märka förändringar för variabler med hög kardinalitet:<ul><li>Fler dimensionsvärden kan vara tillgängliga för rapportering.</li><li>Segment och beräknade värden kan innehålla mer data.</li><li>Virtuella rapportsviter baserade på segment kan innehålla mer data.</li><li>Export av klassificeringar kan innehålla mer data.</li></ul>
* Rapporteringen påverkas inte om variabeln inte når det låga tröskelvärdet under en viss månad.
* När en variabel når det låga tröskelvärdet börjar data att paketeras under [!UICONTROL Low-Traffic]. Varje värde som ligger utanför detta tröskelvärde följer följande logik:
   * Om ett värde redan visas i rapporter lägger du till det värdet som vanligt.
   * Om ett värde ännu inte visas i rapporter är det till att börja med inbyggt i [!UICONTROL Low-Traffic] dimensionsobjekt.
   * Om ett värde som är bundet under [!UICONTROL Low-Traffic] tar emot ett inflöde av trafik (oftast i dubbelsiffror på en dag), och börjar identifieras som sin egen dimensionspost. Inkomster som samlats in innan tröskelvärdet uppnåddes ligger fortfarande under [!UICONTROL Low-Traffic]. Den exakta punkt där dimensionsobjektet börjar visas i rapporter har många beroenden, till exempel antalet servrar som bearbetar data för rapportsviten och tiden mellan varje dimensionsobjektsinstans.
* Om en variabel når det höga tröskelvärdet används mer aggressiv filtrering. Unika värden kräver instanser i de tre siffrorna på en dag innan de identifieras som sina egna dimensionsobjekt.

Tack vare den här logiken kan Adobe optimera rapporteringsfunktionerna samtidigt som organisationen kan rapportera viktiga dimensionsobjekt som samlas in senare under månaden. Om din organisation till exempel har en webbplats med miljontals artiklar och en ny artikel blir populär mot slutet av månaden (efter att ha överskridit båda unika tröskelvärden) kan du fortfarande analysera hur den artikeln fungerar utan att den är bucketad under [!UICONTROL Low-Traffic]. Den här logiken är inte avsedd att ta bort allt som får ett visst antal sidvisningar per dag eller månad.

>[!NOTE]
>The [Sida](../components/dimensions/page.md) Dimensionen använder flera backend-kolumner som alla räknar mot unika tröskelvärden, inklusive `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`och `click_context`. Dessa backend-kolumner kan orsaka [!UICONTROL Low-Traffic] logik som ska användas långt innan antalet unika sidodimensionsobjekt i Workspace når det låga tröskelvärdet.

Observera att den lågtrafiklogik som beskrivs ovan fungerar bäst med variabler som har dimensionsobjekt som återkommer många gånger under månaden. Om en variabels dimensionsposter är nästan eller helt unika för varje träff, kommer variabeln att nå det låga tröskelvärdet snabbt och alla nya dimensionsposter för månaden kommer att hamna i lågtrafikpytsen.

## Ändra unika gränströsklar

Tröskelvärdena kan ibland ändras för varje variabel. Kontakta Adobe kundtjänst eller ditt kontoteam på Adobe för att begära denna ändring. I vilken utsträckning tröskelvärdena kan höjas beror på flera faktorer och Adobe kanske inte kan anpassa sig till tröskelökningar i samtliga fall. När du begär en ändring, inkludera:

* Rapportsvitens ID
* Variabeln som du vill öka tröskelvärdet för
* Både det första och det andra tröskelvärdet önskades

Ändringar av tröskelvärden kan påverka rapportens prestanda. Adobe rekommenderar starkt att man använder god vana vid att begära en ökning av unika värden i en variabel. Öka bara de unika gränserna för variabler som är viktiga för organisationens rapporteringsbehov.

Lågtrafiktröskelvärden visas inte i analysgränssnittet. Kontakta Adobe kundtjänst om du vill ha mer information om de befintliga tröskelvärdena.

## Låg trafik med komponenter och andra funktioner

Olika funktioner behandlar lågtrafikvärden på olika sätt.

* **Data Warehouse:** Det finns ingen gräns för antalet unika värden i Data Warehouse. Dess unika arkitektur gör det möjligt att rapportera hur många unika värden som helst.
   * I vissa begränsade scenarier kan lågtrafikvärden fortfarande förekomma. Exempel är listvariabler, listprops, eVars för försäljning och detaljdimensioner för marknadsföringskanaler.
* **Segmentering:** Om segmentkriterierna innehåller en variabel med ett stort antal unika värden, inkluderas inte värden som hämtats under lågtrafik.
* **Klassificeringar:** Klassificeringsrapporterna omfattas också av unika begränsningar. Om en klassificerings överordnade variabelvärde inkluderas under lågtrafik, klassificeras inte värdet.
   * Lågtrafikklassificerade värden som erhållits av importören kan visas i Data Warehouse. <!-- AN-115871 -->
   * Värden för lågtrafikklassificering som erhållits via regelbyggaren *inte* visas i Data Warehouse. <!-- AN-122872 -->
