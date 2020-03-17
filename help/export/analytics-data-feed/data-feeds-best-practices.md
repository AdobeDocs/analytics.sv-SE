---
description: 'Nedan följer några tips om hur du bäst hanterar och levererar dataflöden. Du borde '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: God praxis och allmän information
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Bästa praxis

Nedan följer några tips om hur du bäst hanterar och levererar dataflöden.

* Försäkra dig om att du i förväg informerar om förväntade trafiktoppar. Latens påverkar bearbetningstiden direkt för dataflöden. Se [Schemalägg en trafiktoppning](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) i användarhandboken för Admin.
* Dataflöden innehåller inte något servicenivåavtal såvida det inte uttryckligen anges i ditt avtal med Adobe. Feeds levereras vanligtvis inom flera timmar efter att rapportfönstret har passerat, men kan ibland ta upp till 12 timmar eller mer.
* Se till att du har gott om utrymme på FTP-platsen. Ta bort filer från målet regelbundet så att du inte råkar få slut på diskutrymme av misstag.
* Timmatning med flera olika filleveransprocesser är snabbast. Det kan vara bra att använda flera filflöden per timme om leveransen är en prioriterad fråga för organisationen.
* Om du använder sFTP ska du inte läsa eller ta bort filer med ett `.part` suffix. Suffixet anger att filen har överförts delvis `.part` . När filen har överförts försvinner suffixet `.part` .
* Om du automatiserar matningsprocessen bör du tänka på att en fil kan överföras mer än en gång. Duplicerade filer kan skickas av användaren eller sällan av Adobe.
