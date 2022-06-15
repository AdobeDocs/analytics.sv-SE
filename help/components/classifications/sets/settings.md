---
title: Inställningar för klassificeringsuppsättning
description: Skapa eller redigera en klassificeringsuppsättning.
source-git-commit: c9465ea0524225494aa5067d00ca5e7aba4bca92
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---


# Inställningar för klassificeringsuppsättning

Konfigurera en klassificeringsuppsättning, överföra data eller hämta data.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Klicka på önskat namn på klassificeringsuppsättningen

När du redigerar en klassificeringsuppsättning finns det två flikar: **[!UICONTROL Schema]** och **[!UICONTROL Settings]**.

## Inställningar

Följande fält är tillgängliga i [!UICONTROL Settings] och kan redigeras:

* **[!UICONTROL Name]**: Klassificeringsuppsättningens namn.
* **[!UICONTROL Description]**: Beskrivning av klassificeringsuppsättningen.
* **[!UICONTROL Owner name]**: Ägarens namn.
* **[!UICONTROL Owner email]**: Ägarens e-postadress.
* **[!UICONTROL Notify of issues]**: En kommaavgränsad lista med e-postadresser som meddelas om problem med den här klassificeringsuppsättningen.
* **[!UICONTROL Tags]**: Lägg till en eller flera taggar i de markerade klassificeringsuppsättningarna, som gör det enklare att hitta dem i framtiden genom att ordna eller gruppera klassificeringsuppsättningar.

Ytterligare fält är tillgängliga i informationssyfte och kan inte redigeras:

* **[!UICONTROL Type]**: Typ av klassificering mellan [!UICONTROL Primary] och [!UICONTROL Lookup]. Primära klassificeringar används vanligtvis.
* **[!UICONTROL Subscriptions]**: Rapportsviten och variabeln som klassificeringsuppsättningen gäller för. För närvarande stöds endast en Report Suite för en viss klassificeringsuppsättning. stöd för flera rapportsviter planeras.

## Schema

Visa aktuella konfigurerade klassificeringsdimensioner för den här prenumerationen. Följande knappar är tillgängliga:

* **[!UICONTROL Upload]**: Överför klassificeringsdata manuellt för en eller flera klassificeringsdimensioner. JSON-, CSV-, TSV- och TAB-filer stöds. När du överför en giltig fil visas en tabellförhandsvisning av data som ska klassificeras.
   * **[!UICONTROL File encoding]**: Välj rätt filkodning i den här listrutan. Giltiga alternativ är [!UICONTROL UTF-8] och [!UICONTROL Latin1].
   * **[!UICONTROL List delimiter]**: Välj rätt listavgränsare. Om du använder en hämtad fil eller mallfil måste du kontrollera att [!UICONTROL List delimiter] här matchar [!UICONTROL List delimiter] när filen hämtades.
   * **[!UICONTROL Apply]**: Spara överförda klassificeringsdata i klassificeringsuppsättningen.
