---
title: Anpassade händelser
description: Antalet träffar där en anpassad händelse finns.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Anpassade händelser

*Den här hjälpsidan beskriver hur anpassade händelser fungerar som mått. Mer information om hur anpassade händelser fungerar som en implementeringsvariabel finns i [Översikt över händelser](/help/implement/vars/page-vars/events/events-overview.md) i Implementeringshandboken.*

Anpassad händelse [mått](overview.md) visa antalet träffar där en viss anpassad händelse har angetts i en bildbegäran. Dessa mått är viktiga för många implementeringar, eftersom de ger insikter till händelser som är specifika för varje organisation.

## Hur det här måttet beräknas

Anpassade händelser beräknas på olika sätt beroende på typ. Du kan kontrollera en händelsetyp under [Slutförda händelser](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) i Rapportsvitens inställningar.

* **Räknarhändelser**: Standardinställningen för händelse. De flesta händelser är räknehändelser. Räknar antalet träffar där den matchande anpassade händelsen `event1` - `event1000` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabel.
* **Numeriska händelser**: Summerar det numeriska värde som tilldelats händelsen i `events` variabel.
* **Valutahändelser**: Använder valutakonvertering mot den aktuella dagens valutakurs och summerar sedan det numeriska värde som tilldelats varje träff i `events` variabel.

Antalet tillgängliga händelser beror på organisationens Analytics-kontrakt. De flesta organisationer som har kontrakt som inte är äldre har 1 000 anpassade händelser tillgängliga. Kontakta kontoteamet på Adobe om du inte är säker på hur många anpassade händelser som är tillgängliga för dig.

Adobe rekommenderar starkt att du registrerar hur du använder varje händelse i din organisations [konstruktionsdokument](/help/implement/prepare/solution-design.md).
