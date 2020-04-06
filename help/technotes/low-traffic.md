---
description: När en rapport har ett stort antal unika värden tillhandahåller Adobe funktioner som säkerställer att de viktigaste värdena visas i rapporten.
title: Lågtrafikvärde i Adobe Analytics
topic: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Lågtrafikvärde i Adobe Analytics

När en rapport har ett stort antal unika värden tillhandahåller Adobe funktioner som säkerställer att de viktigaste värdena visas i rapporten. Unika variabelvärden som samlats in efter cirka 500 000 befintliga värden listas under en radobjekt med namnet **(lågtrafik)**.

## Hur låg trafik fungerar

* Rapporteringen påverkas inte om variabeln inte når 500 000 unika värden under en viss månad.
* När en variabel når detta första tröskelvärde på 500 000 kommer data att paketeras under låg trafik. Varje värde som ligger utanför detta tröskelvärde följer följande logik:
   * Om ett värde redan finns i rapporter lägger du till det som vanligt.
   * Om ett värde ännu inte har rapporterats kontrollerar du om det har setts mer än ungefär tio gånger idag. Om så är fallet lägger du till det här värdet i rapporteringen. Om den inte har räknats mer än tio gånger, lämna den under lågtrafik.
* Om en rapportserie når över 1 000 000 unika värden tillämpas mer aggressiv filtrering:
   * Om ett värde redan finns i rapporter lägger du till det som vanligt.
   * Om ett värde ännu inte har rapporterats kontrollerar du om värdet har setts mer än cirka 100 gånger idag. Om så är fallet lägger du till värdet i rapporten. Om det inte gör det, lämna det under lågtrafik.

>[!NOTE] Om ett variabelvärde tar emot tillräckligt mycket trafik för att lämna lågtrafikpytsen flyttas inte de första värdena som samlas in till respektive radpost. De första 10-100 instanserna har låg trafik.

## Ändra unika gränströsklar

Tröskelvärdena är som standard 500 000 och 1 miljon unika värden. Dessa gränser kan ändras för varje variabel. Kontakta din organisations kontoansvarige för att begära denna ändring. När du begär en ändring, inkludera:

* Rapportsvitens ID
* Variabeln som du vill öka tröskelvärdet för
* Både det första och det andra tröskelvärdet önskades

Ändringar av tröskelvärden kan påverka rapportens prestanda. Adobe rekommenderar starkt att du använder god vana vid att begära en ökning av unika värden i en variabel.

Lågtrafiktröskelvärden visas inte i analysgränssnittet. Be en användare i organisationen kontakta Adobes kundtjänst om du vill ha mer information om befintliga tröskelvärden.

## Låg trafik med komponenter och andra funktioner

Olika funktioner behandlar lågtrafikvärden på olika sätt.

* **Datalager:** Det finns ingen gräns för antalet unika värden i datalagerrapporter. Dess unika arkitektur gör det möjligt att rapportera hur många unika värden som helst.
   * I vissa begränsade scenarier kan lågtrafikvärden fortfarande förekomma. Exempel är listvariabler, listprops, eVars för försäljning och detaljdimensioner för marknadsföringskanaler.
* **Segmentering:** Om segmentkriterierna innehåller en variabel med ett stort antal unika värden, inkluderas inte värden som hämtats under lågtrafik.
* **Klassificeringar:** Klassificeringsrapporterna omfattas också av unika begränsningar. Om en klassificerings överordnade variabelvärde inkluderas under lågtrafik, klassificeras inte värdet.
   * Om du klassificerar värden innan de visas i data räknas dessa värden mot den unika tröskeln för den månaden.
