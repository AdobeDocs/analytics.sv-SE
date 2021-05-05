---
description: När en rapport har ett stort antal unika värden tillhandahåller Adobe funktioner som säkerställer att de viktigaste värdena visas i rapporten.
title: Lågtrafikvärde i Adobe Analytics
feature: Mätvärden
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
translation-type: tm+mt
source-git-commit: 482dcc04b7d68c6a555d318d8493c309e5899ae1
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Lågtrafikvärde i Adobe Analytics

När en rapport har många unika värden tillhandahåller Adobe funktioner som säkerställer att de viktigaste värdena visas i rapporten. Unika variabelvärden som samlats in efter cirka 500 000 befintliga värden listas under ett radobjekt med namnet **(Lågtrafik)**.

## Hur låg trafik fungerar

* Rapporteringen påverkas inte om variabeln inte når 500 000 unika värden under en viss månad.
* När en variabel når detta första tröskelvärde på 500 000 kommer data att paketeras under låg trafik. Varje värde som ligger utanför detta tröskelvärde följer följande logik:
   * Om ett värde redan finns i rapporter lägger du till det som vanligt.
   * Om ett värde ännu inte rapporteras beror tröskelvärdena för antal&quot;observerade&quot; på serverdelskonfigurationer. De är inte exakta&quot; 10&quot; - eller&quot; 100&quot; gånger som de ses.
* Om en rapportserie når över 1 000 000 unika värden tillämpas mer aggressiv filtrering:
   * Om ett värde redan finns i rapporter lägger du till det som vanligt.
   * Om ett värde ännu inte rapporteras beror tröskelvärdena för antal&quot;observerade&quot; på serverdelskonfigurationer. De är inte exakta&quot; 10&quot; - eller&quot; 100&quot; gånger som de ses.

>[!NOTE]
>
>Om ett variabelvärde tar emot tillräckligt mycket trafik för att lämna lågtrafikpytsen flyttas inte de första värdena som samlas in till respektive radpost. De första 10-100 instanserna har låg trafik.

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
* **Segmentering:** Om segmentvillkoret innehåller en variabel med ett stort antal unika värden, inkluderas inte värden som hämtats under lågtrafik.
* **Klassificeringar:** Klassificeringsrapporter omfattas också av unika begränsningar. Om en klassificerings överordnade variabelvärde inkluderas under lågtrafik, klassificeras inte värdet.
   * Lågtrafikklassificerade värden som erhållits av importören kan visas i Data warehouse. <!-- AN-115871 -->
   * Lågtrafikklassificeringsvärden som erhållits via regelbyggaren *kan inte* visas i Data warehouse. <!-- AN-122872 -->
