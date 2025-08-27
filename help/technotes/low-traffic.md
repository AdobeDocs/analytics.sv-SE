---
description: När en rapport har många unika värden använder Adobe måttobjektet Lågtrafik för att förbättra rapportens prestanda.
title: Lågtrafikvärde i Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 42d044c3c56f13a232b721ef60f64bcf622ffa9f
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 0%

---

# [!UICONTROL Low-Traffic]-värde i Adobe Analytics

När en dimension innehåller miljontals unika värden tillhandahåller Adobe funktioner som säkerställer att de viktigaste värdena visas i rapporten i tid. Unika värden som samlats in utöver ett visst tröskelvärde listas under ett dimensionsobjekt med namnet **[!UICONTROL Low-Traffic]**.

Dimensionsobjektet [!UICONTROL Low-Traffic] gör det möjligt för Adobe att säkerställa att rapporter returneras i tid genom att ta överflödiga unika värden och paketera dem tillsammans.

Observera att logiken i [!UICONTROL Low-traffic] fungerar bäst med dimensioner som har objekt som upprepas många gånger under månaden. Om dimensionsobjekten är nästan eller helt unika för varje träff når antalet unika värden tröskeln snabbt och alla efterföljande värden för månaden hamnar i [!UICONTROL Low-Traffic]-haken.

## Ange värden [!UICONTROL Low-Traffic]

Som standard anges ett tröskelvärde på **2 000 000 unika värden** per dimension, per rapportsvit, per kalendermånad. Dimension-objekt som överskrider det här unika tröskelvärdet paketeras under [!UICONTROL Low-Traffic].

* Dimension-objekt som samlats in innan tröskelvärdet nås beräknas normalt.
* Dimension-objekt som samlats in efter att tröskelvärdet har överskridits är paketerade under [!UICONTROL Low-Traffic].

>[!NOTE]
>Dimensionen [Sida](../components/dimensions/page.md) använder flera backend-kolumner som alla räknar mot det unika tröskelvärdet, inklusive `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url` och `click_context`. Dessa backend-kolumner kan göra att [!UICONTROL Low-Traffic]-logik används långt innan antalet unika sidodimensionsobjekt i Workspace når tröskelvärdet.

Den unika gränsen på 2 000 000 kan ändras per dimension. Se [Ändra unika tröskelvärden](#changing-unique-limit-thresholds) nedan. I slutet av en kalendermånad återställs antalet spårade unika värden globalt.

## Så här kan värden kringgå [!UICONTROL Low-Traffic] efter att tröskelvärdet har överskridits

Om en given dimension samlar in över 2 000 000 unika värden under en given månad, kan enskilda dimensionsobjekt återgå till att rapportera sin egen dimensionspost. Det främsta användningsområdet för den här funktionen är att tillåta rapportering av viktiga dimensionsposter som kan få en ökning av popularitet sent under månaden efter att det unika tröskelvärdet har överskridits. Om din organisation till exempel har en webbplats med miljontals artiklar och en ny artikel blir populär i slutet av månaden kan du fortfarande analysera hur den artikeln fungerar. Den här logiken är inte avsedd att ta bort allt som får ett visst antal instanser, utan snarare erbjuder en möjlighet att analysera innehåll som tar emot en ström av trafik.

Kraven för att ett enskilt dimensionsobjekt ska undantas [!UICONTROL Low-Traffic] beror på många faktorer, varav många förhindrar möjligheten att beräkna ett exakt tröskelvärde:

* **Antal servrar som bearbetar data för rapportsviten**: Rapporteringssviter med mer trafik kräver fler instanser av ett enskilt dimensionsobjekt för att kunna kringgås [!UICONTROL Low-Traffic].
* **Tiden mellan varje instans av dimensionsobjektet**: Träffar som innehåller ett uppslag för dimensionsobjektet under dagen kräver fler instanser än en koncentrerad ökning av träffar.
* **Antal unika värden för dimensionen**: Varje dimension har som standard ett andra tröskelvärde som är 2 100 000 unika värden. Om antalet unika värden i en dimension överskrider det högre tröskelvärdet tillämpas mycket mer aggressiv filtrering.

Om du tar hänsyn till ovanstående faktorer kan du förvänta dig att **hundratals till tusentals** instanser för ett enskilt dimensionsobjekt kommer att komma bort [!UICONTROL Low-Traffic] om bara det första tröskelvärdet överskrids. **tusentals till tiotusentals** instanser av ett enskilt dimensionsobjekt kan komma att kringgås [!UICONTROL Low-Traffic] om det högre tröskelvärdet överskrids. Adobe garanterar inte att dimensionsobjekten på ett tillförlitligt sätt kan kringgå [!UICONTROL Low-Traffic]-bucket. Det här konceptet är vanligtvis reserverat för dimensionsartiklar med mycket stora volymer som kommer för sent under månaden.

När ett dimensionsobjekt kringgår [!UICONTROL Low-Traffic]-bucket blir instanser som samlats in före inflödet av trafik kvar under [!UICONTROL Low-Traffic].

## Ändra unika gränströsklar

Tröskelgränser kan ibland ändras per dimension. Kontakta Adobe kundtjänst eller ditt kontoteam på Adobe för att begära denna ändring. I vilken utsträckning tröskelvärdena kan höjas beror på flera faktorer. Adobe garanterar inte att alla tröskelökningsbegäranden kan hanteras. När du begär en ändring, inkludera:

* Rapportsvitens ID
* Dimensionen som du vill öka tröskelvärdet för
* Både det första och det andra tröskelvärdet önskades:
   * Det första tröskelvärdet (inledande spärring) är som standard **2 000 000**.
   * Det andra tröskelvärdet (mer aggressiv filtrering) är som standard **2,100,000**.

>[!IMPORTANT]
>
>Ändringar av tröskelvärden kan påverka rapportens prestanda. Adobe rekommenderar starkt att man använder god vana vid att begära en ökning av unika värden för en dimension. Öka bara de unika gränserna för dimensioner som är viktiga för organisationens rapporteringsbehov.

[!UICONTROL Low-Traffic]-trösklar visas inte i analysgränssnittet. Kontakta Adobe kundtjänst om du vill ha mer information om tröskelvärdena.

## Interaktion med andra funktioner

Olika funktioner behandlar [!UICONTROL Low-Traffic]-värden på olika sätt.

* **Data Warehouse:** I de flesta fall finns det ingen gräns för antalet unika värden i Data Warehouse-rapporter. Dess unika arkitektur gör det möjligt att rapportera hur många unika värden som helst. [!UICONTROL Low-Traffic] värden kan dock fortfarande visas i vissa begränsade scenarier. Exempel är listvariabler, listprops, eVars för försäljning och detaljdimensioner för marknadsföringskanaler.
* **Segmentering:** Om segmentvillkoret innehåller en dimension med ett stort antal unika värden, inkluderas inte värden som hämtats under [!UICONTROL Low-Traffic].
* **Klassificeringar:** Klassificeringsrapporter har också unika begränsningar. Om en klassificerings överordnade dimensionsobjekt ingår under [!UICONTROL Low-Traffic] klassificeras inte värdet.
   * [!UICONTROL Low-Traffic] värden som klassificerats genom importeraren kan visas i Data Warehouse. <!-- AN-115871 -->
   * [!UICONTROL Low-Traffic] värden som klassificerats med regelbyggaren *kan inte* visas i Data Warehouse. <!-- AN-122872 -->
