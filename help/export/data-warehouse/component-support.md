---
title: Komponentstöd i Data warehouse
description: Lär dig vilka ytterligare mått och mätvärden som finns i Data warehouse och vad som inte stöds.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 4%

---

# Komponentstöd i Data warehouse

data warehouse unika bearbetningsarkitektur tillåter vissa komponenter som vanligtvis inte är tillgängliga i andra funktioner i Adobe Analytics. På grund av sin unika arkitektur är vissa komponenter inte tillgängliga för användning i vare sig rapporter eller segment. Använd den här sidan för att förstå vad som kan användas och vad som inte kan användas.

## Komponenter som är unika för Data warehouse

Vissa mått och mätvärden kan användas i Data warehouse, men de är inte tillgängliga med andra funktioner i Adobe Analytics.

### Endast Dimensioner

* Experience Cloud-ID: För implementeringar som använder Experience Cloud ID Service (ECID), ett 128-bitars nummer som består av två sammanfogade 64-bitars nummer som fylls på med 19 siffror.
* Sidans URL: Sidans URL som träffen inträffade på.
* Inköps-ID: Unik identifierare för ett inköp, angiven med variabeln purchaseID.
* Besökar-ID: Anger besökarens unika identifierare. Detta värde är detsamma som sammanfogat värde för `visid_high` och `visid_low` kolumner i dataflöden. Se [Referens för datakolumn](../analytics-data-feed/c-df-contents/datafeeds-reference.md) under Dataflöden för mer information.

### Endast mått som stöds

* Besök: Detta mått i samband med Data warehouse utesluter icke-permanenta cookie-besök.
* Besök - alla besökare: Detta mätresultat i samband med Data warehouse ligger närmare varandra med besöksmätningen i andra verktyg i Adobe Analytics.

## Komponenter som inte stöds i Data warehouse

Vissa mått och mätvärden stöds inte i Data warehouse.

>[!NOTE]
>
>Om en dimension eller ett mätvärde inte stöds i Data warehouse stöds inte heller segment som använder dessa komponenter. Kontrollera alltid produktkompatibilitet när du skapar eller redigerar ett segment.

### Dimensioner som inte stöds

* Några tidsbaserade dimensioner, bland annat:
   * AM/PM
   * Dag i månaden
   * Veckodag
   * Dag på året
   * Timme på dagen
   * Minut
   * Månad på året
   * Kvartal på året
   * Veckodag/Veckoslut
   * År
* Några målningsbaserade dimensioner, bland annat:
   * Alla inmatningsdimensioner, utom inmatningssida
   * Alla avslutningsdimensioner, utom Avsluta sida och Avsluta länk
   * Träff-djup
   * Återbesöksfrekvens
   * Tid före händelse
   * Tid som använts på sidan - paketerad
   * Tid per besök - paketerad
   * Besöksdjup
* Alla söksidrankning
* Hierarkivariabler
* Träfftyp
* Sidor som inte hittats (tillgängliga som en dimension); stöds inte för segmentering)
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
