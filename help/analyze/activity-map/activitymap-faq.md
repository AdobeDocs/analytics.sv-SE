---
description: Vanliga frågor och svar om hur du konfigurerar, konfigurerar och använder funktioner i Activity Map.
title: Vanliga frågor om Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: 0570bea923edc21a0f185f49fd6f604115d4a6e1
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Vanliga frågor om Activity Map

Vanliga frågor och svar om hur du konfigurerar, konfigurerar och använder funktioner i Activity Map.

+++Har alla Analytics-kunder tillgång till sidan för aktivering av Admin Tools ActivityMap?
Organisationer som har ett kontrakt för Adobe Analytics Standard, Premium och Ultimate har tillgång till Activity Map.
+++

+++Hur stöder Activity Map Single-Page Applications (SPA)?
Med några sekunders mellanrum skannar Activity Map webbsidan och letar efter ändringar på sidan. ActivityMap hittar nytt innehåll på sidan utan att en ny sidinläsning krävs, men det nya innehållet tilldelas alltid till den första pageName som hittades när sidan lästes in.

* Activity Map kontrollerar om synligheten för länkar som de känner till har ändrats. Om synligheten ändras uppdateras kolumnen Present (Länkar på sida) för den länken med [!UICONTROL Displayed] eller [!UICONTROL Hidden].

* När användarinteraktion skapar nytt innehåll läggs alla nya element som AppMeasurement finner vara en länk till i [!UICONTROL Links On Page] tabell. Activity Map skickar en ny databegäran som innehåller de nya länkarna. De nya länkarna ska visas i [!UICONTROL Links On Page] tabellen när databegäran hanteras av användargränssnittet.
+++

+++Tillhandahåller Activity Map data om&quot;vyer&quot;?
Nej, Adobe spårar inte länkar som visats.
+++

+++Vilka webbläsare och versioner stöder Activity Map?
Activity Map har stöd för den senaste versionen av de flesta moderna webbläsare.
+++

+++Ökar Activity Map serveranrop?
Activity Map skickar inte serversamtal själv. I stället inkluderas datavariabler för kontext i Activity Map i sidvisningsanropen för Analytics på efterföljande sida.
+++

+++Varför saknas vissa rankade objektövertäckningar?
Vissa rankade länkar, t.ex. undermenylänkar, är dolda på sidan. Därför visas inte deras motsvarande länkövertäckningar. Rankningen beräknas för alla länkar på sidan, inklusive dolda länkar.
+++

+++Hur bestäms länkrankningen i rapporten Alla länkar?**
* **I läget Övertoning och Bubbel**: Rankningen bestäms av måttkolumnen. För länkar med samma måttvärde baseras rangordningen ytterligare på länk-ID i alfabetisk ordning.
* **I grönt och glesare läge**: Rankningen bestäms primärt av kolumnen % vinst. För länkar med samma ökning baseras rangordningen ytterligare på länk-ID i alfabetisk ordning.
+++

+++Hur fungerar Activity Map med sidor som använder flera rapportsviter?
Som standard använder Activity Map den rapportserie som är associerad med den första taggen som skickas av sidan. Du kan välja en annan taggad rapportserie via **[!UICONTROL Activity Map Settings]** > **[!UICONTROL Others]** -fliken.
+++

+++Hur länge söker Activity Map efter Adobe Analytics på sidan?
Aktivitetskartan söker efter Adobe Analytics i upp till 20 sekunder efter en händelse om att sidan har slutförts.
+++

+++Hur hanterar Activity Map dynamiskt innehåll?
Activity Map kontrollerar varannan sekund om det finns några förändringar i webbsidans tillstånd, till exempel:

* HTML-innehåll som har blivit synligt
* dolt HTML-innehåll
* Nytt HTML-innehåll som injicerats

Om innehållet är dolt eller visas, ändrar programmet automatiskt läget för berörda länkar (och därmed övertäckningar) från dolt till visat eller från visat till dolt. Om nytt innehåll injiceras hämtar programmet de associerade länkarna, hämtar analysdata för dem och lägger till övertäckningar för dessa länkar.
+++

+++Vilka mått baseras sidflödesrapporten på?
Alla data som visas baseras på sidvisningar.
+++

+++Kan jag exportera datavariabler i Activity Map-kontext via dataflöden?
Ja. The [Datakolumner](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) som Activity Map använder `clickmaplink`, `clickmaplinkbyregion`, `clickmappage`och `clickmapregion`.
+++

+++Fungerar segment i Live-läge?
Nej, segment fungerar inte i Live-läge. Funktionen motsvarar den i realtidsrapporter i rapporter och analyser, som inte stöder segmentering.
+++

+++Är Activity Map kompatibelt med virtuella rapportsviter?
Ja. På grund av begränsningar i den virtuella rapportsviten är Activity Map Live Mode inte kompatibelt med virtuella rapportsviter.
+++

+++Hur inaktiverar jag Activity Map?
Du har tre alternativ:

* Ta bort `AppMeasurement_Module_ActivityMap` funktion från JS-filen
* Lägg till egen kod som skriver om funktionen ovan med en tom brödtext, till exempel:

   ```js
   function AppMeasurement_Module_ActivityMap() {}
   ```

* Konfigurera AppMeasurement med inställning `s.trackClickMap` och `s.trackInlineStats` till `false`
+++
