---
title: Komponentstöd i Data Warehouse
description: Läs om vilka ytterligare mått och mätvärden som finns i Data Warehouse och vad som inte stöds.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 0%

---

# Komponentstöd i Data Warehouse

Tack vare den unika bearbetningen i Data Warehouse-arkitekturen kan vissa komponenter som vanligtvis inte är tillgängliga i andra funktioner i Adobe Analytics användas. På grund av sin unika arkitektur är vissa komponenter inte tillgängliga för användning i vare sig rapporter eller segment. Använd den här sidan för att förstå vad som kan användas och vad som inte kan användas.

## Komponenter som är unika för Data Warehouse

Vissa dimensioner och mätvärden som kan användas i Data Warehouse är inte tillgängliga när andra funktioner används i Adobe Analytics.

### Endast dimensioner som stöds

* **Experience Cloud ID**: För implementeringar som använder Experience Cloud ID Service (ECID), är ett 128-bitars nummer bestående av två sammanfogade 64-bitarsnummer som fyllts i med 19 siffror.
* **Sidans URL**: Den sidadress som träffen inträffade på.
* **Inköps-ID**: Unik identifierare för ett inköp, anges med variabeln purchaseID.
* **Besökar-ID**: Anger den unika identifieraren för besökaren. Det här värdet är samma som det sammanfogade värdet för `visid_high` och `visid_low` kolumner i dataflöden. Mer information finns i [Datakolumnreferens](../analytics-data-feed/c-df-contents/datafeeds-reference.md) under Datafeeds.

### Endast mått som stöds

* **Besök**: Det här måttet i samband med Data Warehouse utesluter icke-beständiga cookie-besök.
* **Besök - alla besökare**: Det här måttet i Data Warehouse-sammanhang liknar besöksmätningen i andra verktyg i Adobe Analytics.

## Komponenter som inte stöds i Data Warehouse

Vissa dimensioner och mätvärden stöds inte i Data Warehouse.

>[!NOTE]
>
>Om en dimension eller ett mått inte stöds i Data Warehouse stöds inte heller segment som använder dessa komponenter. Kontrollera alltid produktkompatibilitet när du skapar eller redigerar ett segment.

### Dimensioner stöds inte

* AM/PM
* Några målningsbaserade dimensioner, bland annat:
   * Alla inmatningsdimensioner, utom inmatningssida
   * Alla avslutningsdimensioner, utom Avsluta sida och Avsluta länk
   * Träff-djup
   * Returfrekvens
   * Tid före händelse
   * Tid som använts på sidan - paketerad
   * Tid per besök - paketerad
* Alla söksidrankning
* Hierarkivariabler
* Träfftyp
* Sidor som inte hittas (tillgängliga som en dimension, stöds inte för segmentering)
* Betalsökning
* Besök på en sida
* Orsak till avanmälan av spårning
* USA

### Mått stöds inte

* Några målningsbaserade mätvärden, bland annat:
   * Studsar
   * Poster
   * Avslutar
   * Läs in igen
   * Enkel åtkomst
   * Mätvärden för tidsåtgång
* Deltagandestatistik (enligt beskrivningen i [Bygg ett delgivningsmått](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md))

### Dimensioner stöds på ett annat sätt (icke-standard datumformatering)

Följande tidsbaserade dimensioner stöds:

* År
* Kvartal
* Månad
* Vecka
* Dag
* Timme
* Minut

Datumutdata är dock inte standard när de här måtten används.

Tänk på följande när du beräknar datumutdata i Data Warehouse:

* Datumdimensioner visas i följande format: `1YYMMDDHHMM`

* År (YY) är 1900. Det innebär att du lägger till `1900` till de första tre värdena i datumfältet.

  Om till exempel värdet för fältet Datumintervallvecka i Data Warehouse är `1250901` lägger du till 1900 till 125, vilket resulterar i 2025.

* Alla månader är nollbaserade. Januari representeras av 00, februari av 01 och så vidare, enligt följande:

   * 00: Januari
   * 01: februari
   * 02: Mars
   * 03: April
   * 04: Maj
   * 05: Juni
   * 06: juli
   * 07: augusti
   * 08: september
   * 09: oktober
   * 10: November
   * 11: December

  Om till exempel värdet för fältet Datumintervallvecka i Data Warehouse är `1250901`, visas månaden som 09, vilket anger oktober.




## Segmentera som dimensioner i Data Warehouse

När du använder ett segment som en dimension i Data Warehouse returnerar rapporten en kolumn som innehåller `"0"` eller `"1"`:

* **`"0"`**: Dimensionsobjektet uppfyllde inte segmentets villkor.
* **`"1"`**: Dimensionsobjektet uppfyller segmentets villkor.
