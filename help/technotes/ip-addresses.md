---
title: IP-adresser och domäner som används av Adobe Analytics
description: Om brandväggen blockerar IP-adresser som kommer från Adobe kan du uppdatera brandväggsinställningarna i den här listan.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: ea859717c6a40b4eeeb9eca54b95718859af9c7b
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# IP-adresser och domäner som används av Adobe Analytics

Vissa brandväggskonfigurationer blockerar domäner som Adobe Analytics förlitar sig på för sitt produktgränssnitt. Du kan använda den här listan med domäner för att ändra organisationens nätverksinställningar och tillåta produktåtkomst inifrån organisationen.

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

{style="table-layout:auto"}

## Adobe Experience Cloud IP-adressblock

Förutom ovanstående domäner använder Adobe Analytics flera IP-adressblock för datainsamling och export av rapporter.

En fullständig lista över IP-intervall finns i Adobe Experience Cloud IP-adresser.

## IP-adresser för prestandaoptimering i Kina

Tilläggspaketet för prestandaoptimering i Kina är en extra betaltjänst som förbättrar AppMeasurementets datainsamling för besökare i Kina. Kontakta kontoteamet på Adobe om du vill veta mer om hur du använder den här funktionen.

>[!IMPORTANT]
>
>China RDC är inte tillgängligt för Web SDK-datainsamling. De här AppMeasurementen gäller endast för serverbibliotek.

Regionala datainsamlingsservrar i Kina använder följande IP-adresser:

| Plats | Värd |
| --- | --- |
| Kina | `52.80.168.159` |
| Kina | `52.80.199.104` |
| Kina | `54.223.199.8` |

{style="table-layout:auto"}
