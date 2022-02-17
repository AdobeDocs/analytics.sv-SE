---
description: Felsök och åtgärda problem som rör segment.
title: Felsökning av segmentering
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---

# Felsökning av segmentering

## Fel: &quot;Inkompatibla element i det här segmentet&quot; {#incompatible}

Det här felet inträffar när du försöker spara ett segment i Data warehouse-mappen där segmentet innehåller element som inte är kompatibla med Data warehouse. Gör något av två för att lösa det här felet:

* Spara segmentet i en annan mapp
* Ta bort eller ändra inkompatibla delar av segmentet.

## Varför returnerar mitt segment inga data alls? {#no-data}

Möjliga orsaker:

* Invertera kapsling - t.ex. kapsling av en besökarbehållare under en besöksbehållare.
* Rapporten stöder inte segmentering.
* Det finns inga data som matchar segmenteringskriterierna.

## Varför kan jag inte se segmentet jag skapade i segmenthanteraren? {#invisible}

Möjliga orsaker:

* Vissa dimensioner är bara tillgängliga i Data warehouse och inte i segmenthanteraren.
* Segmentet är inte kompatibelt med rapporter och analyser.
* Segmentet kontrolleras bara för en viss rapportserie.
* Ett delat segment kan ha tagits bort av en annan användare.
* Det gick inte att läsa in segment på grund av ett datacenter- eller webbläsarcachefel.
* Segmentet har inte sparats.
* IP-adressen kan blockeras vid användarens slut.

## Varför verkar de siddata som visas när du har använt ett segment felaktigt? {#page-data}

Möjliga orsaker:

* Regler/operatorer är felaktiga för det obligatoriska resultatet.
* Felaktig användning av behållare i segmentet.
* Trafikvariablerna som används för segmentering är inte korrekt inställda eller har gått ut.
