---
title: HTTPS-krypteringsalgoritmer som stöds
description: Den 23 juni 2022 tar vi bort stöd för TLS 1.2-ciphers som använder SHA1 eller CBC för kunder med chiffreringssäkerhetsnivån "Hög".
feature: Regional Data Collection
source-git-commit: ce607610516a94e4d0fbbc53a1f8f53f5977a777
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# HTTPS-krypteringsalgoritmer som stöds

Adobe erbjuder två krypteringsnivåer för att uppfylla olika kundbehov när det gäller säkerhet vid datainsamling från första part. Dessa nivåer avgör vilka krypteringsalgoritmer som stöds för HTTPS-anslutningar med våra servrar. Kunderna använder&quot;Standard&quot; som endast stöder moderna krypteringsalgoritmer. &quot;Hög&quot; stöder en mindre lista med krypteringsalgoritmer för kunder som är mer oroade över dessa anslutningar. För båda säkerhetsnivåerna uppdaterar Adobe regelbundet uppsättningen algoritmer som stöds baserat på nuvarande säkerhetspraxis. Kontakta kundtjänst om du vill ändra säkerhetsinställningarna för chiffrering.

Den 23 juni 2022 tar vi bort stöd för TLS 1.2-ciphers som använder SHA1 eller CBC för kunder med chiffreringssäkerhetsnivån &quot;Hög&quot;.  Den här ändringen påverkar säker datainsamling för slutanvändare i äldre operativsystem.

Följande TLS 1.2-skrivare stöds inte längre:

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA

Följande klienter påverkas av den här ändringen eftersom de saknar stöd för aktuella krypteringsstandarder:

* Windows 8.1 och tidigare (senast uppdaterat 2018)
* Windows Phone 8.1 och tidigare (senast uppdaterad 2016)
* OS X 10.10 och tidigare (senast uppdaterat 2017)
* iOS 8.4 och tidigare (senast uppdaterad 2015)

Android-enheter påverkas inte av den här ändringen.

Kunder som har chiffersäkerhetsnivån inställd på Standard påverkas inte av den här ändringen.

