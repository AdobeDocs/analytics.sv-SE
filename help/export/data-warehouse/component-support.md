---
title: Komponentstöd i datalagret
description: Lär dig vilka ytterligare mått och mätvärden som finns i datalagret och vad som inte stöds.
translation-type: tm+mt
source-git-commit: 00d4d59cb4c922b54a97ef7000e294ef3bf61f20

---


# Komponentstöd i datalagret

Data Warehouse unika bearbetningsarkitektur tillåter vissa komponenter som vanligtvis inte är tillgängliga i andra funktioner i Adobe Analytics. På grund av sin unika arkitektur är vissa komponenter inte tillgängliga för användning i vare sig rapporter eller segment. Använd den här sidan för att förstå vad som kan användas och vad som inte kan användas.

## Komponenter som är unika för datalagret

Vissa dimensioner och mätvärden kan användas i datalagret, medan de inte är tillgängliga med andra funktioner i Adobe Analytics.

### Endast dimensioner som stöds

* Experience Cloud-ID: För implementeringar som använder Experience Cloud ID Service (ECID) är ett 128-bitarsnummer bestående av två sammanfogade 64-bitarsnummer som fyllts i med 19 siffror.
* Sidans URL: Sidans URL som träffen inträffade på.
* Inköps-ID: Unik identifierare för ett inköp, angiven med variabeln purchaseID.
* Besökar-ID: Anger besökarens unika identifierare. Det här värdet är samma som sammanfogade värden för `visid_high` och `visid_low` kolumner i dataflöden. Mer information finns i [Datakolumnreferens](../analytics-data-feed/c-df-contents/datafeeds-reference.md) under Dataflöden.

### Endast mått som stöds

* Besök: Detta mått i samband med datalagret utesluter icke-beständiga cookie-besök.
* Besök - alla besökare: Detta mått i samband med datalagret är närmare paritet med besöksmätningen i andra verktyg i Adobe Analytics.

## Komponenter som inte stöds i datalagret

Vissa dimensioner och mått stöds inte i datalagret.

> [!NOTE] Om en dimension eller ett mått inte stöds i datalagret stöds inte heller segment som använder dessa komponenter. Kontrollera alltid produktkompatibilitet när du skapar eller redigerar ett segment.

### Dimensioner stöds inte

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
   * Returfrekvens
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
   * studsar
   * Poster
   * Avslutar
   * Läs in igen
   * Enkel åtkomst
   * Mätvärden för tidsåtgång
