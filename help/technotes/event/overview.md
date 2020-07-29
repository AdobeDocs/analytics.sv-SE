---
title: Analysera data som påverkas av händelser
description: Förstå hur data som påverkas av en händelse bidrar till den övergripande datakvaliteten.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---


# Analysera data som påverkas av händelser

Ibland kan en händelse påverka datakvaliteten i organisationen. Exempel:

* En robot som skickar data som miljontals dollar i intäkter
* Din organisation har publicerat en uppdatering till din webbplats som har en negativ inverkan på din Analytics-implementering
* Andra problem som påverkar datakvaliteten eller fullständigheten

Om sajten har något slags problem med datakvaliteten kanske du vill utesluta den från rapporteringen för att förhindra att du fattar affärsbeslut om den. Använd de här avsnitten för att mäta effekten av händelsen på dina data och bestämma hur du vill fortsätta.

## Identifiera orsaken till en händelse

Om du är osäker på varför du ser ett spike eller en datasläppning kan du läsa [Felsöka spikes/drops i data](spikes-drops.md).

## Analysera och exkludera data med hjälp av segmentering

Adobe Analytics erbjuder ett enkelt och robust sätt att fokusera på eller exkludera data med hjälp av segmentering. Du kan använda datumintervalldimensioner inom segment för att filtrera bort eller fokusera på dessa specifika datum. See [Exclude specific dates in analysis](segments.md).

## Jämföra en händelse med tidigare datumintervall

Om du vill veta mer om hur stor inverkan en händelse har på dina data över tiden kan du använda datumjämförelsen i Analysis Workspace. Med den här funktionen kan du jämföra data dag för dag, vecka för vecka eller månad för att se hur de ser ut jämfört med tidigare intervall. Du kan sedan använda den här jämförelsen för att avgöra hur mycket en händelse påverkar trender. Se [Jämför datum som påverkas av en händelse med tidigare intervall](compare-dates.md).

## härleda data med beräknade värden

När du har skapat segment och använt datumjämförelse kan du kombinera båda dessa begrepp för att korrigera trenddata med hjälp av beräknade värden. Inkludera segmenten i ett beräknat mätvärde och multiplicera sedan de berörda dagarna med den förskjutning som påträffades vid jämförelse av datum. See [Derive data impacted by events](calcmetrics.md).

## Förmedla genomslag till användare i organisationen

När du har förberetts för hur du tänker hantera en händelse kan du [kommunicera med användare i organisationen](communicate.md). Adobe erbjuder flera ställen i Analytics där du kan montera text som informerar användarna om vad som hänt och vilka komponenter de kan använda.

## Video

I den här videon går du igenom alla steg ovan.

>[!VIDEO](https://video.tv.adobe.com/v/33316?quality=12)

* **0:27**: Uteslut data med segmentering
* **2:55**: Jämföra en händelse med tidigare intervall
* **8:42**: härleda data med beräknade värden
* **11:46**: förmedla genomslag till användarna
