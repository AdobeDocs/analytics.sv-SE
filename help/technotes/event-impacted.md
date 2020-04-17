---
title: Analysera data som påverkas av händelser
description: Förstå hur data som påverkas av en händelse bidrar till den övergripande datakvaliteten.
translation-type: tm+mt
source-git-commit: 09c7c1f4b4a6f67243cc72c642fd83a75406fb76

---


# Analysera data som påverkas av händelser

Ibland kan en händelse påverka datakvaliteten i organisationen. Exempel:

* En robot som skickar data som miljontals dollar i intäkter
* Din organisation har publicerat en uppdatering till din webbplats som har negativ inverkan på er Analytics-implementering
* Andra problem som påverkar datakvaliteten eller fullständigheten

Om sajten har problem med datakvaliteten, implementeringsproblem eller andra luckor i data kanske du vill utesluta den från rapporteringen för att förhindra att du fattar beslut om partiella data. Använd de här avsnitten för att mäta effekten av händelsen på dina data och bestämma hur du vill fortsätta.

## Analysera och exkludera data med hjälp av segmentering

Adobe Analytics är ett enkelt och robust sätt att fokusera på eller exkludera data med hjälp av segmentering. Du kan använda datumintervalldimensioner inom segment för att filtrera bort eller fokusera på dessa specifika datum. Se [Uteslut specifika datum i analysen](/help/components/c-segmentation/use-cases/exclude-date-range.md) i användarhandboken för komponenter.

## Jämföra en händelse med tidigare datumintervall

Om du vill veta mer om hur stor inverkan en händelse har på dina data över tiden kan du använda datumjämförelsen i Analysis Workspace. Med den här funktionen kan du jämföra data dag för dag, vecka för vecka eller månad för att se hur de ser ut jämfört med tidigare intervall. Du kan sedan använda den här jämförelsen för att avgöra hur mycket en händelse påverkar trender. Se [Jämför datum som påverkas av en händelse med tidigare intervall](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) i användarhandboken för Analysera.

## Använd en kalenderhändelse i Rapporter och analyser

Om du använder Rapporter och analyser kan du använda en [kalenderhändelse](/help/components/t-calendar-event.md) för att markera berörda dagar i alla trendrapporter. Den här metoden gäller inte för Analysis Workspace.

1. Navigera till **[!UICONTROL Components]** > **[!UICONTROL Calendar events]**.
2. Ange önskad titel, datumintervall och anteckningstext.
3. Klicka på **[!UICONTROL Save]**.

![Kalenderhändelse](assets/exclude_calendar_event.jpg)
