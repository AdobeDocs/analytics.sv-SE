---
description: Visar en lista över några saker du bör tänka på innan du tar bort segment.
title: Ta bort segment
feature: Segment
uuid: cb6db6ad-f400-4633-900a-8a02dcfccf2c
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 2%

---

# Ta bort segment

Visar en lista över några saker du bör tänka på innan du tar bort segment.

När du tar bort ett segment

* Schemalagda rapporter och instrumentpaneler som använder det här segmentet fortsätter att fungera som vanligt, dvs. segmentet eller instrumentpanelen fortsätter att använda det borttagna segmentet.
* Schemalagda rapporter uppdateras inte när du redigerar ett segment med samma namn. Här är ett exempel: Låt oss anta att du har två segment med samma namn i olika rapportsviter:

   ![](assets/duplicate_seg_names.png)

   Du har ett bokmärke som refererar till segmentet för huvudprod-rapportsviten. Sedan tar du bort segmentet eftersom det är en dubblett. Bokmärket fortsätter att köras och refererar till definitionen för det borttagna segmentet. Om du ändrar segmentdefinitionen för det återstående segmentet till att omfatta Catalinön och Tijuana Mexico, ändras inte segmentet som används för bokmärket. Den gamla definitionen kommer att användas. Du åtgärdar detta genom att uppdatera bokmärket så att det refererar till den nya definitionen. Om du är osäker på om ett bokmärke, en kontrollpanel eller en schemalagd rapport använder ett borttaget segment, kan du ändra namnet på det återstående segmentet så att det blir tydligare om bokmärket använder det återstående segmentet.
