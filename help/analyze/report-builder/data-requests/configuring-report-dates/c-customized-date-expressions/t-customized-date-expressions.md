---
description: Du kan ange ett komplext datumintervall genom att skapa ett anpassat uttryck.
title: Anpassade datumuttryck - översikt
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: User, Admin
exl-id: b3bdc07e-5c2d-4be3-86c9-b4b7380be0f6
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Anpassade datumuttryck

Du kan ange ett komplext datumintervall genom att skapa ett anpassat uttryck.

När du skapar uttryck ska du referera till en kalender för att ange antalet veckor och dagar korrekt. Excel har flera inbyggda funktioner som gör att du kan beräkna antalet dagar, arbetsdagar, månader och år mellan datum. Du kan använda dessa funktioner i formler för att beräkna andra intervall, t.ex. veckor och kvartal.

**Aktivera anpassade uttryck**

I följande exempel visas hur du aktiverar ett anpassat uttryck för **[!UICONTROL Rolling Dates]**.

1. I [!UICONTROL Request Wizard: Step 1] väljer du **[!UICONTROL Rolling Dates]** i stället för att använda **[!UICONTROL Preset Dates]**.

   ![Skärmbild med valda rullande datum.](assets/rolldates1.png)

1. Växla till rullande varje vecka, månad, kvartal eller år. Lägg märke till hur alternativen nedan ändras.
1. Klicka på **[!UICONTROL Show Advanced Options]** om du vill ha fler anpassningsalternativ.

   ![Skärmbild som markerar Visa avancerade alternativ.](assets/rolldates2.png)

1. Om du t.ex. ändrar datumen ovan till rullande månadsvis från den första dagen för tre månader sedan till den första dagen i den här månaden uppdateras datumen i alternativen för förskottsbetalning automatiskt så att de återspeglar följande:

   ![Skärmbild som visar rullande datum från första dagen för tre månader sedan till första dagen i den här månaden.](assets/rolldatesfor3.png)

1. Aktivera **[!UICONTROL Customize Expression]**. Genom att välja alternativ under **[!UICONTROL Rolling Dates]** kan du enkelt se syntaxen för anpassade datumuttryck.

   ![Skärmbild med Anpassa uttryck valt.](assets/rolldatesfor5.png)

   Du kan använda Avancerade alternativ för att blanda och matcha anpassade datumuttryck. Om du till exempel vill se data från det första året till slutet av den sista hela månaden kan du ange följande: `From: cy` `To: cm-1d`. I guiden visas dessa datum som 1 januari 2020-1/31/2020.
