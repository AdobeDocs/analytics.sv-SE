---
description: Nedan följer några tips om hur du bäst hanterar och levererar dataflöden.
keywords: Datafeed;bästa praxis;trafikspik;timvis;ftp
title: God praxis och allmän information
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 6f7f46b0fee46e572a65f639ea511478c0118f4e
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 0%

---

# Bästa praxis

Nedan följer några tips om hur du bäst hanterar och levererar dataflöden.

* Försäkra dig om att du i förväg informerar om förväntade trafiktoppar. Latens påverkar bearbetningstiden direkt för dataflöden. Se [Schemalägg en trafiktoppning](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md) i användarhandboken för Admin.

* Dataflöden innehåller inte något servicenivåavtal såvida det inte uttryckligen anges i ditt avtal med Adobe. Feeds levereras vanligtvis inom flera timmar efter att rapportfönstret har passerat, men kan ibland ta upp till 12 timmar eller mer.

* Se till att du har gott om utrymme på FTP-platsen. Ta bort filer från målet regelbundet så att du inte råkar få slut på diskutrymme av misstag.

* Timmatning med flera olika filleveransprocesser är snabbast. Du bör använda flera filflöden per timme om du prioriterar leverans i rätt tid.

* Om du använder sFTP ska du inte läsa eller ta bort filer med en `.part` suffix. The `.part` -suffix anger att filen har överförts delvis. När filen har överförts visas `.part` suffixet försvinner.

* Om du automatiserar din matningsprocess bör du tänka på att träffar och filer kan överföras mer än en gång. Din matningsprocess måste hantera dubblettträffar och dubblettfiler utan att behöva skriva ut eller duplicera data. Vi rekommenderar att du använder en kombination av `hitid_high` och `hitid_low` kolumner för att unikt identifiera en träff.

   I sällsynta fall kan du se dubbletter `hitid_high` och `hitid_low` värden. Om det inträffar bekräftar du att filen inte har skickats och bearbetats tidigare. Om endast vissa rader i en fil är duplicerade bör du överväga att lägga till `visit_num` och `visit_page_num` för att avgöra om de är unika.
