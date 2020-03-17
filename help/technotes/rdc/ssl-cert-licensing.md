---
title: SSL-certifikatlicensiering
description: Certifikatprocedurer för kundhanterade certifikat
translation-type: tm+mt
source-git-commit: 290838566b86f71902abd303b5c43dd2661d3ce1

---


# Licensiering av SSL-/TLS-certifikat

Adobe rekommenderar att du hanterar ditt certifikat utan extra kostnad via [Adobe Managed Certificate Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html).  Adobes program för hanterat certifikat är helt automatiserat och ser till att certifikaten förnyas i tid så att inget påverkar certifikat som gått ut.

Om du använder väljer att inte använda [Adobes program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) för hanterat certifikat ansvarar du för att tillhandahålla ett SSL/TLS-certifikat som ska användas för cookies från första part.

Om du tillhandahåller ett eget certifikat är det ditt ansvar att köpa och underhålla det.  SSL-/TLS-certifikatet måste innehålla en obegränsad serverlicens.

För att säkerställa certifikatsäkerheten ska du skaffa en CSR [] för certifikatsigneringsbegäran från Adobe och ordna med din önskade certifikatutfärdare att få certifikatet signerat.  Ge Adobe det signerade certifikatet för implementering.  Genom att följa den här processen upprätthålls certifikatets nyckelsäkerhet.  Adobes kundtjänst kommer att hjälpa till i den här processen.

Som en del av certifikatunderhållet ska du minst en månad innan ditt certifikat upphör att gälla samarbeta med den önskade certifikatutfärdaren för att få ett förnyat certifikat och lämna detta till Adobe.  Det här certifikatet bör använda samma CSR som tidigare.  Kontakta Adobe om du behöver en kopia av CSR eller vill ha en ny CSR genererad med en ny nyckel.

Kundtjänst finns på customercare@adobe.com eller 1-800-497-0335.

Vanliga certifikatutfärdare är DigiCert, Comodo och GeoTrust.
