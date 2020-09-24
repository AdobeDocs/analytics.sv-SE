---
title: Använda XDM-data med Analytics
description: 'Översikt över hur du använder XDM-data från Experience Platform i Adobe Analytics '
translation-type: tm+mt
source-git-commit: 0a570f52c3eb62ca517770fa12f2272f6ccc978d
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---


# Använda Adobe Experience Platform Edge-data med Analytics

Du kan använda [Adobe Experience Platform (AEP) Web SDK](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) för att skicka data till Adobe Analytics. Detta fungerar genom att översätta [Experience Data Model (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) till ett format som används av Analytics.

Analytics samlar in XDM-data på två sätt:

* Automatisk mappning från XDM-scheman
* Manuell mappning till kontextdata

## Automatisk mappning

[Automatisk mappning](xdm-manual.md) är beroende av ett [standardschema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) i XDM som automatiskt fyller i JSON-objekt som ingår i vanlig Analytics-datainsamling. Analysvariablerna som automatiskt mappas från XDM till dina konfigurerade rapportsviter kräver inte något utvecklarstöd för att införlivas.

## Manuell mappning

Manuell mappning av XDM-data till Analytics bygger på [kontextdatavariabler](../vars/page-vars/contextdata.md) i Analytics. Dessa variabler placeras i JSON-objekt som motsvarar tillämpliga scheman. Vanligtvis lägger ditt utvecklingsteam till kontextdata vid implementeringen och sedan anger administratörer [bearbetningsregler](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) för att tillämpa dessa data på angivna rapportsviter.

## Inställningar

Så här ställer du in Analytics för att ta emot XDM-data:

1. Installera och [konfigurera](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) [Adobe Experience Platform Web SDK](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html).

2. Se till att rätt rapportsviter är mappade till de data du vill ha. XDM-data flödar automatiskt till rapportsviten från Adobe Experience-plattformen.
