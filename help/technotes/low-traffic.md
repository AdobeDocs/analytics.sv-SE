---
description: När en rapport har många unika värden använder Adobe måttobjektet Lågtrafik för att förbättra rapportens prestanda.
title: Lågtrafikvärde i Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 81c7dcea2d42ee8e31140523cd43cdfd001baf28
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# Lågtrafikvärde i Adobe Analytics

När en rapport har många unika värden tillhandahåller Adobe funktioner som säkerställer att de viktigaste värdena visas i rapporten. Unika variabelvärden som samlats in efter cirka 500 000 befintliga värden listas under en dimensionspost som är märkt **[!UICONTROL Low-Traffic]**.

## Hur [!UICONTROL Low-Traffic] verk

* Rapporteringen påverkas inte om variabeln inte når 500 000 unika värden under en viss månad.
* När en variabel når 500 000 unika värden, börjar data bli inkapslade under [!UICONTROL Low-Traffic]. Varje värde som ligger utanför detta tröskelvärde följer följande logik:
   * Om ett värde redan visas i rapporter lägger du till det värdet som vanligt.
   * Om ett värde ännu inte visas i rapporter är det till att börja med inbyggt i [!UICONTROL Low-Traffic] dimensionsobjekt.
   * Om ett värde som är bundet under [!UICONTROL Low-Traffic] tar emot ett inflöde av trafik (oftast i dubbelsiffror på en dag), och börjar identifieras som sin egen dimensionspost. Inkomster som samlats in innan tröskelvärdet uppnåddes ligger fortfarande under [!UICONTROL Low-Traffic]. Det exakta tröskelvärdet har många beroenden, till exempel antalet servrar som bearbetar data för rapportsviten och hur lång tid det tar mellan varje instans av dimensionsobjektet.
* Om en rapportserie når över 1 000 000 unika värden tillämpas mer aggressiv filtrering. Unika värden kräver instanser i de tre siffrorna på en dag innan de identifieras som sina egna dimensionsobjekt.

Tack vare den här logiken kan Adobe optimera rapporteringsfunktionerna samtidigt som organisationen kan rapportera viktiga dimensionsobjekt som samlas in senare under månaden. Din organisation har till exempel en webbplats med miljontals artiklar och en ny artikel har blivit populär i slutet av månaden (efter att ha överskridit båda tröskelvärdena). Du kan fortfarande analysera prestanda för den artikeln utan att den är bucketterad under [!UICONTROL Low-Traffic]. Den här logiken är inte avsedd att ta bort allt som får ett visst antal sidvisningar per dag eller månad.

>[!NOTE]
>The [Sida](../components/dimensions/page.md) Dimensionen använder flera backend-kolumner som alla räknar mot unika tröskelvärden, inklusive `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`och `click_context`. Dessa backend-kolumner kan orsaka [!UICONTROL Low-Traffic] logik som ska användas långt innan antalet unika sidodimensionsobjekt i Workspace når 500 000.

## Ändra unika gränströsklar

Tröskelvärdena är som standard 500 000 och 1 miljon unika värden. Dessa gränser kan ändras för varje variabel. Kontakta Adobe kundtjänst eller din organisations kontoansvarige för att begära denna ändring. När du begär en ändring, inkludera:

* Rapportsvitens ID
* Variabeln som du vill öka tröskelvärdet för
* Både det första och det andra tröskelvärdet önskades

Ändringar av tröskelvärden kan påverka rapportens prestanda. Adobe rekommenderar starkt att man använder god vana vid att begära en ökning av unika värden i en variabel. Öka bara de unika gränserna för variabler som är viktiga för organisationens rapporteringsbehov.

Lågtrafiktröskelvärden visas inte i analysgränssnittet. Kontakta Adobe kundtjänst om du vill ha mer information om tröskelvärdena.

## Låg trafik med komponenter och andra funktioner

Olika funktioner behandlar lågtrafikvärden på olika sätt.

* **data warehouse:** Det finns ingen gräns för antalet unika värden i Data warehouse-rapporter. Dess unika arkitektur gör det möjligt att rapportera hur många unika värden som helst.
   * I vissa begränsade scenarier kan lågtrafikvärden fortfarande förekomma. Exempel är listvariabler, listprops, eVars för försäljning och detaljdimensioner för marknadsföringskanaler.
* **Segmentering:** Om segmentkriterierna innehåller en variabel med ett stort antal unika värden, inkluderas inte värden som hämtats under lågtrafik.
* **Klassificeringar:** Klassificeringsrapporterna omfattas också av unika begränsningar. Om en klassificerings överordnade variabelvärde inkluderas under lågtrafik, klassificeras inte värdet.
   * Lågtrafikklassificerade värden som erhållits av importören kan visas i Data warehouse. <!-- AN-115871 -->
   * Värden för lågtrafikklassificering som erhållits via regelbyggaren *inte* visas i Data warehouse. <!-- AN-122872 -->
