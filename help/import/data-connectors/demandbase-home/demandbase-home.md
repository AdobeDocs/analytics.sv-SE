---
description: Använd Demandbase-dataanslutningen med Adobe Analytics.
title: Demandbase Data Connector för Adobe Analytics
uuid: 28fddb8f-06f6-4447-8257-4a59131bedbe
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 4%

---


# Demandbase Data Connector för Adobe Analytics{#demandbase-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>Adobe Data Connector-tekniken upphör den 1 augusti 2021. [Läs mer …](/help/import/data-connectors/data-connectors-eol.md)

Integrationen av Adobe® Data Connectors kombinerar Real-Time ID-tjänsten hos Demandbase med beteendeinformationen från Adobe Analytics för att skapa kraftfulla funktioner för analys, optimering och innehållspersonalisering för B2B-organisationer.

Leverera relevant innehåll till potentiella kunder baserat på förutbestämda egenskaper, leder till fler kvalificerade leads och ökad konvertering. Genom att leverera innehåll som är relevant för en viss bransch, företagsstorlek eller till och med för ett visst företag, kan ni skicka rätt budskap direkt till besökaren, utan att förlita er på att de hittar det på er webbplats. Detta kommer att leda till färre studsar och en friskare och mer kvalificerad konverteringstratt.

## Viktiga fördelar och funktioner{#key-benefits-and-features}

Listar de fem främsta fördelarna och funktionerna.

* Erbjuder trafik- och konverteringsrapportering på åtta standarddimensioner för Demandbase-organisationen som företagsnamn, bransch och intäktsintervall.
* Du kan inkludera ytterligare 8 valfria Demandbase-dimensioner. Dessa kan innehålla mått för kontobevakning.
* Innehåller användning av Demandbase-dimensioner för att bygga och tillämpa segment i hela Adobe Experience Cloud.
* Erbjudandena gäller optimering av vissa variabler. Alla 16 möjliga Demandbase-dimensioner kan fångas med endast två anpassade konverteringsvariabler (eVars).
* Gör att du kan skicka inbyggda Demandbase-dimensioner till Adobe Target för användning vid målgruppsanpassning till specifika målgrupper.

## Krav för integrering{#integration-prerequisites}

Demonstrerar viktiga förutsättningar för kunder som använder Adobe och Demandbase.

### Krav för Adobe-kunder {#section-ce8963ca1c1741009d842222c6a49063}

* Måste vara Adobe Analytics nuvarande kund.
* Måste vara en Adobe Experience Cloud-administratörsanvändare med behörighet att aktivera Data Connectors.
* Det måste finnas minst en tillgänglig och aktiverad variabel för eVar i rapportsviten. En andra eVar är valfri.

### Krav för kunder som använder Demandbase {#section-08e14afe216a4b0db9e7e2965894de6f}

* Måste vara en aktuell kund hos Demandbase.
* Måste ha en giltig Demandbase API-nyckel som är licensierad för Analytics.
* **Valfritt:** Måste ha en giltig API-nyckel för Demandbase som är licensierad för innehållspersonalisering. Detta krävs endast om du tänker aktivera de inbyggda Demandbase-dimensionerna i Adobe Target.
