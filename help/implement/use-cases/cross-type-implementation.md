---
title: Spåra på olika implementeringstyper
description: Använd olika implementeringstyper och spåra besökare smidigt mellan dem.
feature: Implementation Basics
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 9%

---

# Spåra på olika implementeringstyper

Den här informationen är avsedd för avancerade användare som är väl insatta i både rapportering och implementering. Försök inte redigera implementeringen utan att förstå konsekvenserna. Kontakta er kontoansvarige om ni behöver ändra implementeringen.

Om du använder mer än en typ av implementering (till exempel JavaScript och hårdkodade bildbegäranden) måste du se till att följande variabler anges och matchar varandra:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (om SSL används)

Om vart och ett av dessa inte matchar olika implementeringar kan användarna spåras som separata besökare.
