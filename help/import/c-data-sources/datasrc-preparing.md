---
description: Steg som du kan vidta för att förbereda för att använda datakällor
subtopic: Data sources
title: Förbereda för att använda Data Sources
topic-fix: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
exl-id: 3cad7c33-f31c-41a2-9dd2-9535713c7620
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 5%

---

# Förbered användning av datakällor

Steg som du kan vidta för att förbereda för att använda datakällor

* [Identifiera och namnge måtten](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [Identifiera Dimensionerna](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [Kampanjspårningskod](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [Transaktions-ID](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [Identifiera ett giltigt datumintervall för datakälldata](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## Identifiera och namnge måtten {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

Det är viktigt att förstå mätvärden eller mått som finns i datakällorna, till exempel *`Off-line Sales Revenue by Product`*, *`Returns by Product`* eller *`Ad Impressions by Campaign`*. Det här är namnen som du kan associera med rapportvärden (händelser, props och eVars).

När du har fastställt lämpliga metrisk-till-händelse-mappningar för Data Sources-data ändrar du namn på händelserna med beskrivande namn som passar för det associerade datakällmåttet.

Se [Slutförda händelser](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) i hjälpen för Admin Tools.

>[!NOTE]
>
>Adobe rekommenderar starkt att du använder nya, tomma händelser med data från datakällor, men i sällsynta fall kan det vara bra att använda en befintlig händelse.

## Identifiera Dimensionerna {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

Identifiera och samla in de data (rapporter) som du vill använda för att dela upp de värden som importeras via datakällor. Dessa data kallas *`data dimensions`*.

Om en datakälla till exempel mäter och avtryck av data, är det troligt att din datamängd är kampanjspårningskoden. Om du mäter offlineförsäljning kanske du vill använda produktkoden (eller SKU) som datamängd.

Du kan definiera flera datamått för ett mätvärde, men varje mätvärde måste ange ett relevant värde, eller en kombination av värden, för varje tillhörande datamängd. Om du till exempel importerar ett offlineförsäljningsmått och associerar det med datamätningarna *`Product`* och *`Partner`* måste offlineförsäljningsmåttet vara relevant för varje kombination av produkt och partner (till exempel Total Intäkter).

>[!NOTE]
>
>Det går att importera summerade mått som inte kan delas upp efter någon datamängd.

När du har definierat de datamängder som ska användas med en datakälla integrerar du dimensionsdata i marknadsföringsrapporter genom att mappa dem till en variabel. Använd antingen standardrapporter (till exempel Produkt, Spårningskod, Söknyckelord) eller Konverteringstrafikvariabler (eVars).

När du använder eVars kan du använda befintliga eVars eller nya eVars som datamått. När du har valt en eVar som ska ta emot en datamängd från datakällor måste du namnge dem korrekt.

Se [Success Events](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) i Analytics-hjälpen.

## Kampanjspårningskod {#section_468222796FF449ABAA90D88EB3264CB1}

Förutom att importera lyckade händelser kan du även importera associerade eVar. Om du till exempel spårar onlineaktivitet med en kampanjspårningskod och har kampanjspårningskoder för offlinemätningarna, kan du importera mätvärdena med kampanjspårningskoder. Med den här metoden kan ni visa både online- och offlinemätningar i Campaign-rapporter.

Om du inte importerar datakällemått med ett associerat eVar-värde kan du inte visa datakällmått uppdelade efter eVars. I stället kan du bara se Total-mått.

## Transaktions-ID {#section_D9513C1204B7496C9B738C5B12CCCFC7}

Transaktions-ID:t används för att ansluta en online-händelse till en offline-händelse.

## Identifiera ett giltigt datumintervall för datakälldata {#section_03AAB1291BDC4403BDC50905A78FDB71}

När du har definierat datakällstatistik (anpassade händelser) och datamått (eVars) granskar du datumintervallet för de data i datakällan som du vill importera. Du kan inte importera datakällor som ligger utanför intervallet för dina befintliga rapportdata.

Du kan till exempel inte importera datakälldata från innan du har implementerat onlinedatespårning. Data för datakällor ska delas upp per dag.
