---
title: Fokuserad granskning (efter varje webbplatsrelease)
description: Följ de här stegen för att se till att implementeringen inte är felfri och att den överensstämmer med dina nyckeltal.
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
role: Admin, Leader
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# Fokuserad granskning (efter varje webbplatsrelease)

Varför ska ni granska implementeringen var tredje månad? Så att ni kan ta itu med eventuella problem med datakvaliteten medan de fortfarande är små. Om du konsekvent utför den fokuserade granskningen efter varje webbplatsrelease kommer du att upptäcka att det är mycket enklare att utföra [fullständiga granskningar](/help/implement/review/full-review.md) vartannat år. Ni kommer också att förhindra att små problem växer till stora dataproblem som kan urholka intressenternas förtroende.

## &#x200B;1. Börja med de fem viktigaste KPI:erna

Genom att känna till era fem viktigaste nyckeltal (KPI) kan ni avgöra vilka mätvärden och dimensioner ni behöver undersöka. Om du inte har uppdaterat dina KPI:er de senaste sex månaderna eller om ditt företag inte har skapat KPI:er än, följ [dessa instruktioner](/help/implement/review/define-kpis.md).

## &#x200B;2. Se till att dina KPI-värden och -variabler fortfarande fungerar bra.

Kom ihåg att koduppdateringar kan få oönskade konsekvenser. Du vill se till att alla mått och mått som är associerade med dina [5 KPI:er](/help/implement/review/define-kpis.md) fortfarande fungerar som de ska. Det här görs helst direkt efter en webbplatsrelease. Om du inte har gjort det de senaste månaderna gör du det *nu*. Så här gör du:

* Skapa instrumentpaneler om du vill se timvisa trender för dessa viktiga mått och variabler (eller konfigurera [varningar](/help/components/alerts/alerts-overview.md) för varje mätvärde). Övervaka dem sedan i en dag eller två för att säkerställa att du får de data du förväntar dig, och att data är korrekta. Håll utkik efter inflammationspunkter. Var beredd på att åtgärda allvarliga problem omedelbart. Om du hittar avvikelser kan du ta reda på varför i datalagret, tagghanteringsreglerna och bearbetningsreglerna.
* Kör [Analytics Health Dashboard](https://express.adobe.com/page/tnNQGNlfzta3b/) igen för att övervaka breda trender för KPI-mått och -variabler.

*Mer information om hur du kontrollerar att dina mått och variabler fungerar som de ska finns i [de här tipsen](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) från Adobe Analytics Champion Sarah Owen.*

## &#x200B;3. Granska noggrant data från den uppdaterade delen av din webbplats

Se till att den senaste webbplatsreleasen inte inverkar negativt på datainsamlingen för det avsnittet på webbplatsen: granska all kod och alla variabler som motsvarar det avsnittet för att se till att den nya spårningen fungerar som avsett.

## &#x200B;4. Uppdatera dokumentationen

Om du nyligen har lagt till eller ändrat några mätvärden eller variabler måste du uppdatera ditt Business Requirement Document (BRD) och Solution Design Reference (SDR).

Om du inte har någon dokumentation om implementeringen exporterar du en lista med variabler och skapar din BRD eller SDR med [den här mallen](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=sv-SE#implementation).

## &#x200B;5. Åtgärda omedelbart eventuella luckor i datakvaliteten

Utvärdera situationen och ta fram en plan för att åtgärda uppgifterna. Gör sedan de ändringar du behöver, uppdatera dokumentationen och informera dina intressenter om ändringarna.

*Titta på den här 2-minutersvideon från Adobe Analytics Champion Sarah Owen om naturliga tider när du kan anpassa granskningar av din implementering till ditt hektiska schema:*


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Granska implementeringen](https://video.tv.adobe.com/v/328340?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


