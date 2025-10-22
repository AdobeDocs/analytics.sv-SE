---
title: Besökaridentifiering med Web SDK JavaScript-bibliotek
description: Identifiera besökarna korrekt när du implementerar SDK JavaScript-biblioteket.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Besökaridentifiering med Web SDK JavaScript-bibliotek

Adobe Experience Platform Web SDK JavaScript-biblioteket (`alloy.js`) erbjuder en enhetlig, modern metod för datainsamling för alla Adobe Experience Cloud-program, inklusive Adobe Analytics. De flesta kunder implementerar vanligtvis [SDK-taggtillägget ](web-sdk-extension.md) för webben, men du kan använda SDK JavaScript-biblioteket fristående eller i ett tredjeparts tagghanteringssystem. Se [Tillåt](https://github.com/adobe/alloy) på GitHub om du vill hämta den senaste versionen av biblioteket.

Identitetsdata kan utökas med stöd för anpassade ID:n och flera namnutrymmen med hjälp av XDM:s `identityMap`. Adobe rekommenderar att du använder Adobe Experience Cloud ID Service som primär identifierare för Analytics, och använder andra identitetshanteringsalternativ för avancerade scenarier.

Om din organisation använder Web SDK JavaScript-biblioteket för att skicka data till Adobe Analytics krävs minimalt med konfigurering för besöksidentifiering. Besökar-ID-tjänsten är inbyggd i biblioteket och kräver bara att du anger **[!UICONTROL Edge Domain]** i kommandot `configure`. Om det här fältet är inställt på önskat värde fungerar besökaridentifieringen utan någon ytterligare konfiguration.
