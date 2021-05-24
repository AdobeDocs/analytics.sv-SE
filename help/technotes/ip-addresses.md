---
title: IP-adresser och domäner som används av Adobe Analytics
description: Om brandväggen blockerar IP-adresser som kommer från Adobe kan du uppdatera brandväggsinställningarna i den här listan.
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 4460850971fe822ff8a0ebf3e3269d0e573fa1db
workflow-type: tm+mt
source-wordcount: '408'
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
| Adobe Analytics domäner | `adobe.com`, `adobe.net`, `adobe.io` |
| Adobe Analytics äldre domän | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com` |
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

Adobe Analytics använder Amazon Web Services som en del av datainsamlingsprocessen. Följande tabell innehåller AWS-värdar som är reserverade för Adobe. Dessa värdar **ingår inte** i det aggregerade blockintervallet ovan.

| Plats | Värd |
| --- | --- |
| Australien | `13.54.219.183` |
| Australien | `52.62.137.88` |
| Australien | `54.79.162.112` |
| Kina | `52.81.111.133` |
| Kina | `140.179.22.22` |
| Frankrike | `13.36.218.177` |
| Frankrike | `15.188.95.229` |
| Frankrike | `15.236.176.210` |
| Indien | `65.0.114.116` |
| Indien | `65.0.115.179` |
| Indien | `65.0.25.111` |
| Indien | `13.233.180.137` |
| Indien | `65.0.111.130` |
| Indien | `52.66.172.181` |
| Irland | `18.202.158.78` |
| Irland | `54.72.205.114` |
| Irland | `54.78.36.71` |
| Irland | `54.220.133.225` |
| Irland | `54.74.170.177` |
| Irland | `54.195.254.128` |
| Oregon | `44.233.255.254` |
| Oregon | `44.237.54.118` |
| Oregon | `44.238.157.95` |
| Oregon | `54.212.155.93` |
| Oregon | `52.10.149.115` |
| Oregon | `52.40.172.46` |
| Singapore | `52.220.116.94` |
| Singapore | `52.76.68.91` |
| Singapore | `54.179.114.68` |
| Singapore | `54.255.88.178` |
| Singapore | `52.220.235.10` |
| Singapore | `3.1.237.132` |
| Tokyo | `18.182.161.178` |
| Tokyo | `54.168.58.167` |
| Tokyo | `54.178.61.109` |
| Tokyo | `3.113.78.189` |
| Tokyo | `13.115.137.161` |
| Tokyo | `54.178.162.114` |
| Virginia | `3.213.168.181` |
| Virginia | `3.219.249.186` |
| Virginia | `3.220.129.153` |
| Virginia | `18.206.109.10` |
| Virginia | `18.211.197.67` |
| Virginia | `34.227.41.189` |
| Virginia | `34.228.124.176` |
| Virginia | `54.90.190.103` |
| Virginia | `54.174.149.161` |
