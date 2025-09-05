---
title: Listvariabler
description: Skapa och konfigurera listvariabler för rapportering.
feature: Admin Tools
role: Admin
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 0%

---

# Listvariabler

Skapa och konfigurera listvariabler för rapportering. Ange värden för avgränsare, förfallodatum, allokering och max. Samla in data för listvariabler med [`list1` - `list3`](/help/implement/vars/page-vars/list.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]**

* **[!UICONTROL Name]**: Listvariabelns namn. Det här namnet är dimensionsetiketten i Analysis Workspace.

* **[!UICONTROL Status]**: Aktivera eller inaktivera datainsamling för den här variabeln. Om en variabel är inaktiverad samlas inga data in, även om implementeringen skickar data till den variabeln.

* **[!UICONTROL Value Delimiter]**: Det tecken som används för att separera värden inom listvariabeln. De vanligaste är tecken som kommatecken, kolon, rör eller liknande. Flerbytetecken stöds inte som avgränsare i listvariabler.

* **[!UICONTROL Expire After]**: Precis som när eVar förfaller avgör det här fältet hur lång tid det kan ta mellan listvariabeln och konverteringshändelsen för dem att vara relaterade.
   * **Vid sidvisning eller besök**: Framgångshändelser utanför sidvyn eller besök länkar inte tillbaka till några värden i listvariabeln.
   * **Baserat på en tidsperiod, t.ex. dag, vecka, månad osv.**: Slutförda händelser efter den angivna tidsperioden länkar inte tillbaka till några värden i listvariabeln. Ett anpassat antal dagar kan också definieras.
   * **Specifika konverteringshändelser**: Alla andra lyckade händelser som utlöses efter den angivna specifika händelsen länkas inte tillbaka till några värden i listvariabeln.
   * **Aldrig**: En viss tid kan gå mellan listvariabeln och success-händelsen.

* **[!UICONTROL Allocation]**: Den här inställningen avgör hur lyckade händelser delar kredit mellan värden:
   * **Fullständig**: Alla variabelvärden som har definierats innan variabelns förfallodatum får full kredit för lyckade händelser.
   * **Linjär**: Alla variabelvärden som definierats innan variabeln har upphört att gälla får kreditdelad kredit för konverteringshändelser.
   * Variabelvärden skrivs aldrig över, utan läggs i stället till de värden som får kredit för lyckade händelser.

* **[!UICONTROL Description]**: En beskrivning av hur din organisation använder listvariabeln.

* **[!UICONTROL Max Values]**: Anger antalet aktiva värden som tillåts för den här listvariabeln. Om värdet till exempel är 3 sparas bara de tre senaste värdena som hämtats och alla tidigare värden som hämtats tas bort. Observera, att om flera värden för samma listvariabel skickas i samma träff och du har begränsat med max-värden, får varje värde samma tidsstämpel och det finns ingen garanti för vilket värde som sparas. Om en besökare behåller fler värden än det högsta tillåtna värdet används de senaste värdena. Upp till 250 maxvärden tillåts.

  Den här inställningen är användbar för att begränsa attribuering till ett visst antal värden. Om en listvariabel till exempel är inställd på `"A,B,C"` på den första sidan av ett besök och sedan är inställd på `"X,Y,Z"` på nästa sida, fördelas attribueringen till dessa sex värden baserat på dess allokering. Om du vill begränsa attribuering till endast `"X,Y,Z"` kan du ange maxvärden till tre.
