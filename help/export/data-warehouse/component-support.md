---
title: Komponentstöd i Data Warehouse
description: Lär dig vilka ytterligare mått och mätvärden som finns i Datan Warehouse och vad som inte stöds.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: ecd02a087e7ab344ccfbad1d5e1c30260577002c
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 3%

---

# Komponentstöd i Data Warehouse

Tack vare den unika bearbetningen i Data Warehouse-arkitekturen kan vissa komponenter som vanligtvis inte är tillgängliga i andra funktioner i Adobe Analytics användas. På grund av sin unika arkitektur är vissa komponenter inte tillgängliga för användning i vare sig rapporter eller segment. Använd den här sidan för att förstå vad som kan användas och vad som inte kan användas.

## Komponenter som är unika för Datan Warehouse

Vissa mått och mätvärden som kan användas i Data Warehouse är inte tillgängliga när andra funktioner används i Adobe Analytics.

### Endast Dimensioner som stöds

* **EXPERIENCE CLOUD ID**: För implementeringar som använder Experience Cloud ID Service (ECID), ett 128-bitars nummer som består av två sammanfogade 64-bitars tal som fylls på med 19 siffror.
* **Sidans URL**: Den sid-URL som träffen inträffade på.
* **Inköps-ID**: Unik identifierare för ett köp, ange med variabeln purchaseID.
* **Besökar-ID**: Anger den unika identifieraren för besökaren. Det här värdet är samma som det sammanfogade värdet för `visid_high` och `visid_low` kolumner i dataflöden. Se [Referens för datakolumn](../analytics-data-feed/c-df-contents/datafeeds-reference.md) under Dataflöden för mer information.

### Endast mått som stöds

* **Besök**: Detta mått i samband med Data Warehouse utesluter icke-beständiga cookie-besök.
* **Besök - alla besökare**: Det här mätvärdet i samband med Data Warehouse är närmare paritet med besöksmätningen i andra verktyg i Adobe Analytics.

## Komponenter som inte stöds i Datan Warehouse

Vissa mått och mätvärden stöds inte i Datan Warehouse.

>[!NOTE]
>
>Om en dimension eller ett mått inte stöds i Datan Warehouse stöds inte heller segment som använder dessa komponenter. Kontrollera alltid produktkompatibilitet när du skapar eller redigerar ett segment.

### Dimensioner som inte stöds

* AM/PM
* Några målningsbaserade dimensioner, bland annat:
   * Alla inmatningsdimensioner, utom inmatningssida
   * Alla avslutningsdimensioner, utom Avsluta sida och Avsluta länk
   * Träff-djup
   * Återbesöksfrekvens
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
   * Första besökssida
   * Sista besökssida
   * Siduppdateringar
   * Enkelt besök
   * Mätvärden för tidsåtgång
* Deltagandestatistik (enligt beskrivning i [Bygg ett delgivningsmått](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md))

### Dimensioner som stöds på ett annat sätt

Följande tidsbaserade dimensioner stöds. Datumutdata är dock inte standard när de här måtten används. År kompenseras med 1900 och månader är nollbaserade.

* År
* Kvartal
* Månad
* Vecka
* Dag
* Timme
* Minut
