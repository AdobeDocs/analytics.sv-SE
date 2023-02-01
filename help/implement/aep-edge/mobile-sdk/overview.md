---
title: Implementera Adobe Analytics med Adobe Experience Platform Mobile SDK
description: Använd SDK-tillägget för mobiler i Adobe Experience Platform Data Collection för att skicka data till Adobe Analytics.
source-git-commit: e6b40881a543b43c03b612c7e7b0d9bd09f44c0d
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# Implementera Adobe Analytics med Adobe Experience Platform Mobile SDK

Adobe Experience Platform Mobile SDK hjälper er att driva lösningar och tjänster från Adobe Experience Cloud i era mobilappar. Det finns för Android™, iOS och olika plattformsoberoende utvecklingsramverk. Konfigurationen hanteras med Adobe Experience Platform Data Collection.
>[!IMPORTANT]
>
>Ett Adobe Analytics-tillägg finns också i Adobe Experience Platform Data Collection. Om du installerar det här tillägget kan du inte utnyttja XDM eller Edge Network.

## Adobe Experience Platform SDK

Översikt över implementeringsuppgifterna:

![Adobe Analytics med hjälp av arbetsflödet för Analytics-tillägget](../../assets/mobilesdk-annotated.png)

|<div style="width:20px"></div>| Aktivitet | Mer information | |-| —|—| | 1 | Kontrollera att du har **har definierat en rapportserie**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Konfigurera scheman och datauppsättningar**. För att standardisera datainsamlingen för användning i olika program som utnyttjar Adobe Experience Platform har Adobe skapat den öppna och offentligt dokumenterade standarden Experience Data Model (XDM). | [Konfigurera scheman och datauppsättningar](https://developer.adobe.com/client-sdks/documentation/getting-started/set-up-schemas-and-datasets/) | | 3 | **Konfigurera ett datastream**. En datastream representerar konfigurationen på serversidan när Adobe Experience Platform Web SDK implementeras. | [Konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 4 | **Lägg till en Adobe Analytics-tjänst** till din datastream. Tjänsten styr om och hur data skickas till Adobe Analytics. | [Lägg till Adobe Analytics-tjänst i ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 5 | **Skapa en mobil egenskap**. En egenskap är en behållare som du fyller med tillägg, regler, dataelement och bibliotek. | [Konfigurera en mobil egenskap](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 6 | **Installera Adobe Experience Platform Edge Network-tillägget** i egenskapen mobile tag och konfigurera datastream i tillägget. | [Adobe Experience Platform Edge Network](https://developer.adobe.com/client-sdks/documentation/edge-network/) | | 7 | **Använd kod i din app** om du vill registrera nödvändiga tillägg och läsa in din taggkonfiguration. | [Konfigurera konfigurationen](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 8 | **Implementera och testa funktioner** med en kombination av taggens dataelement, regler, ytterligare tillägg och SDK API-anrop i din app. Inspect, validera och felsök datainsamling och upplevelser för er mobilapplikation. | [Använda exempelprogrammet](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 9 | **Utöka och validera er mobilappsimplementering** innan det går till produktion. | |


## Adobe Analytics-tillägg.

Översikt över implementeringsuppgifterna:

![Adobe Analytics med hjälp av arbetsflödet för Analytics-tillägget](../../assets/mobilesdk-analytics-annotated.png)

|<div style="width:20px"></div> | Aktivitet | Mer information | |-| —|—| | 1 | Kontrollera att du har **har definierat en rapportserie**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Skapa en mobil egenskap**. En egenskap är en behållare som du fyller med tillägg, regler, dataelement och bibliotek. | [Konfigurera en mobil egenskap](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 3 | **Installera Adobe Analytics-tillägget** i egenskapen mobile tag och konfigurera tillägget så att det pekar på rapportsviten. | [Adobe Analytics-tillägg för mobil egendom](https://developer.adobe.com/client-sdks/documentation/adobe-analytics/) | | 4 | **Använd kod i din app** om du vill registrera nödvändiga tillägg och läsa in din taggkonfiguration. | [Konfigurera konfigurationen](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 5 | **Implementera och testa funktioner** med en kombination av taggens dataelement, regler, ytterligare tillägg och SDK API-anrop i din app. Inspect, validera och felsök datainsamling och upplevelser för er mobilapplikation. | [Använda exempelprogrammet](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 6 | **Utöka och validera er mobilappsimplementering** innan det går till produktion. | |

## Ytterligare resurser

- [Dokumentation för taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#)

- [Mobile SDK-dokumentation](https://developer.adobe.com/client-sdks/documentation/)



