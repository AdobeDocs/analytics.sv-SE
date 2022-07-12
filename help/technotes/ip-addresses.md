---
title: IP-adresser och domäner som används av Adobe Analytics
description: Om brandväggen blockerar IP-adresser som kommer från Adobe kan du uppdatera brandväggsinställningarna i den här listan.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 6788b904295fd92642d27ade65a31d61897069a3
workflow-type: tm+mt
source-wordcount: '408'
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
| `172.82.192.0/18` |
| `185.34.188.0/22` |
| `192.243.224.0/19` |
| `205.219.231.0/24` |
| `208.67.40.0/22` |
| `208.77.136.0/22` |

## Datainsamling och IP-adressblock för FTP

Om din organisation föredrar att tillåta specifika IP-adressintervall kan du använda följande tabell. Alla intervall i det här avsnittet ingår i tabellen ovan. FTP-anslutningar för Data warehouse och datafeeds kommer endast från platserna London, Oregon och Singapore.

| Plats | IP-intervall (CIDR-notering) |
| --- | --- |
| Amsterdam | `66.117.28.0/23` |
| Dallas | `205.219.231.0/24` |
| Dallas | `66.235.152.0/22` |
| Dallas | `66.235.140.0/22` |
| Dallas | `63.140.32.0/21` |
| Dallas | `172.82.208.0/22` |
| Hongkong SAR of China | `66.117.24.0/22` |
| London | `66.235.156.0/24` |
| London | `66.235.148.0/23` |
| London | `63.140.40.0/22` |
| London | `208.67.41.0/24` |
| London | `192.243.254.0/23` |
| London | `192.243.244.0/22` |
| London | `185.34.188.0/23` |
| London | `130.248.152.0/21` |
| London | `172.82.224.0/21` |
| London | `172.82.232.0/21` |
| Oregon | `192.243.240.0/22` |
| Oregon | `192.243.232.0/21` |
| Oregon | `192.243.224.0/21` |
| Oregon | `130.248.160.0/21` |
| Oregon | `130.248.148.0/22` |
| Oregon | `172.82.192.0/21` |
| Oregon | `172.82.216.0/21` |
| Paris | `208.67.40.0/24` |
| Singapore | `66.235.150.0/24` |
| Singapore | `66.235.130.0/23` |
| Singapore | `63.140.44.0/22` |
| Singapore | `208.67.43.0/24` |
| Singapore | `172.82.240.0/22` |
| Singapore | `172.82.246.0/23` |
| Singapore | `172.82.248.0/21` |
| San Jose | `66.117.20.0/24` |
| San Jose | `66.235.132.0/22` |
| San Jose | `130.248.128.0/22` |
| San Jose | `192.243.248.0/23` |
| San Jose | `172.82.200.0/22` |
| San Jose | `66.235.136.0/22` |
| San Jose | `208.91.175.0/24` |
| San Jose | `208.91.174.0/24` |
| San Jose | `208.91.169.0/24` |
| Sydney | `216.104.216.0/23` |
| Tokyo | `66.235.159.0/24` |
| Tokyo | `66.117.21.0/24` |
| Tokyo | `63.140.52.0/24` |
| Tokyo | `63.140.50.0/23` |
| Virginia | `66.235.144.0/22` |
| Virginia | `208.77.138.0/23` |
| Virginia | `208.77.136.0/23` |
| Virginia | `192.243.250.0/23` |
| Virginia | `130.248.144.0/22` |
| Virginia | `172.82.204.0/22` |
| Virginia | `172.82.212.0/22` |

## AWS-värdar

Adobe Analytics använder Amazon Web Services som en del av sin datainsamlingsprocess. Följande tabell innehåller AWS-värdar som är reserverade för Adobe. Värdarna är **not** ingår i det aggregerade blockområdet ovan.

| Plats | Värd |
| --- | --- |
| Kina | `140.179.89.228` |
| Kina | `140.179.125.98` |
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
