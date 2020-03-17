---
title: Spåra olika implementeringstyper
description: Använd olika implementeringstyper och spåra besökare smidigt mellan dem.
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Spåra olika implementeringstyper

Den här informationen är avsedd för avancerade användare som är väl insatta i både rapportering och implementering. Försök inte redigera implementeringen utan att förstå konsekvenserna. Kontakta er kontoansvarige om ni behöver ändra implementeringen.

Om du använder mer än en typ av implementering (till exempel JavaScript och hårdkodade bildbegäranden) måste du se till att följande variabler anges och matchar varandra:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (om SSL används)

Om vart och ett av dessa inte matchar olika implementeringar kan användarna spåras som separata besökare.
