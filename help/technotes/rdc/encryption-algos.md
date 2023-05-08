---
title: HTTPS-krypteringsalgoritmer som stöds
description: Säkerhetsinställningar och certifikattyper för TLS-chiffrering.
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
source-git-commit: 1ca7f750387fd9ae034d10ebf3e47190cf33d4b7
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---

# HTTPS-krypteringsalgoritmer som stöds

## Cipher Security Levels

Adobe erbjuder två krypteringsnivåer för att uppfylla olika kundbehov när det gäller säkerhet vid datainsamling från första part. Dessa nivåer avgör vilka krypteringsalgoritmer som stöds för HTTPS-anslutningar med Adobe-servrar. Adobe granskar och uppdaterar regelbundet de algoritmer som stöds baserat på nuvarande säkerhetspraxis. Kontakta kundtjänst om du vill ändra säkerhetsinställningarna för chiffrering.

Standard kräver TLS 1.2 eller senare och minst 128-bitars kryptering. Den är utformad för att ge största möjliga enhetskompatibilitet samtidigt som den bevarar säker kryptering.

Hög chiffreringssäkerhetsnivå kräver TLS 1.2 eller senare och tar bort stödet för svagare cifer. Den är utformad för kunder som vill ha den starkaste krypteringen och inte bryr sig om stöd för äldre enheter.

Följande klienter är kända för att inte kunna ansluta med krypteringssäkerhet inställd på Hög.

* Windows 8.1 och tidigare (senast uppdaterat 2018)
* Windows Phone 8.1 och tidigare (senast uppdaterad 2016)
* OS X 10.10 och tidigare (senast uppdaterat 2017)
* iOS 8.4 och tidigare (senast uppdaterad 2015)

## HTTPS-certifikattyper som stöds

Adobe stöder både RSA- och ECC-certifikattyper för att uppfylla olika kundbehov. RSA-certifikat stöds i större utsträckning för klienter, men ECC-certifikat använder mindre bearbetning både på server- och klientsidan. För certifikat som hanteras av Adobe tillhandahålls både RSA och ECC. För kundhanterade certifikat rekommenderas både RSA och ECC. Moderna klienter stöder både RSA och ECC. Följande klienter har endast stöd för RSA-certifikat:

* Windows Vista och tidigare (senast uppdaterat 2012)
* Windows Phone 8.0 och tidigare (senast uppdaterad 2014)
* OS X 10.8 och tidigare (senast uppdaterat 2013)
* iOS 5.1 och tidigare (senast uppdaterad 2012)
* Android 4.3 och tidigare (senast uppdaterat 2013)
