---
description: Vanliga frågor och svar om hur du konfigurerar, konfigurerar och använder funktioner i Activity Map.
title: Vanliga frågor om Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---


# Vanliga frågor om Activity Map

Vanliga frågor och svar om hur du konfigurerar, konfigurerar och använder funktioner i Activity Map.

## Har alla Analytics-kunder tillgång till sidan ActivityMap Enablement för Admin Tools?

Organisationer som har ett kontrakt för Adobe Analytics Standard, Premium och Ultimate har tillgång till Activity Map.

## Tillhandahåller Activity Map data om&quot;vyer&quot;?

Nej, Adobe spårar inte länkar som visats.

## Vilka webbläsare och versioner stöder Activity Map?

Activity Map har stöd för den senaste versionen av de flesta moderna webbläsare.

## Ökar Activity Map serveranrop?

Activity Map skickar inte serversamtal själv. I stället inkluderas datavariabler för kontext i Activity Map i sidvisningsanropen för Analytics på efterföljande sida.

## Varför saknas vissa rankade objektövertäckningar?**

Vissa rankade länkar, t.ex. undermenylänkar, är dolda på sidan. Därför visas inte deras motsvarande länkövertäckningar. Rankningen beräknas för alla länkar på sidan, inklusive dolda länkar.

## Hur bestäms länkrankningen i rapporten Alla länkar?**

* **I läget** Övertoning och Bubbel: Rankningen bestäms av måttkolumnen. För länkar med samma måttvärde baseras rangordningen ytterligare på länk-ID i alfabetisk ordning.
* **I läget** Ingenjör och Lägre: Rankningen bestäms primärt av kolumnen % vinst. För länkar med samma ökning baseras rangordningen ytterligare på länk-ID i alfabetisk ordning.

## Hur fungerar Activity Map med sidor som använder flera rapportsviter?

Som standard använder Activity Map den rapportserie som är associerad med den första taggen som skickas av sidan. Du kan välja en annan taggad rapportserie via fliken **[!UICONTROL Activity Map Settings]** > **[!UICONTROL Others]**.

## Hur länge söker Activity Map efter Adobe Analytics på sidan?

Aktivitetskartan söker efter Adobe Analytics i upp till 20 sekunder efter en händelse om att sidan har slutförts.

## Hur hanterar Activity Map dynamiskt innehåll?

Activity Map kontrollerar varannan sekund om det finns några förändringar i webbsidans tillstånd, till exempel:

* HTML-innehåll som har blivit synligt
* dolt HTML-innehåll
* Nytt HTML-innehåll som injicerats

Om innehållet är dolt eller visas, ändrar programmet automatiskt läget för berörda länkar (och därmed övertäckningar) från dolt till visat eller från visat till dolt. Om nytt innehåll injiceras hämtar programmet de associerade länkarna, hämtar analysdata för dem och lägger till övertäckningar för dessa länkar.

## Vilka mått baseras sidflödesrapporten på?

Alla data som visas baseras på sidvisningar.

## Kan jag exportera datavariabler för Activity Map-kontext via dataflöden?

Kontextvariabler för aktivitetskarta är inte tillgängliga i dataflöden.

## Fungerar segment i Live-läge?

Nej, segment fungerar inte i Live-läge. Funktionen motsvarar den i realtidsrapporter i rapporter och analyser, som inte stöder segmentering.

## Är Activity Map kompatibelt med virtuella rapportsviter?

Ja. På grund av begränsningar i den virtuella rapportsviten är Activity Map Live Mode inte kompatibelt med virtuella rapportsviter.
