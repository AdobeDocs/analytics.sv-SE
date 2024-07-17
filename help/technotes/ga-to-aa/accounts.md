---
title: Konton och rapportsviter
description: Lär dig använda ett inloggningsföretag och en rapportserie för att hålla ordning på data i Adobe Analytics.
feature: Third-party Integration
exl-id: f4cf2a77-30c1-40f8-ba18-e4d71e170831
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# Konton och rapportsviter

I Adobe Analytics finns det två nivåer för att hålla datastrukturen organiserad:

* Ett **inloggningsföretag** är en övergripande organisation som innehåller en eller flera rapportsviter. Ett inloggningsföretag liknar ett *konto* i andra analysverktyg, till exempel Google Analytics. Konsulter som arbetar med flera organisationer har vanligtvis tillgång till flera inloggningsföretag.
* En **rapportserie** är en databas där du skickar data och där du hämtar rapporter. En rapportsvit innehåller vanligtvis data från en webbplats, men det beror på implementeringen i respektive organisation. En rapportsvit liknar en *vy* i andra analysverktyg.

Större organisationer har oftast flera rapportsviter, en för varje webbplats eller app. Kontakta en administratör i organisationen om du är osäker på vilken rapporteringsprogramsvit du ska använda för att hämta data.

En viktig skillnad mellan Adobe datainsamlingsmetod och många andra verktyg är att du anger vilka rapporteringsprogram som data ska skickas till i implementeringen. Detta skiljer sig från andra verktyg som vanligtvis skickar alla data till en samlingsplats och sedan filtrerar ned dem till vyer eller profiler.

[!UICONTROL Virtual report suites] finns också i Adobe Analytics, som ger en filtrerad vy av en rapportserie utan att ändra datainsamling eller historiska data. Du kan t.ex. använda en [!UICONTROL virtual report suite] för att eliminera robottrafik som inte fångats tidigare eller exkludera bedrägliga/avvikande intäkter. Mer information finns i [Virtuella rapportsviter](/help/components/vrs/vrs-about.md) i användarhandboken för komponenter.
