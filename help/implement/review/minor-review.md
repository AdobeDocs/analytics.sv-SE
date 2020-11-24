---
title: Mindre implementeringsgranskning (efter varje webbplatsrelease)
description: Följ de här stegen för att se till att implementeringen inte är felfri och att den överensstämmer med dina nyckeltal.
translation-type: tm+mt
source-git-commit: 82064e267729b6995402bd122c6f71b3d38967a3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# Mindre implementeringsgranskning (efter varje webbplatsrelease)

Varför ska ni granska implementeringen efter varje webbplatsrelease? Eftersom du måste se till att dina koduppdateringar inte har några oönskade ändringar, och du bör åtgärda eventuella problem med datakvaliteten medan de fortfarande är små. Om du konsekvent utför den här mindre granskningen efter varje webbplatsrelease kommer du att märka att det är mycket enklare att göra [större granskningar](/help/implement/review/major-review.md) (var sjätte månad). Ni kommer också att förhindra att små problem växer till stora dataproblem som kan urholka intressenternas förtroende.

## 1. Hur påverkade releasen data för den delen av webbplatsen?

Gör noggranna enhetstester: Granska all kod och alla variabler som motsvarar den del av webbplatsen som du just har uppdaterat för att säkerställa att den nya spårningen fungerar som avsett.

## 2. Uppdatera din dokumentation

Uppdatera ditt verksamhetskrav Document (BRD) och Solution Design Reference (SDR) med alla variabler som du har lagt till eller ändrat för att kunna starta programmet.

Har du ingen dokumentation om implementeringen? Exportera en lista med variabler och skapa din BRD eller SDR med [den här mallen](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 3. Börja med de fem viktigaste KPI:erna

Genom att känna till era fem nyckeltal (KPI) kan ni identifiera de mått och mått ni behöver undersöka. Om du inte har uppdaterat dina nyckeltal de senaste sex månaderna eller om ditt företag inte har skapat nyckeltal än, följ [dessa instruktioner](/help/implement/review/define-kpis.md).

## 4. Fungerar alla KPI-värden och -variabler fortfarande bra efter releasen?

Kom ihåg att alla koduppdateringar kan få oönskade konsekvenser. Du vill vara säker på att alla mått och mått som är kopplade till [dina 5 KPI:er](/help/implement/review/define-kpis.md) fortfarande fungerar som de ska. Så här gör du:

* **Skapa instrumentpaneler** för att se timvisa trendvyer av dessa kritiska mått och variabler (du kan också skapa intelligenta aviseringar för varje mätvärde) och övervaka dem för en dag eller två efterversioner, för att säkerställa att du får de data du förväntar dig och att data är korrekta. Håll utkik efter inflammationspunkter. Var beredd på att åtgärda allvarliga problem omedelbart. Om du hittar avvikelser som inte ser bra ut kan du ta reda på varför i datalagret, tagghanteringsreglerna och bearbetningsreglerna.
* **Kör Analytics Health Dashboard** igen för att övervaka breda trender för dina KPI-värden och -variabler.
Mer information om hur du ser till att dina mätvärden och variabler fungerar som de ska finns i tipsen från Adobe Analytics Champion Sarah Owen.

## 5. Finns det brister i datakvaliteten?

Utvärdera situationen och ta fram en plan för att åtgärda uppgifterna. Gör sedan de ändringar du behöver, uppdatera dokumentationen och informera dina intressenter om ändringarna.

Titta på den här videon från Adobe Analytics Champion Sarah Owen om naturliga tidpunkter när du kan anpassa granskningar av din implementering till ditt hektiska schema:

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
