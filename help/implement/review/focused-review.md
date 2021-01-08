---
title: Fokuserad granskning (efter varje webbplatsrelease)
description: Följ de här stegen för att se till att implementeringen inte är felfri och att den överensstämmer med dina nyckeltal.
translation-type: tm+mt
source-git-commit: a7f1da79bd5a6f78ed1a706ccae01b03a2f5665c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---


# Fokuserad granskning (efter varje webbplatsrelease)

Varför ska ni granska implementeringen var tredje månad? Så att ni kan ta itu med eventuella problem med datakvaliteten medan de fortfarande är små. Om du konsekvent utför den fokuserade granskningen efter varje webbplatsrelease kommer du att märka att det är mycket lättare att utföra dina [fullständiga granskningar](/help/implement/review/full-review.md) varannan år. Ni kommer också att förhindra att små problem växer till stora dataproblem som kan urholka intressenternas förtroende.

## 1. Börja med de fem viktigaste KPI:erna.

Genom att känna till era fem nyckeltal (KPI) kan ni identifiera de mått och mått ni behöver undersöka. Om du inte har uppdaterat dina nyckeltal de senaste sex månaderna eller om ditt företag ännu inte har skapat nyckeltal följer du [dessa instruktioner](/help/implement/review/define-kpis.md).

## 2. Se till att era KPI-värden och variabler fortfarande fungerar bra.

Kom ihåg att koduppdateringar kan få oönskade konsekvenser. Du vill se till att alla mått och mått som är associerade med [dina 5 KPI:er](/help/implement/review/define-kpis.md) fortfarande fungerar som de ska. Helst bör detta göras direkt efter en webbplatsrelease. om du inte har gjort det de senaste månaderna, gör det *nu*. Så här gör du:

* **Skapa** kontrollpaneler för att se timvisa trendvyer av dessa viktiga mått och variabler. Du kan också skapa intelligenta aviseringar för varje mätvärde och övervaka dem en dag eller två för att säkerställa att du får de data du förväntar dig, och att data är korrekta. Håll utkik efter inflammationspunkter. Var beredd på att åtgärda allvarliga problem omedelbart. Om du hittar avvikelser kan du ta reda på varför i datalagret, tagghanteringsreglerna och bearbetningsreglerna.
* **Kör Analytics Health** Dashboard igen för att övervaka breda trender för KPI-värden och -variabler.

Mer information om hur du ser till att dina mått och variabler fungerar som de ska finns i [dessa tips](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) från Adobe Analytics Champion Sarah Owen.

## 3. Granska noggrant data från den uppdaterade delen av din webbplats.

Se till att den senaste webbplatsversionen inte har någon negativ inverkan på datainsamlingen för det avsnittet på webbplatsen: Granska all kod och alla variabler som motsvarar det avsnittet för att säkerställa att den nya spårningen fungerar som avsett.

## 4. Uppdatera dokumentationen.

Om du nyligen har lagt till eller ändrat några mätvärden eller variabler måste du uppdatera ditt Business Requirement Document (BRD) och Solution Design Reference (SDR).

Om du inte har någon dokumentation om implementeringen exporterar du en lista med variabler och skapar din BRD eller SDR med [den här mallen](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 5. Åtgärda omedelbart eventuella luckor i datakvaliteten.

Utvärdera situationen och ta fram en plan för att åtgärda uppgifterna. Gör sedan de ändringar du behöver, uppdatera dokumentationen och informera dina intressenter om ändringarna.

*Titta på den här 2-minuters videon från Adobe Analytics Champion Sarah Owen om naturliga tider när du kan anpassa granskningar av din implementering till ditt hektiska schema:*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
