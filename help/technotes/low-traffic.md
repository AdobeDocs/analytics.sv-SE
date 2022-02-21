---
description: När en rapport har ett stort antal unika värden tillhandahåller Adobe funktioner som säkerställer att de viktigaste värdena visas i rapporten.
title: Lågtrafikvärde i Adobe Analytics
feature: Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---

# Lågtrafikvärde i Adobe Analytics

När en rapport har många unika värden tillhandahåller Adobe funktioner som säkerställer att de viktigaste värdena visas i rapporten. Unika variabelvärden som samlats in efter ungefär 500 000 befintliga värden listas under en radartikel med namnet **[!UICONTROL Low-Traffic]**.

## Hur [!UICONTROL Low-Traffic] verk

* Rapporteringen påverkas inte om variabeln inte når 500 000 unika värden under en viss månad.
* När en variabel når detta första tröskelvärde på 500 000 kommer data att paketeras under låg trafik. Varje värde som ligger utanför detta tröskelvärde följer följande logik:
   * Om ett värde redan visas i rapporter lägger du till det värdet som vanligt.
   * Om ett värde ännu inte visas i rapporter visas det i [!UICONTROL Low-Traffic] radartikel. Om ett värde som ingår i [!UICONTROL Low-Traffic] radobjektet ses ett betydande antal gånger inom en kort tid och börjar identifieras som ett eget radobjekt. Det betydande antal gånger som ett objekt måste ses har många beroenden, till exempel antalet bearbetningsservrar och daemoner som bearbetar data för just den rapportsviten.
* Om en rapportserie når över 1 000 000 unika värden tillämpas mer aggressiv filtrering:
   * Om ett värde redan visas i rapporter lägger du till det värdet som vanligt.
   * Om ett värde ännu inte visas i rapporter visas det i [!UICONTROL Low-Traffic] radartikel. Om ett värde som ingår i [!UICONTROL Low-Traffic] radobjektet ses ett betydande antal gånger inom en kort tid och börjar identifieras som ett eget radobjekt. Det betydande antal gånger som ett objekt måste ses har många beroenden, till exempel antalet bearbetningsservrar och daemoner som bearbetar data för just den rapportsviten.

Varför flyttar Adobe ett objekt från [!UICONTROL Low Traffic] radartikel till sin egen radartikel? Den här flyttningen kan till exempel identifiera en populär ny sida eller ett nytt objekt som lades till senare under månaden (efter att uniques överskreds) och som får många träffar/vyer. Flyttningen är inte avsedd att fånga allt som får ett visst antal träffar/vyer per dag eller månad.

>[!NOTE]
>Antal sidsökningar inkluderar inte bara värden för [!UICONTROL pagename]/[!UICONTROL page_url]. Uppslagstabellen för sidor innehåller flera kolumner/fält, till exempel [!UICONTROL pagename], [!UICONTROL first_hit_pagename]/[!UICONTROL page_url], [!UICONTROL visit_pagename]/[!UICONTROL page_url]och klickningskontexten (gamla klickmappsdata).

## Ändra unika gränströsklar

Tröskelvärdena är som standard 500 000 och 1 miljon unika värden. Dessa gränser kan ändras för varje variabel. Kontakta din organisations kontoansvarige för att begära denna ändring. När du begär en ändring, inkludera:

* Rapportsvitens ID
* Variabeln som du vill öka tröskelvärdet för
* Både det första och det andra tröskelvärdet önskades

Ändringar av tröskelvärden kan påverka rapportens prestanda. Adobe rekommenderar starkt att man använder god vana vid att begära en ökning av unika värden i en variabel.

Lågtrafiktröskelvärden visas inte i analysgränssnittet. Be en användare i din organisation kontakta Adobe kundtjänst om du vill ha mer information om befintliga tröskelvärden.

## Låg trafik med komponenter och andra funktioner

Olika funktioner behandlar lågtrafikvärden på olika sätt.

* **data warehouse:** Det finns ingen gräns för antalet unika värden i Data warehouse-rapporter. Dess unika arkitektur gör det möjligt att rapportera hur många unika värden som helst.
   * I vissa begränsade scenarier kan lågtrafikvärden fortfarande förekomma. Exempel är listvariabler, listprops, eVars för försäljning och detaljdimensioner för marknadsföringskanaler.
* **Segmentering:** Om segmentkriterierna innehåller en variabel med ett stort antal unika värden, inkluderas inte värden som hämtats under lågtrafik.
* **Klassificeringar:** Klassificeringsrapporterna omfattas också av unika begränsningar. Om en klassificerings överordnade variabelvärde inkluderas under lågtrafik, klassificeras inte värdet.
   * Lågtrafikklassificerade värden som erhållits av importören kan visas i Data warehouse. <!-- AN-115871 -->
   * Värden för lågtrafikklassificering som erhållits via regelbyggaren *inte* visas i Data warehouse. <!-- AN-122872 -->
