---
description: Ändra inställningar och egenskaper för alla typer av övertäckningsvisualiseringar i Activity Map.
title: Konfigurera inställningar för Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
source-git-commit: 13ad9d40ad74a8dffe05d899db54f4d77cbcc34c
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 0%

---

# Konfigurera inställningar för Activity Map

På inställningspanelen Activity Map kan du ändra inställningar och egenskaper för alla typer av övertäckningsvisualiseringar.

**[!UICONTROL Activity Map overlay]** > **Visa inställningar (kugghjulsikon)** > **[!UICONTROL Settings]**

## Allmänna inställningar

Ändra allmänna inställningar för tillägget och övertäckningarna.

* **[!UICONTROL Companies]**: Visar den aktuella Analytics-organisationen som du är inloggad på.
* **[!UICONTROL Page name]**: Visar namnet på den aktuella sidan.
* **[!UICONTROL Language]**: Ändrar språk för tilläggsetiketter i Activity Map. Den här inställningen ändrar inte innehåll på din webbplats eller länknamn i rapporter. Språk som stöds är engelska, franska, kinesiska (förenklad), kinesiska (traditionell), tyska, japanska, koreanska, spanska och portugisiska.
* **[!UICONTROL Label overlays with]**: Avgör vad bubblan eller övertoningstexten är. Standardinställningen är [!UICONTROL Rank]. Alternativen är:
   * **[!UICONTROL No label]**: Det finns ingen text i etiketterna, vilket gör dem till färgade rutor
   * **[!UICONTROL Value]**: Visar antalet länkklick ([Förekomster](/help/components/metrics/occurrences.md))
   * **[!UICONTROL Percent]**: Visar andelen länkklick jämfört med det totala antalet länkklick på sidan
   * **[!UICONTROL Rank]**: Länkens numeriska rankning efter antalet länkklick.
* **[!UICONTROL Label font size]**: Anger storleken på texten i bubblan eller övertoningen.
* **[!UICONTROL Gradient color]**: Gör att du kan ändra övertoningsfärgen när visualiseringstypen är [!UICONTROL Gradient].
* **[!UICONTROL Bubble color]**: Gör att du kan ändra bubbelfärgen när visualiseringstypen är [!UICONTROL Bubble].
* **[!UICONTROL Color gradient based on]**: Avgör vilket mått en länks färgintensitet baseras på när visualiseringstypen är [!UICONTROL Gradient].
   * **[!UICONTROL Top 30 rankings]**: Färgintensiteten har normaliserats för de 30 mest använda länkarna.
   * **[!UICONTROL Absolute metric value]**: Färgintensiteten är en funktion av det absoluta måttvärdet.
* **[!UICONTROL Gradient transparency]**: Anger genomskinligheten för övertoningsövertäckningar när visualiseringstypen är [!UICONTROL Gradient]. Med det här reglaget kan du göra färgövertäckningen helt genomskinlig, helt ogenomskinlig eller var som helst däremellan.

## Standardinställningar

Justera inställningarna för standardvyn.

* **[!UICONTROL Dynamic data filtering]**: Gör att du kan ändra vilka länkar som visas.
   * **[!UICONTROL Top]**: Visar de mest populära länkarna. Använd den numeriska listrutan till höger för att bestämma antalet topplänkar som ska visas. Du kan välja mellan 1, 10, 50 och 100.
   * **[!UICONTROL Bottom]**: Visar de minst populära länkarna baserat på listrutan Nummer. Använd den numeriska listrutan till höger för att bestämma hur många nedersta länkar som ska visas. Du kan välja mellan 1, 10, 50 och 100.
   * **[!UICONTROL All links]**: Använd inte dynamisk datafiltrering. Den numeriska listrutan gäller inte när det här alternativet är markerat.
* **[!UICONTROL Hide overlays for links that received no hits]**: Länkar på sidan utan länkklick visar inte någon övertäckning. Dessa länkar undantas från dynamisk datafiltrering.

## Live-inställningar

* **[!UICONTROL Display top]**: Visa det översta antalet generatorer eller förlorare baserat på den numeriska listrutan till vänster.
* **[!UICONTROL Exclude bottom (%)]**: Filtrera ut den nedersta procentandelen av länken så att endast länkar med tillräckligt med data visas för att visa relevanta vinster eller förluster. Procentandelen beräknas utifrån antalet länkar på den sidan. Om du till exempel filtrerar bort de nedre 10 % av en lista med 200 länkar filtreras de nedre 20 länkarna ut.
* **[!UICONTROL Auto update data]**: Avgör om Analytics-data som visas i övertäckningen automatiskt uppdateras när en ny period beräknas.
* **[!UICONTROL Auto update period]**: När det här alternativet är markerat uppdaterar sidan med varje ny datahämtning så att länkarna på sidan synkroniseras närmare med insamlade data.
