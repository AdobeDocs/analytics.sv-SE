---
title: SSL-certifikatlicensiering
description: Certifikatprocedurer för kundhanterade certifikat
feature: Regional Data Collection
exl-id: 7d1373c8-6f7b-4ce7-a555-d3d506e08d17
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---

# Licensiering av SSL-/TLS-certifikat

Adobe rekommenderar att du hanterar ditt certifikat utan extra kostnad via [Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html). Det hanterade certifikatprogrammet i Adobe är helt automatiserat och ser till att certifikaten förnyas i tid så att det inte påverkar certifikat som gått ut.

Om du använder väljer du att inte använda [Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html) du ansvarar för att tillhandahålla ett SSL-/TLS-certifikat som ska användas för cookies från första part.

Om du tillhandahåller ett eget certifikat är det ditt ansvar att köpa och underhålla det.  SSL-/TLS-certifikatet måste innehålla en obegränsad serverlicens.

För att säkerställa certifikatsäkerheten måste du skaffa en CSR-fil [CSR] från Adobe och samarbeta med den önskade certifikatutfärdaren för att få certifikatet signerat.  Ge Adobe det signerade certifikatet för implementering.  Genom att följa den här processen upprätthålls certifikatets nyckelsäkerhet.  Adobe kundtjänst hjälper till i den här processen.

Som en del av certifikatunderhållet ska du, minst en månad innan ditt certifikat upphör att gälla, samarbeta med den önskade certifikatutfärdaren för att få ett förnyat certifikat och lämna detta till Adobe.  Det här certifikatet bör använda samma CSR som tidigare.  Kontakta Adobe om du behöver en kopia av CSR eller vill ha en ny CSR genererad med en ny nyckel.

Kundtjänst finns på customercare@adobe.com eller 1-800-497-0335.

Vanliga certifikatutfärdare är DigiCert, Comodo och GeoTrust.
