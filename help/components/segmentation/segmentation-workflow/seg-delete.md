---
description: Förstå de överväganden du bör vara medveten om innan du tar bort segment.
title: Ta bort segment
feature: Segmentation
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 0%

---

# Ta bort segment

I den här artikeln beskrivs några saker du bör tänka på innan du tar bort segment.

När du tar bort ett segment:

* Schemalagda rapporter och instrumentpaneler som använder det här segmentet fortsätter att fungera som vanligt.
* Schemalagda rapporter uppdateras inte när du redigerar ett segment med samma namn.

<!--

For example: Assume you have 2 segments with the same name in different report suites:

  | Segment name | Report suite |
  |---|---|
  | Visits from California | mainprod |
  | Visits from California | maindev |

  You have a visualization that references the segment for the **[!UICONTROL mainprod]** report suite. Then you delete that segment because the segment is a duplicate. The bookmark will continue to run, referencing the definition of the deleted segment. If you change the segment definition for the remaining segment to include Catalina Island and Tijuana Mexico, the segment applied to the bookmark will not change. The segment will use the old definition. To fix this, update the bookmark to reference the new definition. If you are unsure whether a bookmark, dashboard or scheduled report is using a deleted segment, you could change the name of the remaining segment to indicate whether the bookmark is using the remaining segment.

-->