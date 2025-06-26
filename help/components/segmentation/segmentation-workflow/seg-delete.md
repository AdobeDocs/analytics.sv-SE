---
description: Visar en lista över några överväganden som du bör vara medveten om innan du tar bort segment.
title: Ta bort segment
feature: Segmentation
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Ta bort segment

I den här artikeln beskrivs några saker du bör tänka på innan du tar bort segment.

När du tar bort ett segment:

* Schemalagda rapporter och instrumentpaneler som använder det här segmentet fortsätter att fungera som vanligt. Segmentet eller kontrollpanelen fortsätter till exempel att använda det borttagna segmentet.
* Schemalagda rapporter uppdateras inte när du redigerar ett segment med samma namn. Här följer ett exempel: Anta att du har två segment med samma namn i olika rapportsviter:

  | Segmentnamn | Rapportsvit |
  |---|---|
  | Besök från Kalifornien | mainprod |
  | Besök från Kalifornien | maindev |

  Du har ett bokmärke som refererar till segmentet för rapportsviten [!UICONTROL mainprod]. Sedan tar du bort segmentet eftersom segmentet är en dubblett. Bokmärket fortsätter att köras och refererar till definitionen för det borttagna segmentet. Om du ändrar segmentdefinitionen för det återstående segmentet till att omfatta Catalinön och Tijuana Mexico, ändras inte segmentet som används för bokmärket. Segmentet använder den gamla definitionen. Du åtgärdar detta genom att uppdatera bokmärket så att det refererar till den nya definitionen. Om du är osäker på om ett bokmärke, en kontrollpanel eller en schemalagd rapport använder ett borttaget segment, kan du ändra namnet på det återstående segmentet för att ange om bokmärket använder det återstående segmentet.
