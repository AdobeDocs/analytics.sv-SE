---
title: Använda XDM-data med Analytics
description: Översikt över hur du använder XDM-data från Experience Platform i Adobe Analytics
feature: AEP Edge
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 2%

---

# Använda Adobe Experience Platform Edge-data med Analytics

Du kan använda [Adobe Experience Platform (AEP) Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) för att skicka data till Adobe Analytics. Detta fungerar genom att översätta [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) till ett format som används av Analytics.

Analytics samlar in XDM-data på två sätt:

* Automatisk mappning från XDM-scheman
* Manuell mappning till kontextdata

## Automatisk mappning

Automatisk mappning är beroende av ett standardvärde [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html) i XDM som automatiskt fyller i JSON-objekt som ingår i vanlig Analytics-datainsamling. Analysvariablerna som automatiskt mappas från XDM till dina konfigurerade rapportsviter kräver inte något utvecklarstöd för att införlivas. Se [Variabler mappas automatiskt i Analytics](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/automatically-mapped-vars.html) i användarhandboken för Platform Web SDK.

## Manuell mappning

[Manuell mappning av XDM-data till analyser](xdm-manual.md) använder [Kontextdata för analyser](../vars/page-vars/contextdata.md) variabler. Dessa variabler placeras i JSON-objekt som motsvarar tillämpliga scheman. Vanligtvis lägger ditt utvecklingsteam till kontextdata vid implementeringen och sedan anger administratörer [bearbetningsregler](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) för att tillämpa dessa data på angivna rapportsviter.

## Inställningar

Så här ställer du in Analytics för att ta emot XDM-data:

1. Installera och [konfigurera](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) den [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html).

2. Se till att rätt rapportsviter är mappade till de data du vill ha. XDM-data flödar automatiskt till rapportsviten från Adobe Experience-plattformen.
