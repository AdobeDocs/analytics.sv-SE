---
description: Lär dig hur du aktiverar Adobe Campaign-rapportering i Adobe Analytics
title: Hur integrerar jag Adobe Campaign Reporting i Adobe Analytics?
feature: Campaign Integration
exl-id: 63bae5ee-f94d-43fa-87ce-6380236745d6
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 95%

---

# Adobe Campaign-rapportering

Mer information om hur du konfigurerar den här integreringen finns i [dokumentationen för Adobe Campaign](https://helpx.adobe.com/se/campaign/standard/integrating/using/about-campaign-analytics-integration.html).

Integrationen mellan Adobe Analytics och Adobe Campaign

* Här kan du dela dina KPI-data (Key Performance Indicator) från Adobe Campaign Standard till Adobe Analytics.
* Förbättrar spårningsformler med Adobe Analytics-parametrar.
* Lägger till en ny rapport under **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** > **[!UICONTROL Adobe Campaign.]**
* Lägger till fem nya Adobe Campaign-klassificeringar.
* Lägger till tio nya Adobe Campaign-mätvärden.
* Lägger till sex nya Adobe Campaign-dimensioner.
* Synkroniserar data med Analytics var 15:e minut.

## Steg 1. Aktivera Adobe Campaign-rapportering {#section_C685EF10505045708A6536BB13F6CD58}

För att kunna visa Campaign-data i Analytics måste du först aktivera Campaign-rapportering.

1. Navigera till  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **`<select report suite>`** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Adobe Campaign Reporting]**.
1. Klicka på **[!UICONTROL Enable Campaign Reporting]**.

   ![](assets/enable-campaign.png)

## Steg 2. Visa Adobe Campaign-rapporter {#section_9C18A29F3CC54BD4AC5EA96417F17B33}

Integrationen mellan Adobe Campaign Standard och Adobe Analytics ger följande rapport under **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**

| Rapport | Definition |
|--- |--- |
| Adobe Campaign Executed Delivery ID | Visar data som importerats från Adobe Campaign om e-postmeddelanden som skickats från Adobe Campaign. |

## Steg 3. Använd Adobe Campaign-klassificeringar {#section_74A28AF3F4CA4091943789DE4D8B2B63}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **`<select report suite>`** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Adobe Campaign Classifications]**

När rapportsviten har aktiverats för Adobe Campaign finns följande klassificeringar:

* Leverans-ID (internt leveransnamn som visas i Campaign)
* Leveransetikett (Leverans i kampanj - Individuell leverans/Återkommande leverans/Transaktionsleverans)
* Kampanj-ID (internt kampanjnamn som du ser i Campaign)
* Kampanjetikett (Campaign i Adobe Campaign)
* Etikett för utförd leverans (lista över enskilda utförda leveranser)

## Adobe Campaign-dimensioner och mätvärden som är tillgängliga i Adobe Analytics {#section_F33385C9660644AF84172EC39601469B}

Följande **mätvärden** är tillgängliga från Campaign i Adobe Analytics-rapportsviter:

* Adobe Campaign - skickat
* Adobe Campaign - öppnat
* Adobe Campaign - klickat
* Adobe Campaign - bearbetat
* Adobe Campaign - levererat
* Adobe Campaign - unikt öppnat
* Adobe Campaign - unikt klickat
* Adobe Campaign - avbeställt
* Adobe Campaign - totala avhopp
* Instanser för leverans-ID som körts i Adobe Campaign

Följande **dimensioner** är tillgängliga från Campaign i rapportsviterna för Adobe Analytics:

| Dimensionsnamn | Definition |
|--- |--- |
| Kampanj-ID | ID för alla kampanjer för vilka KPI har skickats under varaktigheten. |
| Kampanjetikett | Etiketter för kampanj-ID:n |
| Leverans-ID | ID för alla leveranser för vilka KPI har skickats under varaktigheten. Innehåller även ID:n för huvudleveranser av återkommande leveranser och transaktionsleveranser. Exempel: En DM1 med återkommande leverans schemalades och DM2, DM3, DM4 och DM5 var underordnade leveranser för den återkommande leveransen.  Leverans-ID:t visar resultat för alla leveranser, DM1 till DM5. |
| Leveransetikett | Etiketter för leverans-ID |
| Utfört leverans-ID | ID:n för endast utförda leveranser. Inget ID för återkommande/transaktionell huvudleverans. Exempel: En DM1 med återkommande leverans schemalades och DM2, DM3, DM4 och DM5 var underordnade leveranser för den återkommande leveransen. Utfört leverans-ID visar resultat för alla leveranser från DM2 till DM5 - de leveranser som faktiskt har utförts. |
| Etikett för utförd leverans | Etiketter för utförda leverans-ID:n |
