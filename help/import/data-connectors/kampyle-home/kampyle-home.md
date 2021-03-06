---
description: Använd Kampyles dataanslutning med Adobe Analytics.
title: Kampyle Data Connector för Adobe Analytics
uuid: f7733c81-93f5-4c50-b83a-721a6fbd4e8e
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 5%

---


# Kampyle Data Connector för Adobe Analytics{#kampyle-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>Adobe Data Connector-tekniken upphör den 1 augusti 2021. [Läs mer …](/help/import/data-connectors/data-connectors-eol.md)

Kampyle Data Connector for Adobe Analytics kombinerar Kampyles integrerade feedbacksystem och beteenderapporteringen i Adobe Analytics® för att skapa kraftfulla analyser och optimeringsmöjligheter för er organisation.

Marknadsförare på webben inser i allt högre grad kundernas relevans när det gäller att bygga upp varumärken och få affärsresultat. Kampyle Data Connector for Adobe Analytics® ger Adobe Analytics feedback-statistik och dimensioner. Det gör att ni kan analysera besökarnas beteende i samband med deras attityder och åsikter. På så sätt kan du optimera baserat på feedback och förbättra konverteringsgraden.

## Krav för integrering{#integration-prerequisites}

Krav att tänka på innan du kan aktivera dataanslutningen.

### Krav för kunder i Adobe: {#section-d9c2e266931249e596de5f4406b5b6f0}

* Du måste vara Adobe Analytics kund.
* Du måste vara en administratörsanvändare.
* Du måste ha 1 tillgänglig och aktiverad eVar-variabel i rapportsviten.
* Du måste ha 3 tillgängliga och aktiverade anpassade händelser i rapportsviten (typ: räknare).

### Krav för Kampyle-kunder: {#section-4bbbca50e74d4f218414ae0cc535b8e9}

* Du måste vara kund hos Kampyle för webben.
* Du måste vara en Adobe Experience Cloud-administratörsanvändare med behörighet för att kunna aktivera dataanslutningar.
* Du måste kunna hämta Kampyle Private Key från gränssnittet för formulärhantering i Kampyle Feedback.

## Hämta Kampyle-privat nyckel{#retrieve-the-kampyle-private-key}

Steg för att hämta nyckeln i Kampyle-gränssnittet.

1. Logga in på ditt Kampyle-konto på [https://www.kampyle.com/login](https://www.kampyle.com/login).
1. Gå till **[!UICONTROL Feedback Form]** > **[!UICONTROL Feedback Form Customization]** i den vänstra navigeringen.

   ![](assets/retrieve_key1.png)

1. Hitta den privata nyckeln som visas i den nedre delen av rutan med huvudinnehåll.

   ![](assets/retrieve_key2.png)
