---
title: Besökaridentifiering med Web SDK JavaScript-bibliotek
description: Identifiera besökarna korrekt när du implementerar SDK JavaScript-biblioteket.
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Besökaridentifiering med Web SDK JavaScript-bibliotek

Adobe Experience Platform Web SDK (`alloy.js`) erbjuder en enhetlig, modern metod för datainsamling för alla Adobe Experience Cloud-program, inklusive Analytics. Identitetsdata kan utökas med stöd för anpassade ID:n och flera namnutrymmen med hjälp av XDM:s `identityMap`. Adobe rekommenderar att du använder Adobe Experience Cloud ID Service som primär identifierare för Analytics, och använder andra identitetshanteringsalternativ för avancerade scenarier.

Om din organisation använder Web SDK JavaScript-biblioteket för att skicka data till Adobe Analytics krävs minimalt med konfigurering för besöksidentifiering. Besökar-ID-tjänsten är inbyggd i biblioteket och kräver bara att du anger **[!UICONTROL Edge Domain]** i kommandot `configure`. Om det här fältet är inställt på önskat värde fungerar besökaridentifieringen utan någon ytterligare konfiguration.
