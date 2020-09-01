---
title: IP-adresser och domäner som används av Adobe Analytics
description: Om brandväggen blockerar IP-adresser som kommer från Adobe kan du uppdatera brandväggsinställningarna i den här listan.
translation-type: tm+mt
source-git-commit: 4faa557120f937eb240e6d12ab0e2fc0ae7372ab
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---


# IP-adresser och domäner som används av Adobe Analytics

Vissa brandväggskonfigurationer blockerar IP-adresser som kommer från Adobe datainsamlingsservrar eller servrar som är ansvariga för dataåtkomst. Du kan använda den här listan med intervall för att ändra organisationens brandväggsinställningar så att åtkomst tillåts och data skickas inifrån organisationen.

>[!IMPORTANT]
>
>Även om Adobe gör sitt bästa för att hålla det här dokumentet aktuellt kan det inte garantera att listan med IP-intervall är densamma. Möjliga förändringar är bland annat tillväxt och expansion av verksamheten, ett internetregister kräver ändringar av Adobe IP-adressutrymme eller att en Internetleverantör slutar fungera.

## Tillåt beroende teknikdomäner

Adobe Analytics använder följande värdar för att förbättra prestanda och produktupplevelse. Adobe rekommenderar att du lägger till dessa domäner i tillåtelselista i din brandvägg för att få en optimal upplevelse med Adobe Analytics.

| Teknik | Domän |
| --- | --- |
| Adobe Analytics-domän | `adobe.com` |
| Adobe Analytics äldre domän | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com` |
| LaunchMörkt | `app.launchdarkly.com` |
| Microsoft Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft Azure CDN | `aauicdnva7.azureedge.net` |

## Alla Adobe Analytics IP-adressblock

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

Om din organisation föredrar att tillåta specifika IP-adressintervall kan du använda följande tabell. Alla intervall i det här avsnittet ingår i tabellen ovan.

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
| Virginia | Se AWS-värdar |

## AWS-värdar

Adobe Analytics använder Amazon Web Services som en del av datainsamlingsprocessen. Följande tabell innehåller AWS-värdar som är reserverade för Adobe. Dessa värdar ingår **inte** i det aggregerade blockintervallet ovan.

| Plats | Värd |
| --- | --- |
| Australien | `13.238.77.77` |
| Australien | `52.62.21.192` |
| Australien | `54.66.152.159` |
| Japan | `15.188.154.177` |
| Irland | `15.236.175.233` |
| Japan | `15.236.9.100` |
| Indien | `13.232.177.101` |
| Indien | `13.235.4.163` |
| Indien | `3.6.119.69` |
| Irland | `52.17.94.37` |
| Irland | `52.49.253.16` |
| Irland | `52.51.63.15` |
| London | `172.82.228.19` |
| Oregon | `52.42.60.49` |
| Oregon | `54.212.169.56` |
| Oregon | `54.214.170.191` |
| Singapore | `13.228.34.224` |
| Singapore | `18.136.20.161` |
| Singapore | `52.74.162.152` |
| Tokyo | `13.112.72.86` |
| Tokyo | `18.178.74.225` |
| Tokyo | `18.179.88.228` |
| Virginia | `34.234.106.101` |
| Virginia | `52.22.231.198` |
| Virginia | `54.157.65.136` |
| Virginia | `107.23.142.4` |
| Virginia | `34.192.14.184` |
| Virginia | `34.192.146.173` |
| Virginia | `34.192.229.76` |
| Virginia | `34.196.183.216` |
| Virginia | `34.196.219.120` |
| Virginia | `34.196.54.55` |
| Virginia | `34.197.179.21` |
| Virginia | `34.197.45.49` |
| Virginia | `34.197.93.163` |
| Virginia | `34.198.80.27` |
| Virginia | `34.199.102.192` |
| Virginia | `34.199.46.40` |
| Virginia | `34.199.99.62` |
| Virginia | `34.200.67.35` |
| Virginia | `34.204.146.235` |
| Virginia | `34.204.164.1` |
| Virginia | `34.204.27.249` |
| Virginia | `34.205.224.111` |
| Virginia | `34.206.69.71` |
| Virginia | `52.193.88.44` |
| Virginia | `52.200.108.250` |
| Virginia | `52.200.171.156` |
| Virginia | `52.201.49.195` |
| Virginia | `52.205.244.105` |
| Virginia | `52.207.161.156` |
| Virginia | `52.22.148.55` |
| Virginia | `52.4.155.255` |
| Virginia | `52.72.182.205` |
| Virginia | `52.72.185.111` |
| Virginia | `54.152.218.194` |
| Virginia | `54.173.37.66` |
| Virginia | `54.173.69.38` |
| Virginia | `54.236.180.248` |
| Virginia | `54.236.71.218` |
| Virginia | `54.80.103.29` |
| Virginia | `54.88.180.124` |
