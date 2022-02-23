---
description: Beskriver den kontinuerliga funktionsreleasestrategin för Adobe Analytics
title: Adobe Analytics funktionsreleaser
feature: Release Notes
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 1%

---

# Adobe Analytics funktionsreleaser

Adobe Analytics-releaser bygger på en kontinuerlig leveransmodell som ger en mer skalbar, stegvis metod för driftsättning av funktioner.

## Frisläppningsstrategi

[!UICONTROL Analysis Workspace] använder funktionsflaggor (kallas även&quot;växlar&quot;) för att styra synligheten för nya funktioner, vilket möjliggör kontrollerad skaltestning före den fullständiga versionen. Den här versionsstrategin innehåller följande faser:

* **Frigör till produktion (RTP)**: Koden släpps i produktionen och synligheten för funktioner inaktiveras i Analysis Workspace. Funktionen är ibland tillgänglig i 2.0 Analytics API.

* **Begränsad testning**: En stegvis release börjar med testning av användare i Adobe. Versionen skalas sedan från 0 % till 100 % av tillgängligheten under ett par månader. Utfasad utrullning sker på organisationsnivå, så att alla berättigade användare i en organisation får samma upplevelse.

* **Allmän tillgänglighet (GA)**: Funktionen är tillgänglig för 100 % av berättigade Experience Cloud-organisationer och har släppts fullständigt.

För varje funktionsversion kan tidslinjen från RTP till GA variera. Målet är att hålla releaserna korta, så att en funktion blir GA inom två månader från lanseringsstarten (RTP).

## Funktionsflaggor

Funktionsflaggor används för att styra synligheten för nya funktioner under lanseringen. Adobe rekommenderar att du lägger till `app.launchdarkly.com` till er brandvägg [tillåtelselista](/help/technotes/ip-addresses.md) för en optimal upplevelse under lanseringen. Kort efter att GA har nåtts tas flaggan bort.

Du kan när som helst visa flaggor för den aktiva funktionen under **Hjälp > Om arbetsyta > Aktiva funktionsflaggor**.

## Fördelar

Med fasade versioner kan Adobe bättre anpassa driftsättningsprocessen och se till att funktionerna blir bättre före den allmänna tillgängligheten. Funktioner kan också släppas så snart de är tillgängliga, i stället för att följa ett fast månadsfönster.

## Vanliga frågor

| Fråga | Svar |
| --- | --- |
| Kan jag begära tidig åtkomst till en funktion? | Nej. Tidig tillgång kommer inte att beviljas.<br>Om du vill testa tidiga Analytics-koncept rekommenderar vi att du försöker [Adobe Analytics Labs](/help/analyze/labs.md) för att ge feedback på våra branschledande innovationer. |
| Påverkar den här versionsstrategin min tillgång till funktioner? | Nej. När en funktion har nått GA får du tillgång till funktionen om den ingår i Analytics-paketet.<br>Du kan visa information om ditt Analytics-paket under [Åtkomstnivåer för funktioner](/help/admin/company/feature-access-levels.md). |
