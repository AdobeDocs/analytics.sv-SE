---
description: Du kan ange ett komplext datumintervall genom att skapa ett anpassat uttryck.
title: Anpassade datumuttryck – översikt
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 4%

---


# Anpassade datumuttryck – översikt

Du kan ange ett komplext datumintervall genom att skapa ett anpassat uttryck.

Vi rekommenderar att du refererar till en kalender när du skapar uttryck för att ange antalet veckor och dagar korrekt. Excel har flera inbyggda funktioner som gör att du kan beräkna antalet dagar, arbetsdagar, månader och år mellan datum. Du kan använda dessa funktioner i formler för att beräkna andra intervall, t.ex. veckor och kvartal.

**Aktivera anpassade uttryck**

Detta är ett exempel som använder **[!UICONTROL Rolling Dates]**.

1. Välj **[!UICONTROL Rolling Dates]** i stället för att använda **[!UICONTROL Preset Dates]**.[!UICONTROL Request Wizard: Step 1]

   ![](assets/rolldates1.png)

1. Växla till rullande varje vecka, månad, kvartal eller år. Lägg märke till hur alternativen nedan ändras.
1. Om du vill ha fler anpassningsalternativ klickar du på **[!UICONTROL Show Advanced Options]**.

   ![](assets/rolldates2.png)

1. Om du t.ex. ändrar datumen ovan till rullande månadsvis från den första dagen för tre månader sedan till den första dagen i den här månaden uppdateras datumen i alternativen för förskottsbetalning automatiskt så att de återspeglar följande:

   ![](assets/rolldatesfor3.png)

1. Aktivera **[!UICONTROL Customize Expression]**. Genom att välja alternativ under **[!UICONTROL Rolling Dates]** kan du enkelt se syntaxen för anpassade datumuttryck.

   ![](assets/rolldatesfor5.png)

   Du kan använda Avancerade alternativ för att blanda och matcha anpassade datumuttryck. Om du till exempel vill se data från det första året till slutet av den sista hela månaden kan du ange följande: `From: cy` `To: cm-1d`. I guiden visas dessa datum som 1/1/2020-1/31/2020.
