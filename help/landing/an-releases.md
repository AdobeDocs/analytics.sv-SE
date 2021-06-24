---
description: Beskriver den nya strategin för kontinuerlig funktionsrelease för Adobe Analytics
title: Adobe Analytics funktionsreleaser
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
source-git-commit: f120c189228892e57e38e4d0e106eb3190326ff1
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 1%

---

# Adobe Analytics funktionsreleaser

Historiskt sett följde Adobe Analytics-releaser ett fast månadsschema. Från och med april 2020 övergick Adobe Analytics till en kontinuerlig leveransmodell som möjliggör en mer skalbar, stegvis metod för driftsättning av funktioner.

## Frisläppningsstrategi

[!UICONTROL Analysis Workspace] använder funktionsflaggor (kallas även&quot;växlar&quot;) för att styra synligheten för nya funktioner, vilket möjliggör kontrollerad skaltestning före den fullständiga versionen. Den här versionsstrategin innehåller följande faser:

* **Release to Production (RTP)**: Koden släpps i produktionen och synligheten för funktioner inaktiveras i Analysis Workspace. **Obs**: På RTP kan funktionen vara tillgänglig i 2.0 Analytics API.

* **Begränsad testning**: En stegvis release börjar med testning av användare i Adobe. Versionen skalas sedan från 0 % till 100 % av tillgängligheten under ett par månader. Utfasad utrullning sker på organisationsnivå, så att alla berättigade användare i en organisation får samma upplevelse.

* **Allmän tillgänglighet (GA)**: Funktionen är tillgänglig för 100 % av berättigade Experience Cloud-organisationer och har släppts fullständigt.

För varje funktionsversion kan tidslinjen från RTP till GA variera. Målet är att hålla releaserna korta, så att en funktion blir GA inom två månader från lanseringsstarten (RTP).

## Funktionsflaggor

Funktionsflaggor används för att styra synligheten för nya funktioner under lanseringen. Adobe rekommenderar att du lägger till app.launchdarkly.com i din brandväggs [tillåtelselista](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html) för att få en optimal upplevelse under lanseringen. Kort efter att GA har nåtts tas flaggan bort.

Du kan när som helst visa de aktiva funktionsflaggorna under **Hjälp > Om arbetsyta > Aktiva funktionsflaggor**.

## Fördelar

Med fasade versioner kan Adobe bättre anpassa driftsättningsprocessen och se till att funktionerna blir bättre före den allmänna tillgängligheten. Funktioner kan också släppas så snart de är tillgängliga, i stället för att följa ett fast månadsfönster.

## Vanliga frågor

| Fråga | Svar |
| --- | --- |
| Kan jag begära tidig åtkomst till en funktion? | Nej. Tidig tillgång kommer inte att beviljas.<br>Om du vill testa tidiga Analytics-koncept rekommenderar vi att du provar  [Adobe Analytics ](https://experienceleague.adobe.com/docs/analytics/analyze/tech-previews/overview.html) Labs för att få feedback på våra branschledande innovationer. |
| Påverkar den här versionsstrategin min tillgång till funktioner? | Nej. När en funktion har nått GA får du tillgång till funktionen om den ingår i Analytics-paketet.<br>Du kan visa information om ditt Analytics-paket under  [!UICONTROL Admin] >  [!UICONTROL All admin] >  [!UICONTROL Company settings] >  [Funktionsåtkomstnivåer](https://experienceleague.adobe.com/docs/analytics/admin/company-settings/feature-access-levels.html). |
