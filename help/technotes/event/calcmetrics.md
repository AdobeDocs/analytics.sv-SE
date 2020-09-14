---
title: Härleda data som påverkats av händelser
description: Använd beräknade värden för att korrigera trenddata som påverkas av en händelse.
translation-type: tm+mt
source-git-commit: 8e193de6dbb51cb640218a0c7b1b501d4f1eaa27
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 4%

---


# Härleda data som påverkats av händelser

Om du har data [som påverkas av en händelse](overview.md)kan du använda beräknade värden för att härleda beräknade värden under händelseperioden. Om du till exempel har haft en händelse som orsakade en 25-procentig dataminskning kan du använda den som multiplikator i ett beräknat mått.

De här stegen fungerar bäst när du förstår effekten av en händelse, både från en segmentering och en datumjämförelse. Se till att följa [Jämför datum som påverkas av en händelse med tidigare intervall](compare-dates.md) och [Uteslut specifika datum i analysen](segments.md) innan du följer den här sidan.

>[!NOTE]
>
>Denna metod är en uppskattning baserad på en specifik uppsättning indata och datumintervall. Det kommer inte att vara en heltäckande lösning för alla användningsfall eller datasegment. Dessutom kräver det här tillvägagångssättet att det berörda datumintervallet har minst 1 träff att beräkna från.

Så här skapar du ett uppskattat beräknat mått för den påverkade tidsperioden:

1. Skapa två segment för&quot;Påverkade dagar&quot; och&quot;Uteslut påverkade dagar&quot;, enligt beskrivningen under [Uteslut specifika datum i analysen](segments.md).
2. Navigera till **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**.
3. Klicka på **[!UICONTROL Add]**.
4. Dra båda segmenten ovan till definitionsytan. Ändra operatorn mellan dem till en `+` summa för att summera dem.
5. Lägg till önskat mätvärde i båda segmenten. Du kan till exempel använda måttet Besök.

   ![Segmentbyggare](assets/event_segment_builder.png)

6. Klicka **[!UICONTROL Add]** i det övre högra hörnet i behållaren Påverkade dagar och klicka sedan på **[!UICONTROL Static number]**. Ställ in det statiska talet till den procentandel som du vill förskjuta dina data, så som anges under [Jämför datum som påverkas av en händelse med tidigare intervall](compare-dates.md). I det här exemplet är förskjutningen 25 %, eller 1,25.

   ![Statiskt nummer](assets/event_static_number.png)

7. Använd det&quot;korrigerade&quot; måttet sida vid sida i en ritad frihandstabell. Alla dagar utanför händelsen återspeglar deras normala måttantal, medan alla berörda dagar använder multiplikatorförskjutningen.

   ![Korrigerat mätvärde](assets/event_corrected.png)

8. Visa data i en linjevisualisering för att se effekten av det korrigerade måttet.

   ![Korrigerad rad](assets/event_line.png)
