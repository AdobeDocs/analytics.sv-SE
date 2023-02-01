---
description: I kalendern kan du ange datum och datumintervall eller välja en förinställning.
title: Översikt över kalender- och datumintervall
feature: Calendar
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: b08200266204bc01c943194ea2b0b002c2bfa878
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 2%

---

# Översikt över kalender- och datumintervall

I kalendern kan du ange datum och datumintervall eller välja en förinställning.

Här är en video om hur du använder datumintervall och kalendrar i Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23973/?quality=12)

Kalenderval gäller på panelnivå, men du kan välja att använda dem på alla paneler. När du klickar på ett datumintervall i Arbetsyta visas den aktuella kalendermånaden och den föregående kalendermånaden i gränssnittet. Du kan justera dessa två kalendrar genom att klicka på höger- och vänsterpilarna i respektive övre hörn.

![Kalender](assets/aw_calendar1.png)

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

Om du arbetar i Workspace kan du göra datumintervallskomponenterna relativa till panelkalendern så att data som förhandsvisas i den vänstra listen (eller i komponenter) baseras på panelens datumintervall. Tre vanliga användningsfall där du ser relativa paneldatum som börjar gälla är kombinationsdiagram, sammanfattning av nyckelvärden och datumintervall i frihandstabellen.

Använda relativa paneldatumintervall

1. Välj **Arbetsyta** -fliken.
1. Välj **Tomt projekt**.
1. Lägg till mått, mätvärden och segment från den vänstra listen.
1. Klicka på panelens datumintervallfält för att växla den relativa panelens datumintervallinställning.
1. Markera eller avmarkera **Gör datumintervallskomponenter relativa till panelkalendern**.
   * Välj alternativet om du vill att datumintervallets komponenter ska vara relativa till panelkalendern.
   * Om du avmarkerar det här alternativet innebär det att datumintervallen på panelen (antingen Sammanfattning av nyckelmått, Kombinationsdiagram eller Piller för lila datum) inte uppdateras om panelens datumintervall ändras. Detta är standardinställningen.

   ![relativa paneldatum](assets/relative-date-snippet.png)

1. Klicka **Använd**.
De relativa datumen visas i det övre högra hörnet.

   ![relativa datum i frihandsformat ](assets/relative-date-range1.png)