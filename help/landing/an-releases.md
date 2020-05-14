---
description: Beskriver den nya strategin för kontinuerlig funktionsrelease för Adobe Analytics
title: Funktionsreleaser för Adobe Analytics
translation-type: tm+mt
source-git-commit: dcca8559c9e730c9e04981d69068786878062561
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 0%

---


# Funktionsreleaser för Adobe Analytics

Historiskt sett följde Adobe Analytics-releaser ett fast månadsschema. Från och med april 2020 har Adobe Analytics övergått till en kontinuerlig leveransmodell som möjliggör en mer skalbar, fasad strategi för driftsättning av funktioner.

## Frisläppningsstrategi

[!UICONTROL Analysis Workspace] använder funktionsflaggor (kallas även&quot;växlar&quot;) för att styra synligheten för nya funktioner, vilket möjliggör kontrollerad skaltestning före den fullständiga versionen. Den här versionsstrategin innehåller följande faser:

* **Release to Production (RTP)**: Koden släpps upp i produktionen med funktionssynlighet inaktiverat i Analysis Workspace. **Obs**: På RTP kan funktionen vara tillgänglig i 2.0 Analytics API.

* **Begränsad testning**: En stegvis release börjar med att interna Adobe-användare testar. Versionen skalas sedan från 0 % till 100 % av tillgängligheten under ett par månader. Den fasade utrullningen sker på Experience Cloud-organisationsnivå, så att alla berättigade användare i en organisation får samma upplevelse.

* **Allmän tillgänglighet (GA)**: Funktionen är tillgänglig för 100 % av berättigade Experience Cloud-organisationer och funktionen är fullständig.

För varje funktionsversion kan tidslinjen från RTP till GA variera. Målet är att hålla releaserna korta, så att en funktion blir GA inom två månader efter lanseringen (RTP).

## Fördelar

Med fasade versioner kan Adobe bättre skala driftsättningsprocessen och säkerställa att funktionerna blir bättre före den allmänna tillgängligheten. Funktioner kan också släppas så snart de är tillgängliga, i stället för att följa ett fast månadsfönster.

## Vanliga frågor

| Fråga | Svar |
|---|---|
| Kan jag begära tidig åtkomst till en funktion? | Nej. Tidig tillgång kommer inte att beviljas.<br>Om du vill testa tidiga Analytics-koncept rekommenderar vi att du provar [Adobe Analytics Labs](https://docs.adobe.com/content/help/en/analytics/analyze/tech-previews/overview.html) för att ge feedback på våra branschledande innovationer. |
| Påverkar den här versionsstrategin min tillgång till funktioner? | Nej. När en funktion har nått GA får du tillgång till funktionen om den ingår i Analytics-paketet.<br>Du kan visa information om ditt Analytics-paket under [!UICONTROL Admin] > [!UICONTROL Company Settings] > [Funktionsåtkomstnivåer](https://docs.adobe.com/content/help/en/analytics/admin/company-settings/feature-access-levels.html). |