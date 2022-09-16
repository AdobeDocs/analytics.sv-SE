---
title: IP-adresser och domäner som används av Adobe Analytics
description: Om brandväggen blockerar IP-adresser som kommer från Adobe kan du uppdatera brandväggsinställningarna i den här listan.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: be8e4c3a25dccaf7bd591f487e1131288ba26f2a
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 0%

---

# IP-adresser och domäner som används av Adobe Analytics

Vissa brandväggskonfigurationer blockerar IP-adresser som kommer från Adobe datainsamlingsservrar eller servrar som är ansvariga för dataåtkomst. Du kan använda den här listan med intervall för att ändra organisationens brandväggsinställningar så att åtkomst tillåts och data skickas inifrån organisationen. Den här sidan innehåller både inkommande system (till exempel datainsamling) och utgående system (till exempel dataflöden) som Adobe använder.

>[!IMPORTANT]
>
>Även om Adobe gör sitt bästa för att hålla det här dokumentet aktuellt kan det inte garantera att listan med IP-intervall är densamma. Möjliga förändringar är bland annat tillväxt och expansion av verksamheten, ett internetregister kräver ändringar av Adobe IP-adressutrymme eller att en Internetleverantör slutar fungera.

## Tillåt beroende teknikdomäner

Adobe Analytics använder följande värdar för att förbättra prestanda och produktupplevelse. Adobe rekommenderar att du tillåter dessa domäner genom organisationens brandvägg för att få en optimal upplevelse med Adobe Analytics.

| Teknik | Domän |
| --- | --- |
| Adobe Analytics domäner | `adobe.com`, `adobe.net`, `adobe.io` |
| Adobe Analytics äldre domän | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchMörkt | `app.launchdarkly.com` |
| Microsoft Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft Azure CDN | `aauicdnva7.azureedge.net` |

## Alla IP-adressblock för Adobe Analytics Data Collection

Följande tabell omfattar alla standardservrar för datainsamling och regionala datainsamlingsservrar för Adobe Analytics. De omfattar inte enskilda AWS-värdar.

| IP-block (CIDR-notering) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |

## Datainsamling och IP-adressblock för FTP

Om din organisation föredrar att tillåta specifika IP-adressintervall kan du använda följande tabell. Alla intervall i det här avsnittet ingår i tabellen ovan. FTP-anslutningar för Data warehouse och datafeeds kommer endast från platserna London, Oregon och Singapore.

| Plats | IP-intervall (CIDR-notering) |
| --- | --- |
| Australien | `63.140.55.0/24` |
| Australien | `63.140.56.0/23` |
| Kalifornien | `63.140.32.0/23` |
| Kalifornien | `63.140.34.0/24` |
| Indien | `66.117.20.0/24` |
| Indien | `66.117.22.0/23` |
| Japan | `130.248.130.0/23` |
| Japan | `130.248.169.0/23` |
| Japan | `63.140.50.0/23` |
| Japan | `66.117.31.0/24` |
| London | `66.235.156.0/24` |
| Oregon | `66.235.132.0/22` |
| Singapore | `130.248.170.0/23` |
| Singapore | `130.248.240.0/24` |
| Singapore | `63.140.44.0/22` |
| Singapore | `63.140.48.0/23` |
| Singapore | `66.117.30.0/24` |
| Virginia | `63.140.38.0/23` |
| Virginia | `63.140.54.0/24` |

## AWS-värdar

Adobe Analytics använder Amazon Web Services som en del av sin datainsamlingsprocess. Följande tabell innehåller AWS IPv4-värdadresser som är reserverade för Adobe. Värdarna är **not** ingår i det aggregerade blockområdet ovan.

| Plats | Värd |
| --- | --- |
| Kina | `52.80.83.220` |
| Kina | `71.132.16.253` |
| Frankrike | `13.36.218.177` |
| Frankrike | `15.188.95.229` |
| Frankrike | `15.236.176.210` |
| Irland | `54.74.170.177` |
| Irland | `54.195.254.128` |
| Irland | `54.220.133.225` |
| Oregon | `52.10.149.115` |
| Oregon | `52.40.172.46` |
| Oregon | `54.212.155.93` |
| Virginia | `3.216.131.23` |
| Virginia | `34.204.237.47` |
| Virginia | `54.163.234.74` |

Följande tabell innehåller AWS IPv6-adressblock som används av Adobe. Värdarna är **not** ingår i det aggregerade blockområdet ovan.

| Plats | Värd |
| --- | --- |
| Australien | `2406:da1c:406:1a00::/56` |
| Australien | `2406:da1c:ce5:b400::/56` |
| Kalifornien | `2600:1f1c:366:d900::/56` |
| Indien | `2406:da1a:f34:6a00::/56` |
| Irland | `2a05:d018:309:600::/56` |
| Japan | `2406:da14:b07:ab00::/56` |
| Oregon | `2600:1f14:1eb:7d00::/56` |
| Oregon | `2600:1f14:9d3:2b00::/56` |
| Singapore | `2406:da18:6e8:1e00::/56` |
| Virginia | `2600:1f18:1a20:e800::/56` |
| Virginia | `2600:1f18:4fd:6000::/56` |
| Virginia | `2600:1f18:b00:e100::/56` |
| Virginia | `2600:1f18:d1f:bd00::/56` |
