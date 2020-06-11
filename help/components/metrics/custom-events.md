---
title: Anpassade händelser
description: Antalet träffar där en anpassad händelse finns.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---


# Anpassade händelser

*Den här hjälpsidan beskriver hur anpassade händelser fungerar som mått. Mer information om hur anpassade händelser fungerar som en implementeringsvariabel finns i[Händelseöversikt](/help/implement/vars/page-vars/events/events-overview.md)i användarhandboken för Implementera.*

Anpassade händelsemått visar antalet träffar där en viss anpassad händelse angavs i en bildbegäran. Dessa mått är viktiga för många implementeringar, eftersom de ger insikter till händelser som är specifika för varje organisation.

## Hur det här måttet beräknas

Anpassade händelser beräknas på olika sätt beroende på typ. Du kan kontrollera en händelses typ under [Slutförda händelser](../../admin/admin/c-success-events/success-event.md) i inställningarna för rapportsviten.

* **Räknarhändelser**: Standardinställningen för händelse. De flesta händelser är räknehändelser. Räknar antalet träffar där den matchande anpassade händelsen `event1` - `event1000` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabeln.
* **Numeriska händelser**: Summerar det numeriska värde som tilldelats händelsen i `events` variabeln.
* **Valutahändelser**: Tillämpar valutakonvertering mot den dagens valutakurs och summerar sedan det numeriska värde som tilldelats varje träff i `events` variabeln.

Antalet tillgängliga händelser beror på organisationens Analytics-kontrakt. De flesta organisationer som har kontrakt som inte är äldre har 1 000 anpassade händelser tillgängliga. Kontakta din organisations kontoansvarige om du inte är säker på hur många anpassade händelser som är tillgängliga för dig.

Adobe rekommenderar starkt att du registrerar hur du använder varje händelse i organisationens [lösningsdesigndokument](/help/implement/prepare/solution-design.md).
