---
description: Nedan följer några tips om hur du bäst hanterar och levererar dataflöden.
keywords: Datafeed;bästa praxis;trafikspik;timvis;ftp
title: God praxis och allmän information
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 8f6c6aabf1e41cfd4b143a5d4cf14e73cdcbb603
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Bästa praxis

Nedan följer några tips om hur du bäst hanterar och levererar dataflöden.

* Försäkra dig om att du i förväg informerar om förväntade trafiktoppar. Latens påverkar bearbetningstiden direkt för dataflöden. Se [Schemalägg en trafikspik](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) i användarhandboken för Admin.

* Dataflöden innehåller inte något servicenivåavtal såvida det inte uttryckligen anges i ditt avtal med Adobe. Feeds levereras vanligtvis inom flera timmar efter att rapportfönstret har passerat, men kan ibland ta upp till 12 timmar eller mer.

* Se till att du har gott om utrymme på FTP-platsen. Ta bort filer från målet regelbundet så att du inte råkar få slut på diskutrymme av misstag.

* Timmatning med flera olika filleveransprocesser är snabbast. Du bör använda flera filflöden per timme om du prioriterar leverans i rätt tid.

* Om du använder sFTP ska du inte läsa eller ta bort filer med suffixet `.part`. `.part`-suffixet anger att filen har överförts delvis. När filen har överförts försvinner suffixet `.part`.

* Om du automatiserar din matningsprocess bör du tänka på att träffar och filer kan överföras mer än en gång. Din matningsprocess måste hantera dubblettträffar och dubblettfiler utan att behöva skriva ut eller duplicera data. Vi rekommenderar att du använder en kombination av kolumnerna `hitid_high` och `hitid_low` för att unikt identifiera en träff.

   I sällsynta fall kan du se dubblettvärden för `hitid_high` och `hitid_low`. Om det inträffar bekräftar du att filen inte har skickats och bearbetats tidigare. Om bara några av raderna i en fil är duplicerade kan du lägga till `visit_num` och visit_page_num` för att avgöra om de är unika.
