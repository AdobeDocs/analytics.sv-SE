---
description: I kalendern kan du ange datum och datumintervall eller välja en förinställning.
title: Översikt över kalender- och datumintervall
feature: Calendar
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: bec3ddc1f5ccf7b4baddabb0a376ed5775318df7
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 1%

---

# Översikt över kalender- och datumintervall

I kalendern kan du ange datum och datumintervall eller välja en förinställning.

Här är en video om hur du använder datumintervall och kalendrar i Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23973/?quality=12)

Kalenderval gäller på panelnivå, men du kan välja att använda dem på alla paneler. När du klickar på ett datumintervall i Arbetsyta visas den aktuella kalendermånaden och den föregående kalendermånaden i gränssnittet. Du kan justera dessa två kalendrar genom att klicka på höger- och vänsterpilarna i respektive övre hörn.

![Kalender](assets/aw_calendar2.png){width="60%"}

## Välj och tillämpa datumintervall {#select-apply}

Första klicket i en kalender startar ett datumintervallval. Den andra klickningen slutför ett datumintervallval som markeras. Om `Shift` om du håller ned tangenten (eller högerklickar om används) läggs den till i det markerade området.

Du kan också dra datum (och tidsdimensioner) till ett Workspace-projekt. Du kan välja specifika dagar, veckor, månader, år eller rullande datum.

[Använda datumintervall och kalender i Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html) (4:07)

| Inställning | Beskrivning |
|--- |--- |
| Valda dagar | Utvalda dagar/veckor/månader/år. |
| Gör datumintervallskomponenter relativa till panelkalendern | Håll datumen baserade på panelens datumintervall konsekventa. |
| Använd rullande datum | Med rullande datum kan du generera en dynamisk rapport som ser framåt eller bakåt under en angiven tidsperiod baserat på när du körde rapporten. Om du t.ex. vill rapportera alla beställningar som placerats i&quot;Senaste månaden&quot; (baserat på fältet Skapad den) och köra rapporten i december, ser du beställningar som gjorts i november. Om du körde samma rapport i januari skulle du se beställningar i december.<ul><li>**[!UICONTROL Date Preview]**: Anger vilken tidsperiod som den rullande kalendern omfattar.</li><li>**[!UICONTROL Start]**: Du kan välja mellan aktuell dag, aktuell vecka, aktuell månad, aktuellt kvartal, aktuellt år.</li><li>**[!UICONTROL End]**: Du kan välja mellan aktuell dag, aktuell vecka, aktuell månad, aktuellt kvartal, aktuellt år.</li></ul>Om du vill visa ett exempel läser du [Anpassade datumintervall](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). <br>Markerad som standard. |
| Datumintervall | Välj ett förinställt datumintervall. De senaste 30 dagarna är standard. **[!UICONTROL This week/month/quarter/year (excluding today)]** Med kan du välja från datumintervall som inte innehåller data för delar av dagen från och med idag. |
| Använd på alla paneler | Här kan du inte bara ändra det markerade datumintervallet för den aktuella panelen, utan även för alla andra paneler i projektet. |
| Använd | Använder endast datumintervallet på den här panelen. |

## Om relativa paneldatumintervall {#relative-panel-dates}

Om du arbetar i Workspace kan du göra datumintervallets komponenter relativa till panelkalendern.
Tre vanliga användningsområden där du ser relativa paneldatum som börjar gälla är Combo-diagram, Sammanfattning av nyckelmått och datumintervall i frihandstabellen.

Använda relativa paneldatumintervall

1. Välj **Arbetsyta** -fliken.
1. Välj **Tomt projekt**.
1. Lägg till mått, mätvärden och segment från den vänstra listen.
1. Klicka på panelens datumintervallfält för att växla den relativa panelens datumintervallinställning.
1. Välj **Gör datumintervallskomponenter relativa till panelkalendern**.
   * Välj alternativet om du vill att datumintervallets komponenter ska vara relativa till panelkalendern.
Om du väljer relativa datum baseras rullande datum på startdatumet för panelkalendern och inte på dagens datum.
   * Om det här alternativet inte är markerat baseras rullande datum på dagens datum.

   ![relativa paneldatum](assets/relative-date-selected.png){width="60%"}

1. Klicka **Använd**.
De relativa datumen visas i det övre högra hörnet.

   ![relativa datum i frihandsformat ](assets/relative-date-range1.png)

## Riktlinjer för relativa paneldatumintervall {#guidelines}

Tänk på följande när du använder relativa paneldatumintervall.

### Formler och relativa datumintervall {#formula-relative-dates}

Om du har markerat relativa datum används panelens startdatum som startpunkt i alla datumformler.

### Anpassade kalendrar och relativa datumintervall {#custom-calendar-formulas}

När du använder en veckobaserad anpassad kalender och lägger till månader eller år, beräknas förskjutningen för dagen i den angivna perioden enligt formeln. Det faktiska datumet kan vara ett annat på grund av förskjutningen. Formeln väljer landningsdagen på samma plats i den anpassade kalendern. Den tredje fredagen i den tredje veckan i en anpassad kalender.

### Om segment som använder rullande datum och relativa paneldatumintervall {#segments-relative-dates}

Om du skapar ett segment eller använder ett segment med ett rullande datum, t.ex. de senaste 7 dagarna eller de senaste 2 veckorna, och du klickar på segmentförhandsvisningen, startar det rullande datumet från *Idag* i stället för panelens startdatum. Det innebär att förhandsvisningen av segmentet inte matchar när du faktiskt använder segmentet i tabellen. Förhandsgranskningen påverkas, inte själva segmentet.
