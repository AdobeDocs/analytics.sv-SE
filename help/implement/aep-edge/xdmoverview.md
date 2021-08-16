---
title: Använda XDM-data med Analytics
description: Översikt över hur du använder XDM-data från Experience Platform i Adobe Analytics
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
source-git-commit: 501b64c7704c234b21a5ccb428883bc6fcaf166a
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---

# Använda Adobe Experience Platform Edge-data med Analytics

Du kan använda [Adobe Experience Platform (AEP) Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) för att skicka data till Adobe Analytics. Detta fungerar genom att översätta [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) till ett format som används av Analytics.

Analytics samlar in XDM-data på två sätt:

* Automatisk mappning från XDM-scheman
* Manuell mappning till kontextdata

## Automatisk mappning

Automatisk mappning är beroende av ett [standardschema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html) i XDM som automatiskt fyller i JSON-objekt som ingår i vanlig Analytics-datainsamling. Analysvariablerna som automatiskt mappas från XDM till dina konfigurerade rapportsviter kräver inte något utvecklarstöd för att införlivas.

## Manuell mappning

[Manuell mappning av XDM-data till ](xdm-manual.md) Analytics bygger på  [DataVariables för ](../vars/page-vars/contextdata.md) Analytics-kontext. Dessa variabler placeras i JSON-objekt som motsvarar tillämpliga scheman. Vanligtvis lägger ditt utvecklingsteam till kontextdata vid implementeringen och sedan anger administratörer [bearbetningsregler](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) för att använda dessa data i angivna rapportsviter.

## Inställningar

Så här ställer du in Analytics för att ta emot XDM-data:

1. Installera och [konfigurera ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html).

2. Se till att rätt rapportsviter är mappade till de data du vill ha. XDM-data flödar automatiskt till rapportsviten från Adobe Experience-plattformen.
