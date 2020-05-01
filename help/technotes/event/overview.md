---
title: Analysera data som påverkas av händelser
description: Förstå hur data som påverkas av en händelse bidrar till den övergripande datakvaliteten.
translation-type: tm+mt
source-git-commit: b3142a83f7e449380b0dccca8908e988d1abd672

---


# Analysera data som påverkas av händelser

Ibland kan en händelse påverka datakvaliteten i organisationen. Exempel:

* En robot som skickar data som miljontals dollar i intäkter
* Din organisation har publicerat en uppdatering till din webbplats som har negativ inverkan på er Analytics-implementering
* Andra problem som påverkar datakvaliteten eller fullständigheten

Om sajten har problem med datakvaliteten, implementeringsproblem eller andra luckor i data kanske du vill utesluta den från rapporteringen för att förhindra att du fattar beslut om partiella data. Använd de här avsnitten för att mäta effekten av händelsen på dina data och bestämma hur du vill fortsätta.

## Analysera och exkludera data med hjälp av segmentering

Adobe Analytics är ett enkelt och robust sätt att fokusera på eller exkludera data med hjälp av segmentering. Du kan använda datumintervalldimensioner inom segment för att filtrera bort eller fokusera på dessa specifika datum. Se [Uteslut specifika datum i analysen](segments.md).

## Jämföra en händelse med tidigare datumintervall

Om du vill veta mer om hur stor inverkan en händelse har på dina data över tiden kan du använda datumjämförelsen i Analysis Workspace. Med den här funktionen kan du jämföra data dag för dag, vecka för vecka eller månad för att se hur de ser ut jämfört med tidigare intervall. Du kan sedan använda den här jämförelsen för att avgöra hur mycket en händelse påverkar trender. Se [Jämför datum som påverkas av en händelse med tidigare intervall](compare-dates.md).

## härleda data med beräknade värden

När du har skapat segment och använt datumjämförelse kan du kombinera båda dessa begrepp för att korrigera trenddata med hjälp av beräknade värden. Inkludera segmenten i ett beräknat mätvärde och multiplicera sedan de berörda dagarna med den förskjutning som påträffades vid jämförelse av datum. Se [Härledda data som påverkas av händelser](calcmetrics.md).

## Förmedla genomslag till användare i organisationen

När du har förberetts för hur du tänker hantera en händelse kan du [kommunicera med användare i organisationen](communicate.md). Adobe erbjuder flera platser i Analytics där du kan placera text för att informera användarna om vad som hände och vilka komponenter de kan använda.

## Video

I den här videon går du igenom alla steg ovan.

>[!VIDEO](https://video.tv.adobe.com/v/33316?quality=12)

* **0:27**: Uteslut data med segmentering
* **2:55**: Jämföra en händelse med tidigare intervall
* **8:42**: härleda data med beräknade värden
* **11:46**: förmedla genomslag till användarna
