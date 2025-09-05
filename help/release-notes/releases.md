---
description: Beskriver den kontinuerliga funktionsreleasestrategin för Adobe Analytics
title: Adobe Analytics funktionsreleaser
feature: Release Notes
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
source-git-commit: e09234ca27fbf923e026aa1f2ed0ebfed636bf7c
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 1%

---

# Adobe Analytics funktionsreleaser

Adobe Analytics-releaser bygger på en kontinuerlig leveransmodell som ger en mer skalbar, stegvis metod för driftsättning av funktioner.

## Frisläppningsstrategi

[!UICONTROL Analysis Workspace] använder funktionsflaggor (kallas även&quot;växlar&quot;) för att styra synligheten för nya funktioner, vilket möjliggör kontrollerad skaltestning före den fullständiga versionen. Den här versionsstrategin innehåller följande faser:

* **Begränsad testning**: En fasversion börjar med att testas av interna Adobe-användare. Den görs sedan tillgänglig för en liten grupp kundkonton för att säkerställa att funktionen uppfyller kundernas behov och förväntningar.

* **Början av utrullning**: utrullningen av en fasversion börjar med den begränsade testfasen. Versionen skalas sedan från 0 % till 100 % för kunder under ett par månader. Utfasad utrullning sker på Experience Cloud-organisationsnivå, så att alla berättigade användare i en organisation får samma upplevelse.

* **Allmän tillgänglighet (GA)**: Funktionen är tillgänglig för 100 % av berättigade Experience Cloud-organisationer och funktionen är klar.

För varje funktionsversion kan tidslinjen från Start of Rollout till GA variera. Målet är att hålla releaserna korta, så att en funktion blir GA inom två månader efter utrullningsstarten.

## Funktionsflaggor

Funktionsflaggor används för att styra synligheten för nya funktioner under lanseringen. Adobe rekommenderar att du lägger till `app.launchdarkly.com` i din brandväggs [tillåtelselista](/help/technotes/ip-addresses.md) för att få en optimal upplevelse under lanseringen. Kort efter att GA uppnåtts tas flaggan bort.

Du kan när som helst visa de aktiva funktionsflaggorna under **Hjälp > Om Workspace > Aktiva funktionsflaggor**.

## Fördelar

Med fasade versioner kan Adobe bättre skala driftsättningsprocessen och säkerställa att funktionerna blir bättre före den allmänna tillgängligheten. Funktioner kan också släppas så snart de är tillgängliga, i stället för att följa ett fast månadsfönster.

## Vanliga frågor

| Fråga | Svar |
| --- | --- |
| Kan jag begära tidig åtkomst till en funktion? | Nej. Tidig tillgång kommer inte att beviljas.<br>Om du vill testa tidiga Analytics-koncept rekommenderar vi att du provar [Adobe Analytics Labs](/help/analyze/labs.md) för att få feedback på våra branschledande innovationer. |
| Påverkar den här versionsstrategin min tillgång till funktioner? | Nej. När en funktion har nått GA får du tillgång till funktionen om den ingår i Analytics-paketet.<br>Du kan visa information om ditt Analytics-paket under [Åtkomstnivåer för funktioner](/help/admin/tools/company/feature-access-levels.md). |
