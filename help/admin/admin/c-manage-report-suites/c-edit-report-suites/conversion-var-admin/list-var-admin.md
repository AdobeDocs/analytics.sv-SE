---
title: Listvariabler
description: Skapa och konfigurera listvariabler för rapportering.
feature: Admin Tools
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
source-git-commit: 21029930b5cae6acb6bc6a59836ddc1ca33cb27e
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Listvariabler

Skapa och konfigurera listvariabler för rapportering. Ange värden för avgränsare, förfallodatum, allokering och max.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Finding Methods]**

* **Namn**: Varje avgränsat värde kan innehålla högst 255 tecken (eller mindre om flerbytetecken används). Det här är maxlängden för varje element.
* **Värdeavgränsare**: Det tecken som används för att avgränsa värden inom List Var. De vanligaste är tecken som kommatecken, kolon, rör eller liknande.

  >[!NOTE]
  >
  >Flerbytetecken stöds inte som avgränsare i List Vars. Avgränsaren måste vara en byte.

* **Förfaller**: På samma sätt som när eVar förfaller avgör det här fältet hur lång tid det kan ta mellan List Var och konverteringshändelsen för dem att vara relaterade.
   * **På sidvy eller besöksnivå**: Framgångshändelser utanför sidvyn eller besöket länkar inte tillbaka till några värden i List Var.
   * **Baserat på en tidsperiod, t.ex. dag, vecka, månad**: Slutförda händelser efter den angivna tidsperioden länkar inte tillbaka till några värden i List Var. Ett anpassat antal dagar kan också definieras.
   * **Specifika konverteringshändelser**: Andra lyckade händelser som utlöses efter den angivna händelsen länkas inte tillbaka till några värden i List Var.
   * **Aldrig**: Hur lång tid som helst kan gå mellan händelsen List Var och success.

* **Allokering**: Den här inställningen avgör hur lyckade händelser delar upp kredit mellan värden:
   * **Fullständig**: Alla variabelvärden som har definierats innan variabelns förfallodatum får full kredit för lyckade händelser.
   * **Linjär**: Alla variabelvärden som har definierats innan variabelns förfallodatum får kreditdelad kredit för konverteringshändelser.
   * Variabelvärden skrivs aldrig över, utan läggs i stället till de värden som får kredit för lyckade händelser.

* **Max. värden**: Anger antalet aktiva värden som tillåts för den här listvariabeln. Om värdet till exempel är 3 sparas bara de tre senaste värdena som hämtats och alla tidigare värden som hämtats tas bort. Observera, att om flera värden för samma lista skickas in för samma träff och du har begränsat med max-värden, kommer varje värde att ha samma tidsstämpel och det finns ingen garanti för vilket värde som sparas.

En gräns på 250 maxvärden lagras en gång per besökare. Om 250 värden per besökare överskrids används de senaste 250 värdena. Förfallodagen för dessa värden baseras på variabelns konfigurerade förfallodatum.

Inställningen Max. värden är användbar för att begränsa attribuering till ett visst antal värden. Om till exempel en listvar är inställd på&quot;A,B,C&quot; på första sidan av ett besök och sedan är inställd på&quot;X,Y,Z&quot; på nästa sida, fördelas attribueringen till dessa sex värden baserat på allokeringen. Om du vill begränsa attribueringen till endast&quot;X,Y,Z&quot; kan du ange maxvärden till tre.
