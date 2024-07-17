---
description: Nedan följer några tips om hur du bäst hanterar och levererar dataflöden.
keywords: Datafeed;bästa praxis;trafikspik;timvis;ftp
title: God praxis och allmän information
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 6b42fc4a383b05a3630cbba7c5bce6b4561a9419
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 0%

---

# Bästa praxis för dataflöden

Nedan följer några tips om hur du bäst hanterar och levererar dataflöden.

* Försäkra dig om att du i förväg informerar om förväntade trafiktoppar. Latens påverkar bearbetningstiden direkt för dataflöden. Se [Schemalägg en trafiktoppning](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md) i användarhandboken för Admin.

* Dataflöden innehåller inte något servicenivåavtal såvida det inte uttryckligen anges i ditt avtal med Adobe. Feeds levereras vanligtvis inom flera timmar efter att rapportfönstret har passerat, men kan ibland ta upp till 12 timmar eller mer.

* Timmatning med flera olika filleveransprocesser är snabbast. Du bör använda flera filflöden per timme om du prioriterar leverans i rätt tid.

* Om du automatiserar din matningsprocess bör du tänka på att träffar och filer kan överföras mer än en gång. Din matningsprocess måste hantera dubblettträffar och dubblettfiler utan att behöva skriva ut eller duplicera data. Vi rekommenderar att du använder en kombination av kolumnerna `hitid_high` och `hitid_low` för att unikt identifiera en träff.

  I sällsynta fall kan du se duplicerade värden för `hitid_high` och `hitid_low`. Om det inträffar bekräftar du att filen inte har skickats och bearbetats tidigare. Om bara några av raderna i en fil är duplicerade kan du lägga till `visit_num` och `visit_page_num` för att avgöra om de är unika.

* Om du använder FTP (rekommenderas inte) måste du ha gott om utrymme på FTP-platsen. Ta bort filer från målet regelbundet så att du inte råkar få slut på diskutrymme av misstag.

* Om du använder sFTP (rekommenderas inte) ska du inte läsa eller ta bort filer med suffixet `.part`. Suffixet `.part` anger att filen har överförts delvis. När filen har överförts försvinner suffixet `.part`.